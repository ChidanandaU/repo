# Introduction 
The following repository hosts code for the Databricks and SQL DB Project.

# Python, Pyspark Local Environment Setup:
1.	Pre-Requisistes:
    - Visual Studio Code with Python Extension
    - Open JDK 8 Installed with JAVA_HOME Environment Variable Setup
    - Git
    - Anaconda
2.	Clone the repo onto the local system
3.  Create conda Environment with python version created in accordance to Databricks Runtime Version on the cluster used for Development. Refer [Databricks Connect](https://docs.microsoft.com/en-us/azure/databricks/dev-tools/databricks-connect).
4.  In the Conda Environment, install databricks-connect package. pip install -U "databricks-connect==x.y.*". Use x and y according to the Databricks Runtime Version of the cluster.
5.  Run databricks-connect configure command on Terminal to configure the following
    - Workspace URL
    - Personal Access Token
    - Cluster ID
    - Organisation ID
    - Cluster Port
Refer to the document in Point (3) to check how to get the above.
6.	Run the command on the terminal databricks-connect get-jar-dir. Copy the O/P of this command
7.	Open the Visual Studio Code
    - Press Ctrl + Shift + P
    - Search : open user settings in the command palette
    - Search Python
    - Click on settings.json
    - add the "python.envPath" property and assign the value equal to the value we got in (6).
8. Traverse to the EDM-Platform/EDM-Ingestion-Framework/code/deployment
9. pip install -r requirements.txt
10. pip install -e edm_adbk_package

# SQL Local Environment Setup
1. Pre-Requisites:
    - Azure Data Studio with SQL Database Projects Extension
    - .Net Framework
2. Open the Azure Data Studio
3. Click on Projects Menu.
4. Click on Open Existing
5. Select the appropriate .sqlproj file

# Python, SQL Coding Standards and Naming Conventions
[EDM Coding Standards and Naming](https://meicrosoftapc.sharepoint.com/:w:/t/SCBEDMp-Delivery/ESX3pQgOw8lEqP2pYyyNJeIB5PlZz89MamP8vpxj5JVHkQ?e=5fWw37)

# Branching Strategy
1. The Final Branch that will be used for release will be the main branch
2. All code checkins into the main branch must happen via PR raised from main_dev branch.
3. Code must be checked in into the main_dev branch from the task branches using PR.
4. All Code checkins from the task branch during a sprint must be checked in to the main_dev branch.
5. Code should be merged into the main branch after the completion of a sprint. 
6. Before raising PR to the main_dev branch from the task branch, please run the pyspark-python test cases locally, if modifications are done in python-pyspark package. All Test cases should pass.
7. Before raising PR to the main_dev branch from the task branch, please build the SQL Project From Azure Data Studio. The Build must succeed without any errors.