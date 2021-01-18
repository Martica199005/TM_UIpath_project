# TM_UIpath_project

The Uipath.zip contains 2 robots  ReadExcel and CheckAddress.
All the versions of the robot CheckAddress (CheckAddress--vx) until the version 4 included work together with the Read Excel bot which reads only a single kind of Excel.
The robot ReadExcel reads the Excel and add each line to a queue called CheckAddressQueue. Each queue item has the following features:
Address, City, State, Zip, Error_Address, RowNumber

When all the excel rows are added to the queue, the other robot , CheckAddress, can insert each item of the queue to the website ( the URL is in the Config file).
For each queue item inserted in the web site, the robot writes the result founded in the same Excel at the column K which is the Status.

The version 5 is a new version of the two robots:
ReadExcel is able to read another kind of Excel and CheckAddres can insert all the data in the web sites.

Issue with Uipath: Add Queue Item activity - The operation has timed out
Maybe the solution is downgrading your Uipath.System.Activities package to version 20.4.0, not the latest version. Your add queue item command should work when you do this, provided your workflow is correct. Let me know :slight_smile:



other project:
see https://www.youtube.com/watch?v=-osy_nkpmFc for captha
