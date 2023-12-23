# Fabric-Scanner-API-Project

This repo will consist of a notebook and Power BI report sample. The notebook captures metadata about accesses/grant for fabric artifacts and stores into a lakehouse delta table. Power BI report is created on the delta table

Steps:
1. Import the notebook 'Scanner API demo.ipynb' in the workspace of your choice. Follow all the instructions in the notebook. After successful completion of the notebook, a delta table called 'WorkspaceAccessMetadata' will be created in the lakehouse you had selected in the notebook
2. Create a custom semantic model (dataset) called 'WorkspaceAccessesMetadata' in the lakehouse you had selected in the notebook. Include the table 'WorkspaceAccessMetadata' in the semantic model
3. Import the Power BI 'Fabric Artifacts Access Metadata Report' in Power BI desktop. Ensure you are logged in as same user as Fabric. It should prompt you to select semantic model (dataset). Select the one created in the above step. Save the report. Now you should be able to open the report in Fabric and use it
