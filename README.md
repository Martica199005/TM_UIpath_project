# TM_UIpath_project

The Uipath.zip contains 2 robots  ReadExcel and CheckAddress.
All the versions of the robot CheckAddress (CheckAddress--vx) until the version 4 included work together with the Read Excel bot which reads only a single kind of Excel.
The robot ReadExcel reads the Excel and add each line to a queue called CheckAddressQueue. Each queue item has the following features:
Address, City, State, Zip, Error_Address, RowNumber

When all the excel rows are added to the queue, the other robot , CheckAddress, can insert each item of the queue to the website ( the URL is in the Config file).
For each queue item inserted in the web site, the robot writes the result founded in the same Excel at the column K which is the Status.

The new version of CheckAddres can be found in the Uipath2.zip:
This zip contains a new ReadExcel bot which is able to read another kind of Excel and CheckAddres can insert all the data in the web sites.

Issue with Uipath: Add Queue Item activity - The operation has timed out


Maybe the solution is downgrading your Uipath.System.Activities package to version 20.4.0, not the latest version. Your add queue item command should work when you do this, provided your workflow is correct. 

For the moment I added queue items with rowNumber<14340

The ReadExcel--v2.zip contains the unified process ReadExcel which is able to read both kind of excel files ( the old one and the new one) . 
It is the dispatcher process which adds the items to the queue "CheckAddressQueue" and the performer process which puts the items in the website is the CheckAddress robot which can be founded in the Uipath2.zip. 
This version of CheckAddress has another difference: in the Config file you can specify the sheet of the excel to write.


In ReadExcel--v2.2.zip I just added a comment for the catch in try catch activity.
In CheckAddress-v5.2 there are custom exception handling ( also for get app credentials) and trim for row_number and house variables.


I made a modification for ReadExcel--v2.2.zip ( still I don't upload it here) to make it run with an unattended robot. I put the assets excel_path and sheet_name.
 Checkaddress_bot.zip is the last version for both the robots for the moment.

Checkaddress_bots_new.zip: new version for readexcel and checkaddress bots which can read another type of excel. Email trigger bot is inside the folder but still don't implemented in ReadExcelv4, Checkaddressv5.4 has commented the email send workflow. I've deleted some of the last version od the bots which aren't used anymore.
 Checkaddressv5.4 doesn't get stuck when the page changes or is closed.
