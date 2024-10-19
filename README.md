## OBJECTIVE 
In this Robot, data is extracted from Excel and filled in with the crm site automatically in two ways, the first using the idea of the for each and the second using the idea of the variable Data table.
### MANUALLY
1) Extracting employee data from Excel
2) Fill them out on the CRM website and this will require a lot of time and effort
3) Storing the ID of each employee and filling it out on Excel

## TECHNICAL REQUIREMENTS
###  If Activity
   [If Activity](https://docs.uipath.com/studio/standalone/2023.10/user-guide/the-if-activity)
### Using Excel Activities
1) [Excel Process Scope](https://docs.uipath.com/activities/other/latest/productivity/excel-process-scope-x)
2) [Use Excel File](https://docs.uipath.com/activities/other/latest/productivity/excel-application-card)
3) [For Each Excel Row](https://docs.uipath.com/activities/other/latest/productivity/excel-for-each-row)
4) [Insert Column](https://docs.uipath.com/ACTIVITIES/other/latest/productivity/insert-column-x)
   
### Using Data Table Activities

## UI Automation Activities
1) [Use Application/Browser](https://docs.uipath.com/activities/other/latest/ui-automation%22/n-application-card)
2) [Navigate Browser](https://docs.uipath.com/activities/other/latest/ui-automation/n-navigate-browser)
3) [Keyboard Shortcuts](https://docs.uipath.com/activities/other/latest/ui-automation%22/n-keyboard-shortcuts)
4) [Click](https://docs.uipath.com/activities/other/latest/ui-automation%22/click)
5) [Log Message](https://docs.uipath.com/activities/other/latest/workflow/log-message)
6) [Type Into](https://docs.uipath.com/activities/other/latest/ui-automation%22/type-into)
7) [Get Text](https://docs.uipath.com/activities/other/latest/ui-automation%22/n-get-text)
8) [Message Box](https://docs.uipath.com/activities/other/latest/workflow/message-box)

# First Bot 
## PROCEDURES

1) Excel Process Scope > Use Excel File, inside the Excel file put the extention
   
   <img src="https://github.com/user-attachments/assets/16dc183a-3d72-4633-b5b3-d14b33f1ed18" width="400">
   
2) Use Insert Column to add an "ID Number" column to employee data sheet
   
   ![image](https://github.com/user-attachments/assets/e1bb0be0-74a9-41a7-966b-9b7391109eb3)

3) For Each Excel Row > Use Browser Chrome: CRM

 
   <img src="https://github.com/user-attachments/assets/7ff7a72e-29e0-4606-a99e-09043814b1eb" width="400">

 4) In the properties panel change the input mode to Simulate(The fastest), and Resize window (Max)

    
    ![image](https://github.com/user-attachments/assets/359fd0e1-86cb-4bd8-842e-b3a526805e39)

 5) Put Type into and change click befor typing to none

    ![image](https://github.com/user-attachments/assets/eeb76e8b-47c4-49b8-8397-4c6cae9c7904)

    
 6) The best practise for  (either or Fields) is to choose If Activity
    -condition:CurrentRow.ByField("gender")="Female"

    ![image](https://github.com/user-attachments/assets/05c8892b-2b7e-4483-a003-073268080705)

 7)Select item (For multiple choice fields/ drop down menue): inside item to select CurrentRow.ByField("state")
 
 8) Navigate Browser - Refresh (To avoid interference of personnel information during its extraction)
 9) Write Cell activity, With attention, you must put it within the scope of the for to avoid repetition of the information.
     
     ![image](https://github.com/user-attachments/assets/e6fa2580-4e95-49b5-a0d2-fcb980354e19)
    
    
# Second Bot 
## PROCEDURES

1) The difference from the first robot is using Read Range activty which store data in Data table format.
2) Single Excel Process Scope > Use Excel File > Read Range (dt_info)
3) For Each Row in Data Table (dt_info) > Use Browser Firefox: CRM > Navigate Browser - Refresh > Type Into > Select Item

   
<img src="https://github.com/user-attachments/assets/1da7db1c-f87b-4404-8f20-3eb6748292b9" width="400">
 


.
<img src="https://github.com/user-attachments/assets/2472c6b5-1121-4499-9abc-1c1bf0614226" width="400">


.
<img src="https://github.com/user-attachments/assets/b1fe1718-6e41-4306-90d5-5a0845936d8c" width="400">


.
<img src="https://github.com/user-attachments/assets/8e382bef-7792-4c90-b1d9-f12bcec986d3" width="400">


4) If Activity: CurrentRow(2).ToString.Contains("Male")

   
<img src="https://github.com/user-attachments/assets/6fb16599-bbea-471b-a75c-ad19845a3f84" width="400">


6) Get Text 'Customer ID' > Message Box

   
<img src="https://github.com/user-attachments/assets/2b6c402b-342b-4458-bdb4-c6781c0ea81a" width="400">
   



    
## Results
To watch the First Bot run this video, [click here](https://drive.google.com/file/d/13OePogfspo3yjXKYVSjQ00JYrhz_Cnfu/view?usp=drive_link)
 





## CONCLUSION
