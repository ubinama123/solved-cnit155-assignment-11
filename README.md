Download Link: https://assignmentchef.com/product/solved-cnit155-assignment-11
<br>
<strong>Objectives: </strong>

<ul>

 <li>Checkbox control</li>

 <li>Saving to the text file</li>

 <li>Reading from a text file</li>

 <li>Form Closing Event Method</li>

 <li>Form_Load event method</li>

</ul>

<strong> </strong>

<strong>Problem Description:</strong>  Design a C# project to store up to 100 students’ information in parallel arrays. The user will enter each student’s name, score in provided Textboxes and check the Checkbox if student is a CIT major, followed by a click on the Enter button to store the student in the parallel arrays.







Figure 1 – Screen capture when Display is clicked

<strong>Class Scope Declarations:</strong>

<ul>

 <li>Declare a named constant to store size of the parallel arrays = 100.</li>

 <li>Declare 3 parallel arrays to store up to 100 students’ names, scores and CIT major (true / false). Use the named constant at declaration.</li>

 <li>Declare a counter to keep track of the next available index in the array.</li>

 <li>Declare a variable to store <em>the file name</em> with the full path:</li>

</ul>

Private String mFileName = Path.Combine (Application.StartupPath , “Students.txt”);

<strong> </strong>

<strong> Enter Button (pseudo-code)</strong>

<strong> </strong>

<ul>

 <li>Validate the user’s input – Call the helper method.</li>

 <li>If data is not valid – return.</li>

 <li>Store the entered data in parallel arrays.

  <ul>

   <li>If the check box is checked, store <em>true</em> in the array, otherwise store <em>false</em>.</li>

  </ul></li>

 <li>If array is full

  <ul>

   <li>Inform the user</li>

   <li>Disable the Enter button.</li>

  </ul></li>

 <li>Call the helper method to clear the input.</li>

</ul>




<strong>     Display Button:</strong>

<ul>

 <li>Inform the user if array is empty, and return.</li>

 <li>Display all the names, scores and CIT major (true / false) in the Listbox.</li>

</ul>

<strong>       </strong>

<strong>      Stats Button:</strong>

<ul>

 <li>Inform the user if array is empty, and return.</li>

 <li>Clear the Listbox</li>

 <li>Display number of students entered.</li>

 <li>Display number of CIT students entered.</li>

 <li>Compute the average. Display it with proper format.</li>

</ul>

<strong> </strong>

<strong>       Clear Button:</strong>

<ul>

 <li>Call ClearInput() to clear the entered input.</li>

 <li>Clear the Listbox.</li>

</ul>

<strong> </strong>

<strong>Exit Button</strong>: End program execution.




<strong>FormClosing Event:</strong>

Save data stored in parallel arrays to a text file named students.txt, one student per line, with tab delimited fields. Refer to Figure-3.

<ul>

 <li>Declare an object variable of type StreamWriter.</li>

 <li>Open the file <em>txt</em> at the same location as your project’s .exe</li>

 <li>Write a loop to write each student’s data on a separate line, tab delimited.</li>

 <li>Close the file.</li>

</ul>




<strong>Helper Methods:</strong>

<strong> </strong>

<ul>

 <li><strong>ValidateInput(): </strong>

  <ol>

   <li>Input: none</li>

   <li>Output data type: bool</li>

   <li>Task: Validate user’s input based on the following rules:</li>

  </ol></li>

</ul>

– Existence check on name.

– Score must be a whole number.

– Valid range for score is 0 to 100, both inclusive.




<ul>

 <li><strong>ClearInput ( )</strong>

  <ol>

   <li>Input: none</li>

   <li>Output: void</li>

   <li>Task: Clear the entered data and set the focus to the top textbox.</li>

  </ol></li>

</ul>

Call this method at the end of the Enter button and from the Clear button.

<strong><em> </em></strong>

<ul>

 <li><strong>DisplayMessage( )</strong></li>

</ul>

<ol>

 <li>Input: String</li>

 <li>Output data type: void</li>

 <li>Task: Display the input string using MessageBox.Show(). The Messagebox should include all 4 arguments.<strong>                                   </strong></li>

</ol>

<strong> </strong>

<strong> </strong>

<strong>FormClosing Event Method</strong>

<em>     Save content of the parallel arrays to the text file in this event procedure.</em>

<em> </em>

<ul>

 <li>Confirm with the user whether to end the program execution or not.

  <ul>

   <li>Use MessageBox.Show to ask this question. Provide buttons Yes and No in the Messagebox plus the Question icon.</li>

   <li>If the user’s answer is NO,

    <ul>

     <li>Cancel the closing event.</li>

     <li></li>

    </ul></li>

   <li>Save data stored in parallel arrays to a text file.

    <ul>

     <li>Declare an object variable of <em>StreamWriter</em> Open the file (use class scope filename) to write to.</li>

     <li>Write a loop to write each student’s data to the file in a tab delimited format.</li>

     <li>Close the file.</li>

    </ul></li>

   <li>Include Exception Handling code to handle exceptions (try – catch – finally).</li>

  </ul></li>

</ul>










Figure 22 – An image of the text file

<strong>         </strong>

<strong>Form_Load Event Method   </strong>




<em>Upload / read data from a text file into the program in parallel arrays in this event method.</em>

<ul>

 <li>Check if the file exists (Use the class scope filename).

  <ul>

   <li>If file does not exist, return.</li>

  </ul></li>

 <li>Declare an Object variable of <em>StreamReader </em>class and open the file <em>mFilename</em> for reading.</li>

 <li>Declare a string variable to store a line read from the file.</li>

 <li>Write a loop to read until end of the file.

  <ul>

   <li>Read a line into the string variable.</li>

   <li>Split the line to extract pieces of data.</li>

   <li>Store pieces of data in parallel arrays at <em>mIndex</em>. –</li>

  </ul></li>

 <li>Close the file.</li>

 <li>Include Exception Handling code to handle exceptions (try – catch – finally).</li>

</ul>