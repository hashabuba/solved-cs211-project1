Download Link: https://assignmentchef.com/product/solved-cs211-project1
<br>
Write <strong>a C program (not a C++ program!)</strong> that will contain the following:

<ul>

 <li>Write a function that will make a copy the values from one array to another array. Suggested prototype:</li>

</ul>

void makeArrayCopy (int fromArray[], int toArray[], int size);

<ul>

 <li>Write your own function that will sort an array in ascending order. You may use whatever sorting algorithm you wish.  Suggested prototype:</li>

</ul>

void myFavorateSort (int arr[], int size);




<ul>

 <li>Write your own function that will perform a linear search on the unsorted array. <strong>The function is to “return” two values.</strong>  The first should be the position in the array where the value was found or -1 if the value was not found.  The second is the number of comparisons needed to determine if/where the value is located in the array.   Suggested prototype:</li>

</ul>

int linSearch (int arr[], int size, int target, int* numComparisons);




<ul>

 <li>Write your own function that will perform a binary search on the sorted array. <strong>The function is to “return” two values.</strong>  The first should be the position in the array where the value was found or -1 if the value was not found.  The second is the number of comparisons needed to determine if/where the value is located in the array.  Suggested prototype:</li>

</ul>

int binSearch (int arr[], int size, int target, int* numComparisons);




Inside of main:

<ul>

 <li>read in integer input from <strong>standard input</strong> and store these values into a dynamic array. This array is to grow in size if the array is full.  The values will have a “terminal value” of -999.  So you read in these values in a loop that stops when the value of -999 is read in.  The use of informative prompts is required for full credit.  You may not assume how many numeric values are given on each line, nor the total number of values contained in the input.  <strong>The use of a scanf() with the following form is expected</strong> to read in the values:</li>

</ul>

scanf (“%d”, &amp;val);




<ul>

 <li>make a copy of the integer array using the arrayCopy() function described above</li>

</ul>




<ul>

 <li>sort one of the arrays (using the myFavoriteSort() function described above), leave the other array unsorted</li>

</ul>




Inside of main (continued):

<ul>

 <li>read in integer input from standard input (again, the use of scanf() is expected) and for each of the values read in search for the value using both search functions described above (i.e. for each value read in, perform a linear search on the unsorted array and perform a binary search on the sorted array). Using the information returned/sent back from the search functions, <strong>print out from main():</strong></li>

</ul>




<ol>

 <li>The value being searched for and the type of search being preformed.</li>

 <li>Whether the value was found or not found,</li>

 <li>The number of comparisons needed to determine whether the value exists or not in each algorithm,</li>

 <li>And the location in the array where the number is located (if the value does exist in the array).</li>

</ol>




<strong>The above information MAY NOT be printed out in the linear search or binary search functions.  Those functions MUST RETURN/SEND BACK the information to be printed by the main function.  Not doing this will SEVERELY LOWER your score on this project. </strong>




Repeat reading in integer values and searching the arrays until the terminal value of -999 is read in.  The use of informative prompts AND descriptive result output is required for full credit.  Again, scanf() is expected to read the input.

<strong> </strong>

You may not assume the input will be less than any set size.  Thus you will need to dynamically allocated space for the array.




<h1>Dynamic Array Allocation</h1>




Dynamic Array Allocation allows the space in an array to change during the course of the execution of a program.  In C, this requires the use of the malloc() function.  To dynamically allocate space for 100 integers, the malloc() code would be as follows:




int *darr;

int allocated = 100;

darr = (int *) malloc (allocated * sizeof(int) );




This array can only hold 100 integers and it not really dynamic.  To make it truly dynamic, we need to grow the array when we try to put more values into it than can be held by its current size.  The following code will double the size of the array.




int *temp = darr;

darr = (int *) malloc ( allocated * 2 * sizeof(int) );

int i;

for ( i = 0 ; i &lt; allocated ; i++)

darr[i] = temp[i];        free (temp);

allocated = allocated * 2;




<strong>             </strong>

<strong>Running your C Program (not a C++ program) </strong>

<strong> </strong>

<strong>Make sure your program runs properly when compiled using gcc on the bert.cs.uic.edu machine!</strong>  (Do not use g++ or any other C++ compiler with this program.)




<h1>Programming Style</h1>

Make sure your program is written in good programming style.  This includes but is not limited to:

<ul>

 <li>In-line commenting</li>

 <li>Function header commenting</li>

 <li>File header commenting</li>

 <li>Meaningful and description variable names</li>

 <li>Proper use of indentation</li>

 <li>Proper use of blank lines</li>

 <li>Use of Functions</li>

</ul>




<h1>Program Submission</h1>

You are to submit the program via the proper Assignments link in Blackboard. If you create your program in multiple files (<strong>which you should not need to do for this project</strong>), you should create a zip file containing all your files and then submit the zip file on blackboard. You should name your files with your net-id and project name. For example if your net-id is ptroy1, then:




The file should be named as ptroy1proj1.c

The zip file (<strong>if needed</strong>) should be named as ptroy1proj1.zip




<h1>Creating a zip file (if needed)</h1>

<ol>

 <li>Go the directory in which you have saved the files.</li>

 <li>Select the multiple files and right click.</li>

 <li>There should be a menu option to create a zip file. In case of Mac/Linux you will see a menu option <strong>… </strong>In case of Windows you might need to install winzip to create a zip file</li>

</ol>

<strong> </strong>

<h1>Suggestion: Using Redirection of Input and Output to help Test Your Program</h1>




To help test your program, the use of redirection of standard input from a text file is a good idea for this project.   Redirection is done at the command line using the less than and greater than signs.   Redirection of both input and output can be done; however, for this project, you may only want to use redirection of input.




<ul>

 <li>Assume you have a text file that is properly formatted to contain the input as someone would type it in for the input called:<strong>txt</strong></li>

 <li>Also the executable for this project is in a file in the current directory called: <strong>out</strong></li>

 <li>To run the project so that it reads the input from this text file instead of standard input using redirection of input, you would type the following on command line: <strong>./a.out &lt; proj1input.txt </strong></li>

</ul>




<ul>

 <li>To store the output sent to standard output to a file called <strong>txt</strong> using redirection (the input is still being read from standard input), type:</li>

</ul>

<strong>                        ./a.out &gt; outfile.txt </strong>




<ul>

 <li>To redirect both standard input and standard output , type:</li>

</ul>

<h1>                        ./a.out &lt; proj1input.txt  &gt; outfile.txt</h1>




<strong>Note that the code inside of your program will still read from standard input.</strong>  Redirection is information given to the Operating System at the command prompt.  The Operating System then “redirects” a standard input read operation away from the keyboard and to the specified file while the program is running.