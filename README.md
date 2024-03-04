# Fabric-Scanner-API-Project to capture Fabric artifact permissions and accesses

Update 2023/03/04:
1. Added Last Refresh Date to the report to indicate when the data was last updated

Currently, there is no way in Fabric to show which artifacts are shared with which users, groups or Apps. The objective of this project capture this information via the Fabric Scanner APIs and use Power BI to visualize this information

This repo will consist of a notebook and Power BI report sample. The notebook captures metadata about accesses/grant for fabric artifacts and stores into a lakehouse delta table. Power BI report is created on the delta table

Steps:
1. Import the notebook 'Scanner API demo.ipynb' in the workspace of your choice. (If you see 'Missing Lakehouse' error in the left pane window, select the lakehouse where final table created by the notebook will reside in)
2. Follow all the instructions in the notebook. After successful completion of the notebook, a delta table called 'WorkspaceAccessMetadata' will be created in the lakehouse you had selected in the notebook
3. Create a custom semantic model (dataset) called 'WorkspaceAccessesMetadata' in the lakehouse you had selected in the notebook. Include the table 'WorkspaceAccessMetadata' in the semantic model
4. Import the Power BI 'Fabric Artifacts Access Metadata Report' in Power BI desktop. Ensure you are logged in as same user as Fabric. You should see a pop-up that report is not able to find the dataset. Click on Edit and select semantic model (dataset) created in the previous step. Save and publish the report in the workspace you saved the notebook and semantic model earlier. Now you should be able to open the report in Fabric and use it

Future Enhancements planned:
1. Divide list of workspace ids in chunks of 100 workspaces and execute each chunk
2. Implement incremental scan

Report screenshots


![Report screeshot 1](https://github.com/sagarbathe/Fabric-Scanner-API-Project/assets/110572270/43cb11c3-fe8d-4b30-97ff-e1a2bd3421a1)


![Report screeshot 2](https://github.com/sagarbathe/Fabric-Scanner-API-Project/assets/110572270/86af87bd-41bf-4bd3-84e5-72ba5958833e)
