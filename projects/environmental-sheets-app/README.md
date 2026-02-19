# Environmental Sheets Solution
The solution is designed to facilitate the submission, approval, and management of environmental sheets. 
## Architecture Diagram
![Architecture Diagram](/assets/images/Architecture-Environmental.jpg)
## Workflow
The following steps describe the workflow that's shown in the architecture diagram:
1. The **Canvas App** is used for inspectors to fill out and submit environmental sheets for approval. The app includes forms for data entry, image uploads, and submission functionality. Once a sheet is submitted, it triggers a Power Automate flow that handles the approval process and data storage.
2. The approvers will recceive an email notification when a sheet is submitted for approval. The sheet contains all information and images with evidence of enviromental damage.
3. The sheet will be stored in a SharePoint list for record-keeping and future reference. The images will be stored in a SharePoint document library, and the links to the images will be included in the SharePoint list.
4. The managment of sheets will be done through a Power BI dashboard, which will provide insights and analytics on the environmental sheets submitted, including trends, common issues, and areas for improvement.

## Components
1. ** Power Apps**: The Environmental Sheets App is a Canvas Power App that allows inspectors to fill out and submit environmental sheets for approval. The app includes forms for data entry, image uploads, and submission functionality.
2. **Power Automate**: Power Automate is used to create a flow that triggers when a sheet is submitted for approval. The flow sends an email notification to the approvers with the details of the sheet and the images attached in PDF file. It also handles the storage of the sheet data in a SharePoint list and the images in a SharePoint document library.
3. **SharePoint**: SharePoint is used to store the environmental sheets and the associated images. A SharePoint list is created to store the sheet data, while a SharePoint document library is used to store the images. The links to the images are included in the SharePoint list for easy access.
4. **Power BI**: Power BI is used to create a dashboard for management to monitor and analyze the environmental sheets submitted. The dashboard provides insights into trends, common issues, and areas for improvement based on the data collected from the sheets.
## Scenario details
Before the implementation of the Environmental Sheets App, the process of submitting and managing environmental sheets was manual and time-consuming. Inspectors had to fill out paper forms, take photos, and submit them to approvers via email or in person. This often led to delays in the approval process and difficulties in tracking and managing the sheets.
The Environmental Sheets App is designed to streamline the process of submitting and managing environmental sheets. Inspectors can easily fill out the necessary information and upload images as evidence of environmental damage. The approval process is automated through Power Automate, ensuring that approvers are notified promptly. The use of SharePoint for data storage allows for organized record-keeping, while the Power BI dashboard provides valuable insights for management to make informed decisions and take necessary actions to address environmental issues.
## Consderations
- **User Training**: It is important to provide training to inspectors and approvers on how to use the Environmental Sheets App effectively. This will ensure that they are comfortable with the new process and can utilize all the features of the app.

