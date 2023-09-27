<h2>Description:</h2>


In this project phase, I will establish a tailored log configuration within our log analytics workspace, facilitating the integration of geospatial data into our analytical framework. To accomplish this, I will employ the "failed_rdp.log" format, training our log analytics system to effectively identify and interpret the relevant information. Then, we will create a custom extract field from the raw custom log data. Finally, we will add a world map to display the attackers. 

- Create a custom log in Log Analytics Workspace to extract our custom log


<h2></h2>

<h2>Creating Custom Log in L-A-W</h2>

1. In our VM, copy all contents on failed_rdp - Notepad   
    - Go back to our desktop > create a Notepad document, and paste all content there
    - Save it, name: failed_rdp.log


2. In our own Desktop, [Azure Portal](https://portal.azure.com/?quickstart=true#home) search bar, search: Log Analytic workspaces

3. Click on law-honeypot > Click on "Tables" underneath the settings 

<p align="left">
Navigation to Create Custom Logs<br/>
<img src="https://i.imgur.com/i1ovqHo.png" height="35%" width="35%" alt=""/>
<br />

3. Click Create> New custom log (MMA-based)

<p align="left">
Create Custom Log<br/>
<img src="https://i.imgur.com/nO0EAOA.png" height="35%" width="35%" alt=""/>
<br />

4. Click the Select file and use failed_rdp.log > Next > Next

<p align="left">
Selecting the File<br/>
<img src="https://i.imgur.com/uwhni7B.png" height="35%" width="35%" alt=""/>
<br />

5. In Collection paths:
    - Type: Windows
    - Path: C:\ProgramData\failed_rdp.log

<p align="left">
Collection Paths<br/>
<img src="https://i.imgur.com/vLU4VUE.png" height="35%" width="35%" alt=""/>
<br />

6. Details: > Create
    - Custom log name: FAILED_RDP_WITH_GEO

<p align="left">
Create Custom Log Overview<br/>
<img src="https://i.imgur.com/8uLFE07.png" height="35%" width="35%" alt=""/>
<br />

7. Test Logs:
    - Go to Logs in Log Analytics Workspace
    - Type in: SecurityEvent | where EventID == 4625 > Run
    - Result will give all the failed attempts login for our honeypot

<p align="left">
Testing Logs<br/>
<img src="https://i.imgur.com/bifwot2.png" height="35%" width="35%" alt=""/>
<br />

8. Wait until you can run FAILED_RDP_WITH_GEO_CL in Logs

<p align="left">
Wait For Logs<br/>
<img src="https://i.imgur.com/zR952Cl.png" height="35%" width="35%" alt=""/>
<br />   

9. After 15 minutes, and the FAILED_RDP_WITH_GEO_CL runs, apply this whole code and run it:


```
FAILED_RDP_WITH_GEO_CL
| extend username = extract(@"username:([^,]+)", 1, RawData),
         timestamp = extract(@"timestamp:([^,]+)", 1, RawData),
         latitude = extract(@"latitude:([^,]+)", 1, RawData),
         longitude = extract(@"longitude:([^,]+)", 1, RawData),
         sourcehost = extract(@"sourcehost:([^,]+)", 1, RawData),
         state = extract(@"state:([^,]+)", 1, RawData),
         label = extract(@"label:([^,]+)", 1, RawData),
         destination = extract(@"destinationhost:([^,]+)", 1, RawData),
         country = extract(@"country:([^,]+)", 1, RawData)
| where destination != "samplehost"
| where sourcehost != ""
| summarize event_count=count() by latitude, longitude, sourcehost, label, destination, country
```

<p align="left">
Running Code for Custom Extract Field<br/>
<img src="https://i.imgur.com/8QxAulK.png" height="35%" width="35%" alt=""/>
<br />   

<h2></h2>

<h2>Creating a World Map</h2>

1. In our own Desktop, [Azure Portal](https://portal.azure.com/?quickstart=true#home) search bar, search: Sentinel

2. Go to Workbooks under Threat Management > Add Workbook > Edit > remove everything

3. Add query and post the same Code above > run query

4. Change:
    - Visualization: Map
    - Size: Full
    - Metric Setting on the right: Label

5. Save > name: Failed RDP World Map

6. Created our Failed RDP World Map

<p align="left">
Successfully Created Failed RDP World Map <br/>
<img src="https://i.imgur.com/KmeSLti.png" height="35%" width="35%" alt=""/>
<br />   
