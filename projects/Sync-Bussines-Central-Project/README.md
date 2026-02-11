# Dynamics 365 Business Central Synchronization
Implementation data synchronization between the website database and Dynamics 365 Business Central.
## Architecture diagram
![Architecture Diagram](/assets/images/Architecture.jpg)

## Workflow
The following steps describe the workflow that's shown in the architecture diagram:
1. **Website Public**: The public website is built on top of a PostgreSQL database hosted in Azure. This database contains all the relevant information that needs to be synchronized with Dynamics 365 Business Central.
2. **Azure Logic Apps - sync**: An Azure Logic App is responsible for orchestrating the synchronization process. It can be triggered either by an event (e.g., a new record is added to the database) or on a scheduled basis (e.g., every hour). The Logic App retrieves data from the PostgreSQL database, transforms it as needed, and then updates or creates corresponding records in Dynamics 365 Business Central using its APIs.
3. **Power Platform - Synchronization Monitoring app**: A Model-Driven Power App serves as a monitoring dashboard for the synchronization process. It provides IT administrators with real-time insights into the status of sync jobs, including any errors or failures. Admins can also use this app to manually trigger syncs or re-trigger failed syncs.
4. **Dynamics 365 Business Central**: This is the target system where the synchronized data from the website is stored and managed. It is a fully managed SaaS solution operated by Microsoft, and it serves as the central hub for business operations. The synchronization process ensures that the data in Business Central is always up-to-date with the latest information from the website.

## Components
#### 1. **Public website**: These components are not part of the project's scope and are shown in the tiagram exclusively to procide contextual inforpation.

#### 2. **Azure-Logic apps**: Orchestrator of the synchronization process. It can be triggered by an event or on a scheduled basis. It retrieves data from the PostgreSQL database, transforms it as needed, and then updates or creates corresponding records in Dynamics 365 Business Central using its APIs.

#### 3. **Power Platform - Synchronization Monitoring app**: Model driven app to monitor the status of the sync job, re-trigger any failed sync or trigger ad-hoc sync.

#### 4. **Dynamics 365 Business Central**: Fully mandaged Saas solution operated by Micrososft. It serves as the target system for data synchronization. This project scope does not iclude any customazation to this sistem.
## Scenario details
The synchronization process is designed to ensure that data from the website's PostgreSQL database is accurately and efficiently transferred to Dynamics 365 Business Central. The Azure Logic App will handle the data retrieval, transformation, and synchronization tasks, while the Power Platform app will provide visibility and control over the synchronization process for IT administrators. This architecture allows for real-time or scheduled synchronization, ensuring that Business Central always has the most up-to-date information from the website.

## Consderations
- **Data Volume**: The synchronization solution should be designed to handle the expected volume of data without performance degradation. This may involve implementing batching or throttling mechanisms in the Logic App.
- **Error Handling**: Robust error handling and retry mechanisms should be implemented in the Logic App to ensure that transient failures do not result in data loss. The monitoring app should provide clear visibility into any errors that occur during synchronization.
