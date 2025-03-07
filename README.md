# ddr_layout_fields
Helpful script for FileMaker development. It shows you details of the layout in a UNIX style report.

2025-03-08 Prospect KY USA, Brian Ginn — Helpful script for FileMaker development. It shows you details of the layout in a UNIX style report (once added to "Watch" in Data Viewer). See a sample report for the classic template Contacts. It is a standalone script you copy/paste into your solution. Run it and check the "Data Viewer" and add to "Watch" for pretty format. (copy sample below into a text editor with monospacing to see it as it would appear in the real Data Viewer as it's not wide enough here to be clearly read as it otherwise would be.)

A YouTube video is here without sound. https://youtu.be/E5d_2NZSQSA

Sample report in Data Viewer once moved to "Watch" so it can be viewed monospaced:
```
/*
'Add to Watch' for Unix-formatted rpt. Hold shift key while running script to clear globals.
Clear $expert in script setting to hide introductory instructions and helpful information.
@08:51:05

#DB: Contacts
#LN: Contact Details
#TO: Contacts

0 Total Record Count.

19 Regular Fields found on layout.

FieldComment
Addresses::Address Line 1        First line of the address
Addresses::Address Line 2        Second line of the address
Addresses::City                  City of the address
Addresses::Country               Country of the address
Addresses::Postal Code           Postal Code of the address
Addresses::State                 State of the address
Addresses::Type                  Type of the address. Available options are Home and Work
Company                          Company Name of the contact
Email Addresses::Address         The E-mail address
Email Addresses::Type            Type of the E-mail address. Available options are Work and Personal
First Name                       First Name of the contact
Job Title                        Job Title of the contact
Last Name                        Last Name of the contact
Phone Numbers::Number            The phone number
Phone Numbers::Type              Type of the phone number. Available options are Home, Mobile, Work and Fax
Photo                            Photo of the contact
Photo                            Photo of the contact
Title                            Title of the contact. Available options are Mr, Mrs, Ms and Prof
Website                          Website of the company

FieldType
Addresses::Address Line 1        Standard        Text       Unindexed        1
Addresses::Address Line 2        Standard        Text       Unindexed        1
Addresses::City                  Standard        Text       Unindexed        1
Addresses::Country               Standard        Text       Unindexed        1
Addresses::Postal Code           Standard        Number     Unindexed        1
Addresses::State                 Standard        Text       Unindexed        1
Addresses::Type                  Standard        Text       Unindexed        1
Company                          Standard        Text       Indexed          1
Email Addresses::Address         Standard        Text       Unindexed        1
Email Addresses::Type            Standard        Text       Unindexed        1
First Name                       Standard        Text       Unindexed        1
Job Title                        Standard        Text       Indexed          1
Last Name                        Standard        Text       Unindexed        1
Phone Numbers::Number            Standard        Text       Unindexed        1
Phone Numbers::Type              Standard        Text       Unindexed        1
Photo                            Standard        Container  Unindexed        1
Photo                            Standard        Container  Unindexed        1
Title                            Standard        Text       Unindexed        1
Website                          Standard        Text       Unindexed        1

FieldStyle
Addresses::Address Line 1        Standard        
Addresses::Address Line 2        Standard        
Addresses::City                  Standard        
Addresses::Country               Standard        
Addresses::Postal Code           Standard        
Addresses::State                 Standard        
Addresses::Type                  Popupmenu       Address Type
Company                          Popuplist       Company
Email Addresses::Address         Standard        
Email Addresses::Type            Popupmenu       Email Type
First Name                       Standard        
Job Title                        Popuplist       Job Title
Last Name                        Standard        
Phone Numbers::Number            Standard        
Phone Numbers::Type              Popupmenu       Phone Type
Photo                            Standard        
Photo                            Standard        
Title                            Popupmenu       Title
Website                          Standard        

FieldBounds                           l     t     r     b   deg
Addresses::Address Line 1           423   263   841   307     0   418.w    44.h
Addresses::Address Line 2           845   263  1024   307     0   179.w    44.h
Addresses::City                     423   311   589   355     0   166.w    44.h
Addresses::Country                  845   311  1024   355     0   179.w    44.h
Addresses::Postal Code              716   311   841   355     0   125.w    44.h
Addresses::State                    593   311   712   355     0   119.w    44.h
Addresses::Type                     423   215  1024   259     0   601.w    44.h
Company                             402   206   702   250     0   300.w    44.h
Email Addresses::Address            607   215  1024   259     0   417.w    44.h
Email Addresses::Type               423   215   603   259     0   180.w    44.h
First Name                           32   698   359   742     0   327.w    44.h
Job Title                            32   802   359   846     0   327.w    44.h
Last Name                            32   746   359   790     0   327.w    44.h
Phone Numbers::Number               607   215  1024   259     0   417.w    44.h
Phone Numbers::Type                 423   215   603   259     0   180.w    44.h
Photo                                15   116   376   636     0   361.w   520.h
Photo                                15   116   376   636     0   361.w   520.h
Title                                32   650   359   694     0   327.w    44.h
Website                             727   206  1027   250     0   300.w    44.h

Field/Table Occurrence/BaseTableName or Source Table                                   
Address         Email Addresses::  Email Addresses
Address Line 1  Addresses::        Addresses
Address Line 2  Addresses::        Addresses
City            Addresses::        Addresses
Company         Contacts           Contacts
Country         Addresses::        Addresses
First Name      Contacts           Contacts
Job Title       Contacts           Contacts
Last Name       Contacts           Contacts
Number          Phone Numbers::    Phone Numbers
Photo           Contacts           Contacts
Photo           Contacts           Contacts
Postal Code     Addresses::        Addresses
State           Addresses::        Addresses
Title           Contacts           Contacts
Type            Addresses::        Addresses
Type            Email Addresses::  Email Addresses
Type            Phone Numbers::    Phone Numbers
Website         Contacts           Contacts

__________________________________________________________ 
FieldType function from Claris help as of version 19.5.4: 
- The first value is either Standard, StoredCalc, Summary, UnstoredCalc, External(Secure), External(Open), or Global. 
- The second value is the field type: text, number, date, time, timestamp, or container. 
- The third value is Indexed or Unindexed. 
- The fourth value is the maximum number of repetitions defined for the field (if the field isn’t defined as a repeating field, this value is 1). 

FieldStyle function from Claris help as of version 19.5.4: 
If the field has a value list associated with it, the FieldStyle function also returns the name of the value list. 
- standard field returns Standard. 
- standard field with - vertical scroll bar returns Scrolling. 
- drop-down list returns Popuplist. 
- pop-up menu returns Popupmenu. 
- checkbox returns Checkbox. 
- radio button returns RadioButton. 
- drop-down calendar returns Calendar. 

FieldBounds function from Claris help as of version 19.5.4: 
Returns the location, in points, of each field boundary and the field's rotation in degrees. 

How to use: 
 Script is portable without dependencies. Copy into any solution and run. Add shift key when running to clear resulting vars. Clear the $expert var to suppress this extensive help text. It is under settings within the script. My workflow of investigation means I'll look at one to three or four layouts as that is the task at hand. Yes, most can be found in the object inspector but this report is something I wanted in my work life. I can do this within a minute so the $$report[XX] global var uses 60 repetition options, one per second and that is the XX part of the var. It does add simple arithmetic to calc width and height from the FieldBounds function which can help isolate a possible slight misalignment and is kind of fun to see. To see the report clearly (it uses spaces to show columns), in the Data Viewer, "Add to Watch" will move it to the Watch list and there you can open it and view it as intended. There you can use the built-in search too. 
All the best, Brian

Report does not include <<Merge Fields>>.

Script: DDR_Layout_Fields
Set $expert in setting to toggle helper information.
Hold shift key while running script to clear globals.
*/
```
