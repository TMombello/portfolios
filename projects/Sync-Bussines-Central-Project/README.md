# Dynamics 365 Business Central Synchronization
Implementation data synchronization between the website database and Dynamics 365 Business Central.
## Architecture diagram
![Architecture Diagram](/assets/images/Architecture.jpg)

## Workflow
The workflow collects reseller details, purchase orders, and product data via the frontend website into a PostgreSQL database, then triggers a Logic App every 5 minutes (or event-driven) to UPSERT this data into Dynamics 365 Business Central's relevant tables
Workflow Steps
Collection: Frontend captures reseller company info, POs, products into PostgreSQL.
Sync: Logic App performs scheduled (5-min) or event-driven UPSERT to D365 BC tables.
Admins can monitor the sync process history through an Application to review Logs or open a specific run to check details of the execution, including any errors encountered. They can also re-trigger failed syncs or perform ad-hoc syncs as needed.

## Components
 1. **Public website**: These components are not part of the project's scope and are shown in the tiagram exclusively to procide contextual inforpation.

 2. **Azure-Logic apps**: Orchestrator of the synchronization process. It can be triggered by an event or on a scheduled basis. It retrieves data from the PostgreSQL database, transforms it as needed, and then updates or creates corresponding records in Dynamics 365 Business Central using its APIs.

 3. **Power Platform - Synchronization Monitoring app**: Model driven app to monitor the status of the sync job, re-trigger any failed sync or trigger ad-hoc sync.

 4. **Dynamics 365 Business Central**: Fully mandaged Saas solution operated by Micrososft. It serves as the target system for data synchronization. This project scope does not iclude any customazation to this sistem.
## Scenario details
The synchronization process is designed to ensure that data from the website's PostgreSQL database is accurately and efficiently transferred to Dynamics 365 Business Central. The Azure Logic App will handle the data retrieval, transformation, and synchronization tasks, while the Power Platform app will provide visibility and control over the synchronization process for IT administrators. This architecture allows for real-time or scheduled synchronization, ensuring that Business Central always has the most up-to-date information from the website.

## Considerations
- **Data Volume**: The synchronization solution should be designed to handle the expected volume of data without performance degradation. This may involve implementing batching or throttling mechanisms in the Logic App.
- **Error Handling**: Robust error handling and retry mechanisms should be implemented in the Logic App to ensure that transient failures do not result in data loss. The monitoring app should provide clear visibility into any errors that occur during synchronization.
