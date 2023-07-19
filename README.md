# Hotfix Database
Website to store hotfixes using MongoDB and Node.js

# SETUP

To get the application setup on a VM follow the steps below.
1. Navigate to \\usaust-file6\HawkTransfer\MPeterka and download hotfix.zip, VSCode, ChromeSetup.exe, and node-v18.16.1-x64. These will be used to get the app running and on the localhost browser
2. Once all of the files are downloaded, open the hotfix.zip and move the folder inside to the desktop
3. Open the folder on the desktop in VSCode and start a new terminal
4. In the VSCode terminal type in 'node index.js' making sure that the path of the terminal is in the main part of the folder where index.js is located
5. Open Chrome and navigate to localhost:3000, this is where the login page will be

If for any reason the app crashes, to reset the app repeat steps 4 and 5


# HOW TO USE


Homepage
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  
Log in using Emerson credentials
  
  
Data Homepage
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  
Search Bar - in the top right where you can select what category and enter text to search for in the entire database. This will redirect to a new page with all of the filtered hotfixes
  
Date Ascending/Descending - sort the database by either descending or ascending date
  
Export Data - To export data click the export data button and it will download a JSON file with all of the data in the database. This is used to transfer the application to a new host since the database is hosted on the local machine
  
Import Data - To import data, ensure that a file named 'exported_data.json' is in the folder that the main application is in. The file must be in JSON format using the format of the exported data. This will skip     duplicates and add the data to the database and redirect to the main data page
  
Logout - in the top right there is a logout button that will log the user out and return to the login page
  
Clicking on HMS Request # - clicking on the HMS request # will bring the user to the manage hotfix page where the user can download as a CSV, JSON, or docx file as well as delete and update the hotfix
  
Clicking on HMS Bug # - clicking on the HMS bug # will bring the user to the HMS homepage where the user can find the hotfix clicked on
  
Clicking on Azure DevOps Bug # - clicking on the Azure DevOps Bug # will redirect the user to the Azure DevOps page for the bug that was selected
    
    
Add Hotfix
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  
This page is used to upload a hotfix to the database. To do so, enter all of the fields and if not applicable to the hotfix, then put n/a and click save. This will update the database and redirect the user to the data page
  

Manage Hotfix
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

This page allows the user to edit or delete the hotfix that was selected. The page also allows the user to download the hotfix as a CSV, JSON, or docx file to send to DevOps efficiently
