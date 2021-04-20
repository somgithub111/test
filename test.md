
<h2 align="center">OBJECTIVE OF THE ASSIGNMENT</h2> 

 To make a Script to download the Previously created two Evaluation reports in CSV file through link and Extract the data to dispaly only below points from both:-  
 1. Intern Name: _____
 2. Sum    : _______
 3. Average:______

----

<h2 align="center">TEST CASES</h2> 

|Test Cases|Test Case Description|Steps Performed| Test Status|Output
|:----:|:-----:|:-----:|:-----:|:-----:|
|Test Case 1| **WEB PUBLISHING** <br/> Publish the Spreadsheet's link to web with CSV output | A Copy of Spreadsheet's link has been published to web using *Publish to web* option from **File menu** of spreadsheet opting the CSV mode | PASS |![](https://raw.githubusercontent.com/somgithub111/test/master/Screenshot%20from%202021-04-19%2023-55-40.png) <br/> Client/Approver's Signature _______ |
|Test Case 2| **DECLARING PATHS IN VARIABLES** <br/> Path of the commands are stored in variables so that it can be called using $var_name when required| MKDIR=/usr/bin/mkdir <br/> RENAME=/usr/bin/mv <br/> ECHO=/usr/bin/echo <br/> SHOW=/usr/bin/cat <br/> DOWNLOAD=/usr/bin/wget <br/><br/> **Note: Do not use root user to operate**| PASS | ![](https://raw.githubusercontent.com/somgithub111/test/master/Screenshot%20from%202021-04-20%2009-19-11.png) <br/> Client/Approver's Signature _______ |
|Test Case 3| **DOWNLOAD THE LINK SILENTLY** <br/> _wget_ Command is a non-interactive network downloader| Using $wget to call _wget_ from stored path in variable and to download quietly we have used _$wget -q_ (now downloading process is quietly running as hidden mode) | PASS | ![](https://raw.githubusercontent.com/somgithub111/test/master/Screenshot%20from%202021-04-20%2010-00-26.png) <br/> Client/Approver's Signature _______ |
|Test Case 4| **RENAME CSV FILE AND STORE** <br/> Downloaded file via _Test case 3_ is now renamed to Evaluation_of_sheet1 and Evaluation_of_sheet2 stored directly to Evaluation_DIR created by the script to your operating location.| $RENAME is used to call the *mv* command from it's path and renaming and storing the output file to newly created directory. Output can be visible as shown in the image at the Right-End |PASS|![](https://raw.githubusercontent.com/somgithub111/test/master/Screenshot%20from%202021-04-20%2010-09-57.png) <br/> Client/Approver's Signature _______ | 

------

<h2 align="center">IMPLEMENTATION RULES USED </h2> 

 
<p align="center"> <a href="https://exceljet.net/excel-functions/excel-sum-function"><img align="center" alt="GitHub" src="https://img.shields.io/badge/=Sum()%20-%23121011.svg?&style=for-the-badge&logo=github&logoColor=white"/></a></p>
<p align="center"> <a href="https://exceljet.net/excel-functions/excel-counta-function"><img align="center" alt="GitHub" src="https://img.shields.io/badge/CountA(range)%20-%23121011.svg?&style=for-the-badge&logo=github&logoColor=white"/></a></p>
<p align="center"> <a href="https://www.ablebits.com/office-addins-blog/2015/02/25/array-formulas-functions-excel/"><img align="center" alt="GitHub" src="https://img.shields.io/badge/Array_Functions%20-%23121011.svg?&style=for-the-badge&logo=github&logoColor=white"/></a></p>
<p align="center"> <a href="https://exceljet.net/excel-functions/excel-countif-function"><img align="center" alt="GitHub" src="https://img.shields.io/badge/Countif(range,values)%20-%23121011.svg?&style=for-the-badge&logo=github&logoColor=white"/></a></p>

------

<h2 align="center">EXPLANATION OF IMPLEMENTATION</h2> 
<details close="close">
   <summary><b>Functionality in the Drop Down:-</b></summary>
<ul><br/>

 1. COUNTIF(range, value) Function with wildcard Character(*) is used to store values of assumed variables starting from Excellent=5.....upto Poor=0. Functions used on the First cell of average i.e, K4
  
  <b>
  
```sh
  COUNTIF(C4:J4,{"Excellent","Very good","Good","Satisfactory","Fair","Poor"})*{5,4,3,2,1,0})
  ```
  </b> <br/>
  
2. =SUM(values) function is used to Further count the Encounters of COUNTIF function to generate summation output

<b>
  
 ```sh
 (SUM(COUNTIF(C4:J4,{"Excellent","Very good","Good","Satisfactory","Fair","Poor"})*{5,4,3,2,1,0}))
  ```
  
  </b><br/>
  
3. Summation is further divided with COUNTA(range) which stores the count of cell in the selected range. This Formula is applied to generate the average.The output of COUNTA for the selected range in my assignment is 8 </b>

 <b> 
  
   ```sh
 (SUM(COUNTIF(Range, values)/COUNTA(C4:J4)
  ```
</b><br/>

4. Array Function is used to store the numerica values into their respective variables seperately. This Function is generally applied using CTRL+SHIFT+ENTER to save and exit the Editor.

 <b>
  
   ```sh
=ArrayFormula(SUM(COUNTIF(C4:J4,{"Excellent","Very good","Good","Satisfactory","Fair","Poor"})*{5,4,3,2,1,0}))/COUNTA(C4:J4)
  ```
 </b><br/>
 
5. For Bonus Task,I have used Conditional Formatting by selecting the range A4:K24 and select custom function on K with $ to lock the column reference as mentioned below along with red colour option to colour the rows whose value is less than 2.5 in column K:

  <b>
  
```sh
 =$K4<2.5      
  ```
</b></ul>
</details>

 -----
 
 <h2 align="center">TEST RESULTS</h2> 
 
 The Test Results were successful as output for any change in live Entry of any cell will further calculate the correct output and Conditional formatting for displaying the row with RED colour is also working with real time.
 
 ----
 
 
 <h2 align="center">CONCLUSION</h2> 

 I have researched on google to Explore different Ideas, functions and Formulas through which i have gained the calculated Idea to complete this task.I have also observed multiple methods of other Interns assigned with this task and observed the other possible ways through which this task has been completed.
 
 ----
 <br/>
 <br/>
 <b>Link of the Spreadsheet:</b> 
 <p align="left"><a href="https://docs.google.com/spreadsheets/d/1Meany3O0o46ljwN4PBSlDvy0NW9g95EqivOz28xYg9Q/edit?ts=6075dc15#gid=0"> <img src="https://www.picgifs.com/graphics/c/click-here/graphics-click-here-851444.gif" border="0" /></a> <a href="https://github.com/somgithub111/keenable/blob/main/MyPassion.md"><My Passion and Hobby/></a></p>

Feel Free to Drop any Suggestions/Upgradations regarding this markdown on below mail-
<p align="center">
  <a href="mailto:someshkmr4@gmail.com"><img src="https://img.icons8.com/color/96/000000/gmail.png" alt="email"/></a>

 
 
 
 
 
 

