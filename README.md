# Hotfix Database
Website to store hotfixes using MongoDB and Node.js.
<br>
<br>

# SETUP

To get the application setup on a VM follow the steps below:
1. Navigate to \\\usaust-file6\HawkTransfer\MPeterka and download hotfix.zip and install both ChromeSetup.exe and node-v18.16.1-x64. These will be used to get the app running and on the localhost browser.
2. Once all of the files are downloaded, open the hotfix.zip and move the folder inside to the desktop.
3. Start a new terminal in the directory of the file just moved to the desktop.
4. In the terminal type in 'node index.js' making sure that the path of the terminal is in the main part of the folder where index.js is located.
5. Open Chrome and navigate to localhost:3000, this is where the login page will be.

If for any reason the app crashes, to reset the app repeat steps 4 and 5.
<br>
<br>


# HOW TO USE


Homepage
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  
Log into the database using Emerson credentials.
<br>
<br>
  
  
Data Homepage
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Search Bar - in the top right where you can select what category and enter text to search for in the entire database. This will redirect to a new page with all of the filtered hotfixes.
<br>
<br>

Date Ascending/Descending - sort the database by either descending or ascending date.
<br>
<br>

Export Data - To export data click the export data button and it will download a JSON file with all of the data in the database. This is used to transfer the application to a new host since the database is hosted on the local machine.
<br>
<br>

Import Data - To import data, ensure that a file named 'exported_data.json' is in the folder that the main application is in. The file must be in JSON format using the format of the exported data. This will skip     duplicates and add the data to the database and redirect to the main data page.
<br>
<br>

Logout - in the top right there is a logout button that will log the user out and return to the login page.
<br>
<br>

Clicking on HMS Request # - clicking on the HMS request # will bring the user to the manage hotfix page where the user can download as a CSV, JSON, or docx file as well as delete and update the hotfix.
<br>
<br>

Clicking on HMS Bug # - clicking on the HMS bug # will bring the user to the HMS homepage where the user can find the hotfix clicked on.
<br>
<br>

Clicking on Azure DevOps Bug # - clicking on the Azure DevOps Bug # will redirect the user to the Azure DevOps page for the bug that was selected.
<br>
<br>

    
Add Hotfix
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  
This page is used to upload a hotfix to the database. To do so, enter all of the fields and if not applicable to the hotfix, then put n/a and click save. This will update the database and redirect the user to the data page.
<br>
<br>
  

Manage Hotfix
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

This page allows the user to edit or delete the hotfix that was selected. The page also allows the user to download the hotfix as a CSV, JSON, or docx file to send to DevOps efficiently.
<br>
<br>
