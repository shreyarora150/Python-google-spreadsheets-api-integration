# Python-google-spreadsheets-api-integration
Integrating google spreadsheet api python to read, write, and modify spreadsheets using pandas library

Requirements:
1. Google drive Api client secret json file
2. googleapiclient (pip install if not already installed)
3. oauth2client
4. apiclient
5. pandas,numpy

Steps to follow:
1. Go to the google api console : https://console.developers.google.com/apis/dashboard
2. Select an existing project or create a new one
3. Click on enable APIs and services if not already enabled
4. search for google drive api and add it to the project
5. Click 'Create credentials' to get started.
6. Choose 'Google Drive API'
7. Select 'Web Server (e.g node.js, Tomcat)' as the platform, choose 'Application Data' in user data preference, and click 'No, I'm not using them.'
8. Name the service account and grant it a Project Role of Editor.
9. Download the json file, rename it to 'client_secret' and copy it to to your code working directrory
   (if you're using spyder as your python IDE the working directory is 'C:\Users\Username\.spyder-py3')
10. Open the JSON file with any text editor and copy the client email, go to your spreadsheet and share the spreadsheet with the client email with edit access


Debugging and errors:
1. define scopes properly, given below is a list of scopes to be used as per your requirement:

  https://www.googleapis.com/auth/spreadsheets.readonly:	Allows read-only access to the user's sheets and their properties.
  
  https://www.googleapis.com/auth/spreadsheets:	Allows read/write access to the user's sheets and their properties.
  
  https://www.googleapis.com/auth/drive.readonly :	Allows read-only access to the user's file metadata and file content.
  
  https://www.googleapis.com/auth/drive.file :	Per-file access to files created or opened by the app.
  
  https://www.googleapis.com/auth/drive :	Full, permissive scope to access all of a user's files.
  
2. While converting the 2d array values into a dataframe list index out of bounds error may occur. This happens due to empty cells in your data range, make sure you replace them with "NA" or "Null".

3. While writing/modifying values in the google spreadsheet make sure the numeric columns are type casted as strings or floats. int32 or int 64 types are not json subscriptable.

P.S Do check out https://developers.google.com/sheets/api/quickstart/python 



