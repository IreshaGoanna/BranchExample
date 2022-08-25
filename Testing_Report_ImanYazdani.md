# Test case 1 : Creating a musician (Choosing the instrument)

### User requirement being tested
Select whether the musician is a guitarist, bassist, percussionist, or flautist based on the instrument and instrument could be only one of: (1.Guitar,  2.Bass Guitar, 3.Drum or 4.Flute)
Inputs required to test functionality
For this purpose, user must enter the number corresponding  to the instrument to choose the instrument via command line.
### Instruction
Run the application in command prompt: node musoplan.js >> Enter 1 to choose functionality 1.Create a musician >>  choose desired instrument by entering corresponding number
#### Note: if entered value is meets the criteria, entered value will be saved and program proceeds to the next level which is asking the Musician Name. 

## Expected and actual outcome

|Input value    |Expected outcome   |Actual outcome |Status
|-------------|--------------------------------------------------|--------------------------------------------------|
|1	|Please enter Musician Name (Between 3 and 30 characters):	|Please enter Musician Name (Between 3 and 30 characters):  |Correct Input
|5	|Please enter Musician Name (Between 3 and 30 characters):	|Please select Instrument by entering corresponding number  |Incorrect Input
|Guitar	|Please enter Musician Name (Between 3 and 30 characters):	|Please select Instrument by entering corresponding number  |Incorrect Input

## Modifications required (if defect identified)
None.
# Test case 2 : Entering minimum duration of a troupe

## User requirement being tested
Input the minimum duration of a troupe. (Must be between 0.5 and 3 Hours)
Inputs required to test functionality
For this purpose, user must enter the value of minimum duration in hours via command line.
Instruction
Run the application in command prompt: node musoplan.js >> Enter 2 to choose functionality 2.Create a troupe >>  enter a name for the troupe (between 3 and 30 characters) >> enter Minimum Duration
Note: if entered value is meets the criteria, entered value will be saved and program proceeds to the next level which is asking the Musician Name. 

## Expected and actual outcome

|Input value    |Expected outcome   |Actual outcome |Status
|-------------|--------------------------------------------------|--------------------------------------------------|
|1	|Please enter Troupe Genre (Must one of 1."Rock", 2."Jazz", or 3."Pop") Please choose [1 , 2 or 3]:	|Please enter Troupe Genre (Must one of 1."Rock", 2."Jazz", or 3."Pop") Please choose [1 , 2 or 3]:  |Correct Input
|0	|Please enter Troupe Genre (Must one of 1."Rock", 2."Jazz", or 3."Pop") Please choose [1 , 2 or 3]:	|Please enter Minimum Duration (Must be between 0.5 and 3 Hours):  |Incorrect Input
|4	|Please enter Troupe Genre (Must one of 1."Rock", 2."Jazz", or 3."Pop") Please choose [1 , 2 or 3]:	|Please enter Minimum Duration (Must be between 0.5 and 3 Hours):  |Incorrect Input


## Modifications required (if defect identified)

None.

# Test case 3 : Adding a musician to a troupe (selecting the troupe)

## User requirement being tested
Selecting a troupe from the list of previously created troupes shown in the command line by choosing the corresponding number.
## Inputs required to test functionality
For this purpose, user must enter number corresponding to the desired troupe listed in the command line.
## Instruction
Run the application in command prompt: node musoplan.js >> Enter 3 to choose functionality 3.Add a musician to a troupe>>  enter the number allocated to the desired troupe name
#### Note: 
-	if entered value is meets the criteria, entered value will be saved and program proceeds to the next level which is asking the Musician Name. 
-	In this case only 1 troupe was already created in the program: Stars

## Expected and actual outcome

|Input value	|Expected outcome	|Actual outcome |Status
|-------------|--------------------------------------------------|--------------------------------------------------|
|1	|Please enter the number of your chosen instrumentalist according to the list of existing Instrumentalists:	|Please enter the number of your chosen instrumentalist according to the list of existing Instrumentalists:  |Correct Input
|0	|Please enter the number of your chosen instrumentalist according to the list of existing Instrumentalists:	|TypeError: Cannot read properties of undefined (reading 'troupe_name') |Error! 
|Stars	|Please enter the number of your chosen instrumentalist according to the list of existing Instrumentalists:	|Please enter the number of your chosen troupe according to the list of existing Troupes:    |Incorrect Input

 
## Modifications required (if defect identified)

In this case, when user enters 0 the program quits giving below error: </br>

… \musoplan\muso_functions.js:258</br>
            tname = troupeDetails[tchoice-1].troupe_name;</br>
                                             ^</br>
TypeError: Cannot read properties of undefined (reading 'troupe_name') </br>
</br>

## Rectification

“tchoice” holds the value of troupe number. So we can not choose the troupe number 0.</br>
So , below rectification would solve the problem:</br>

if(ichoice > 0 && ichoice <= musicianDetails.length)</br>
</br>

## Expected and actual outcome (After modification)

|Input value	|Expected outcome	|Actual outcome |Status
|-------------|--------------------------------------------------|--------------------------------------------------|
|1	|Please enter the number of your chosen instrumentalist according to the list of existing Instrumentalists:	|Please enter the number of your chosen instrumentalist according to the list of existing Instrumentalists:  |Correct Input
|0	|Please enter the number of your chosen instrumentalist according to the list of existing Instrumentalists:	|Please enter the number of your chosen troupe according to the list of existing Troupes:    |Incorrect Input
|Stars	|Please enter the number of your chosen instrumentalist according to the list of existing Instrumentalists:	|Please enter the number of your chosen troupe according to the list of existing Troupes:    |Incorrect Input
