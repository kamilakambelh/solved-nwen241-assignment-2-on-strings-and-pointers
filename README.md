Download Link: https://assignmentchef.com/product/solved-nwen241-assignment-2-on-strings-and-pointers
<br>
In this assignment, you will be given 11 tasks where you will apply your knowledge about strings and pointers.

The assignment is divided into 3 parts. In Part I (Tasks 1–5), you will be asked to answer questions about pointers. In Part II (Tasks 6–8) and Part III (Tasks 9–11), you continue the implementation several basic text editor operations. You will implement some of the operations in pure C (Part II), and some in C++ (Part III).

You only need to submit the required implementations. You do not need to write a main() function, but you would need one if you want to test your code. <strong>Sample code showing an example on how you can test your code are provided under the files directory in the archive that contains this file.</strong>

<strong>Coding Style for Parts II and III</strong>

Coding style (also known as coding standard) refers to the use of appropriate indentation, proper placement of braces, proper formatting of control constructs, etc. Following a particular coding style consistently will make your source code more readable.

There are many coding standards available (search “C/C++ coding style”). Most of these standards are dense and will take you many days (even weeks) to read and understand. If you want to follow a <em>lightweight </em>coding style, consult the Linux kernel coding style (<a href="https://www.kernel.org/doc/html/v4.10/process/coding-style.html">https://www.kernel. </a><a href="https://www.kernel.org/doc/html/v4.10/process/coding-style.html">org/doc/html/v4.10/process/coding-style.html</a><a href="https://www.kernel.org/doc/html/v4.10/process/coding-style.html">)</a>. You only need to read sections 1–3 of this document.

Note that you do not have to follow every recommendation you can find in a coding style document. If you change, for instance the tab size from 8 to 4, that is fine. You just have to apply that style consistently.

<strong>Part I: Pointer Concepts</strong>

This part will test your conceptual knowledge of pointers. Your answers should be submitted in a plain text file named part1.txt.

<strong>Task 1.</strong>

<strong>Basics </strong>

<ol>

 <li><strong> </strong>Declare a pointer to a floating-point quantity.</li>

 <li><strong> </strong>Declare a prototype for a function func1 that accepts two integer arguments and returns a pointer to a long integer.</li>

 <li><strong> </strong>Declare a prototype for a function func2 that accepts a character pointer argument and returns a pointer to a character. The function must not allow the modification of the input argument.</li>

 <li>Declare a one-dimensional array of integer pointers with 20 elements.</li>

 <li>Declare an array of C strings whose initial values are “cyan”, “magenta”, “yellow”, and “black”.</li>

</ol>

<strong>Task 2.</strong>

<strong>Completion </strong>

A C/C++ program contains the following statements:

<ul>

 <li><strong>char </strong>u, v = ‘A’;</li>

 <li><strong>char </strong>*pu, *pv = &amp;v;</li>

</ul>

3

<ul>

 <li>*pv = v + 1;</li>

 <li>u = *pv + 1;</li>

 <li>pu = &amp;u;</li>

</ul>

Each character occupies 1 byte of memory. If the value assigned to u is stored in (decimal) address 1100 and the value assigned to v is stored in (decimal) address 1101, then

<ol>

 <li><strong>(1 Mark) </strong>What is the numeric value of the expression &amp;u?</li>

 <li><strong>(1 Mark) </strong>What is the numeric value of the expression &amp;v?</li>

 <li><strong>(1 Mark) </strong>What value is assigned to pv after the completion of line 2?</li>

 <li><strong>(1 Mark) </strong>What is the numeric value of the expression *pv after the completion of line 4?</li>

 <li><strong>(1 Mark) </strong>What value is assigned to u after the completion of line 5?</li>

</ol>

<strong>Task 3.</strong>

<strong>Completion </strong>

Consider the following C++ code snippet:

<strong>int </strong>int1 = 26; <strong>int </strong>int2 = 45; <strong>int </strong>*int1Ptr = &amp;int1; <strong>int </strong>*int2Ptr = &amp;int2; *int1Ptr = 89; *int2Ptr = 62; int1Ptr = int2Ptr; *int1Ptr = 80; int1 = 57;

std::cout &lt;&lt; int1 &lt;&lt; ”           ” &lt;&lt; int2 &lt;&lt; endl; std::cout &lt;&lt; *int1Ptr &lt;&lt; ”   ” &lt;&lt; *int2Ptr &lt;&lt; endl;

<ol>

 <li><strong>(1 Mark) </strong>What is its output?</li>

 <li><strong>(4 Marks </strong>Explain individually the printed values.</li>

</ol>

<strong>Task 4.</strong>

<strong>Challenge </strong>

A C/C++ program has the following statements:

<strong>short </strong>a[] = {1, 2, 4, 8, 16, 32}; <strong>short </strong>*pa = a; <strong>short </strong>**ppa = &amp;pa;

Suppose each short integer quantity occupies 2 bytes of memory. If the array a is at (decimal) address 1102, pa is at (decimal) address 1114, and ppa is at (decimal) address 1118, then

<ol>

 <li><strong>(1 Mark) </strong>What is the numeric value of the expression a?</li>

 <li><strong>(1 Mark) </strong>What is the numeric value of the expression ppa?</li>

 <li><strong>(1 Mark) </strong>What is the numeric value of the expression *ppa + 2?</li>

</ol>

<strong>Task 5.</strong>

<strong>Challenge </strong>

Consider the following C++ code snippet:

std::string seasons[4] = {“Winter”, “Spring”, “Summer”,

“Fall”}; std::string *strPtr; strPtr = new string[5]; <strong>for </strong>(<strong>int </strong>i = 0; i &lt; 4; i++) strPtr[i] = seasons[i];

<ol>

 <li><strong> </strong>Write a C++ code snippet that outputs the contents of the array to which strPtr points using pointer notation.</li>

 <li><strong> </strong>Write a C++ code snippet that deallocates the memory space occupied by the array to which strPtr points.</li>

</ol>

<strong>Part II: Pure C Programming</strong>

You may only use the Standard C Library to perform the tasks in this part.

<strong>Task 6.</strong>

Basics [15 Marks]

In this task, you will create a C header that will declare the functions that you will implement in Tasks 7 and 8. You may declare constants and userdefines types needed by your function implementations.

Save the header file as editor2.h.

<strong>Task 7.</strong>

Completion [15 Marks]

In this task, you will implement a function that counts the number of lines from a given editing buffer. The editing buffer is an array of characters, and is passed to the function using pointer notation. The size of the buffer should also be passed to the function. The function will not modify the contents of the buffer, and this should be indicated in the function header (and prototype).

The function should be named editor_count_lines. It must return the number of lines in the buffer. A <em>line </em>is defined as consisting of the characters: (i) from the start of the buffer until a newline character; or (ii) immediately after a newline character until another newline character. The arguments should be ordered as follows:

<ol>

 <li>Editing buffer</li>

 <li>Size of editing buffer</li>

</ol>

In implementing the function, you must use pointer notation in traversing the buffer.

Save the function implementation in editor2.c. You may implement other functions (needed by your implementation) in editor2.c.

<strong>Task 8.</strong>

Challenge [7.5 Marks]

In this task, you will implement a function that will search for multiple occurrences of a given search string from a given editing buffer. The search string is a null-terminated array of characters, and is passed to the functions using pointer notation. The editing buffer is an array of characters, and is passed to the function using pointer notation. The size of the buffer should also be passed to the function. The function will not modify the search string and contents of the buffer, and this should be indicated in the function header (and prototype).

Two other arguments are passed to the function: an array of integers (passed using pointer notation) and the size of the integer array. This array will be used for storing the <em>positions </em>of the found occurrences of search string in the buffer. Position refers to the index of the first letter of the search string in the buffer.

To clarify the use of the integer array, suppose that the search string is found at positions 10, 24, 56, and 100, then the values of integer array elements at indices 0, 1, 2, and 3 should be 10, 24, 56, and 100, respectively. Note that the function will only be able to search at most K occurrences, where K is the size of the integer array.

The function should be named editor_search_multiple. It must return the number of elements in the integer array which has valid positions. In the example above where the search string is found at positions 10, 24, 56, and 100, the function must return 4.

The arguments should be ordered as follows:

<ol>

 <li>Editing buffer</li>

 <li>Size of editing buffer</li>

 <li>String to be searched</li>

 <li>Integer array</li>

 <li>Size of integer array</li>

</ol>

In implementing the function, you must use pointer notation in traversing the search string, buffer and integer array.

Save the function implementation in editor2.c. You may implement other functions (needed by your implementation) in editor2.c.

<strong>Part III: C++ Programming</strong>

You may use the C++ Standard Library to perform the tasks in this part.

<strong>Task 9.</strong>

Basics

In this task, you will create a C++ header file that will contain declaration of a class for implementing Tasks 10 and 11. You may declare constants and user-defines types needed by your implementations.

The class should be named EditorUtilities and should be defined within editor2 namespace.

Save the header file as editor2.hh.

<strong>Task 10.</strong>

Completion [15 Marks]

In this task, you will implement a member function of EditorUtilities for counting the number of words in a given editing buffer. The member function should be public and callable even without the instance of EditorUtilities.

The editing buffer is an array of characters, and is passed to the function using pointer notation. The size of the buffer should also be passed to the function. The function will not modify the contents of the buffer, and this should be indicated in the member function header (and prototype).

The function should be named countWords. It must return the number of words in the buffer. A <em>word </em>is defined as consisting of non-whitespace characters. Words are separated by whitespace charaters. In C/C++, the whitespace characters include:

<ul>

 <li>Space: ‘ ‘</li>

 <li>Horizontal tab: ‘t’</li>

 <li>Newline: ‘
’</li>

 <li>Vertical tab: ‘v’</li>

 <li>Form feed: ‘f’</li>

 <li>Carriage return: ‘r’</li>

</ul>

The arguments should be ordered as follows:

<ol>

 <li>Editing buffer</li>

 <li>Size of editing buffer</li>

</ol>

In implementing the function, you must use pointer notation in traversing the buffer.

Save the implementation in editor2.cc. You may implement other member functions (needed by your implementation) in editor2.cc.

<strong>Task 11.</strong>

Challenge [7.5 Marks]

In this task, you will implement a member function of EditorUtilities that will search for multiple occurrences of a given search string from a given editing buffer, <strong>ignoring case</strong>. The member function should be public and callable even without the instance of EditorUtilities. This is a variation of Task 6, hence, all the points in that task applies to this as well, except for the following:

<ul>

 <li>When searching for the occurrence of search string, case should be ignored. This means that if the search string is “Hello”, then “Hello”, “hello”, “heLLo”, etc. are considered as occurrences.</li>

 <li>The search string argument is of type std::string, not an array of characters.</li>

 <li>The member function should be named searchMultipleNoCase.</li>

</ul>

In implementing the function, you must use pointer notation in traversing the search string, buffer and integer array.

Save the implementation in editor2.cc. You may implement other member functions (needed by your implementation) in editor2.cc.


