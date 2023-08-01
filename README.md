# Build/Sign Request Database
Website to store build and sign requests using MongoDB and Node.js.
<br>
<br>


# SETUP

To get the application setup on a VM follow the steps below:
1. Navigate to \\\usaust-file6\HawkTransfer\MPeterka and download hotfix.zip and install both ChromeSetup.exe (to access localhost:3000), node-v18.16.1-x64 (Node.js) and mongodb-windows-x86_64-6.0.8-signed.msi (MongoDB). These will be used to get the app running and on the localhost browser. There is no need to change any settings on the downloads either.
2. Once all of the files are downloaded, open the hotfix.zip and move the folder inside to the desktop. This is where the javascript application is.
3. Start a new terminal in the directory of the file just moved to the desktop.
4. Before running any command, go into the main folder of the app and open the service.js file. Edit the script path to be the path where the index.js file is located (the same route as the service.js file)
5. In the terminal type in 'node service.js' making sure that the path of the terminal is in the main part of the folder where service.js is located. This should be the same location as the file from hotfix.zip. This javascript file is used to create a Windows service that will keep the app running whenever the VM is on. Whenever this is typed in it may output information or it may not.
6. Next, open task manager and click more details, and then Services on the top. Find a service called 'hotfixdatabase.exe'. If the status is running then nothing needs to be done, if it says stopped then right-click and select start. Once the status stays on running the initial setup is complete.
7. To ensure the app is working correctly, navigate to the folder where the application is and open the file named daemon. In the daemon directory find the hotfix.database.out.log and open it. The text in the file should read: <br><br>
App is listening on localhost:3000 <br>
Database connected 127.0.0.1 <br> <br>

8. Open Chrome and navigate to localhost:3000, this is where the homepage will be.
<br>
--If for any reason the app crashes, to reset the app repeat steps 4 and 5.
<br>
<br>
--To connect to the VM instance of the app simply put in the IP address of the VM and add port:3000 in Google Chrome and it will load up the app on the VM on any machine.
<br>
<br>
--If the website is updated to use HTTPS and needs the LDAPJS authentication feature, simply go to main.js located in /server/routes and find the router.get('') and the router.post('/logout') functions and comment/uncomment out the correct code.
This should only be done if the website is using HTTPS since the username and password are not secure over http.
<br>
<br>


# TROUBLESHOOTING

Error: MongooseServerSelectionError: Invalid message size: 1347703880, max allowed: 67108864 <br><br>
--This error occurs due to the MongoDB msi file not being installed. Install and try again. <br><br>

Error: exception in initAndListen: NonExistentPath: Data directory C:\data\db\ not found. Create the missing directory or specify another path using (1) the --dbpath command line option, or (2) by adding the ‘storage.dbPath’ option in the configuration file., terminating <br><br>
--This is due to there not being a folder for the data to be stored. To fix this error simply go to the C: drive and create a new folder 'data'. In this folder add another new folder 'db'. Once complete, try again. <br><br>

Error: Going to localhost:3000 the app isn't running <br><br>
--To fix this error first ensure that the app is running as a Windows service. Go to the task manager and click on services and check for 'hotfixdatabase.exe' and see if it is running, if it isn't then right-click and start it. If this doesn't fix the issue then go to the project folder and open the daemon folder and read the 'hotfixdatabase.err.log' file to see what the error is. <br>
--Another reason it may not be working is if there is already a service with that name. If that is the case simply go into the service.js file and change the name to something else and retry it.
<br><br>

Error: 10.223.78.60 redirected you too many times.
--To fix this inspect the element and go to the application. In the cookies section add a new cookie named 'authenticated' and set the value to true. Then search for the IP address and '/hotfixes' and it should be functional.
<br><br>


# HOW TO USE
  
  
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

