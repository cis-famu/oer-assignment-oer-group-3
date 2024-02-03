# Input/Output 

## Objectives
After completing this chapter students will be able to:

1. Identify input and output streams
2. Read data from the standard input device
3. Describe input stream functions get, ignore, putback, and peek
4. Write data to the standard output device
5. Use manipulators in a program to format output
6. Perform input and output operations using the string data type
7. Read data from a file (include examples)
8. Write data to a file (include examples)

## Introduction
Chapter 2 introduced fundamental input/output (I/O) instructions in C++, utilizing cin and the extraction operator >> to receive data from the keyboard and cout with the insertion operator << to display results on the screen. This chapter delves deeper into C++'s I/O operations, providing a more comprehensive understanding. The focus is on statements for extracting input from the standard input device and sending output to the standard output device. Additionally, the chapter covers the intricacies of formatting output using manipulators. Recognizing the limitations of standard I/O operations, the chapter explores ways to extend these operations to interact with other devices.

### I/O Streams and Standard I/O Devices
In C++, Input/Output (I/O) operations involve the flow of data between a source and a destination, represented as a sequence of bytes called a stream. A stream can be considered as a continuous flow of characters from one place to another within a program. These characters are typically used to represent text data unless the program deals with other types of information, like images or speech. There are two main types of streams in C++: input streams for receiving data and output streams for sending data. The C++ language provides powerful prewritten I/O operations to simplify handling data in programs. These operations enable programmers to interact with external sources like files, the console, or other devices seamlessly, enhancing the flexibility of their applications. Understanding and utilizing these stream-based I/O operations is crucial for effective data manipulation and program functionality. 

### Using Predefined Functions in a Program
To use a predefined function in a C++ program, certain steps must be followed. Firstly, you need to identify the header file that contains the function's specifications and include it in your program. For instance, to use the "pow" function, you must include the "cmath" header file. Next, understand the function's name, the number of parameters it requires, and the type of each parameter. For "pow," it takes two decimal numbers, and it calculates the first number raised to the power of the second. Being aware of these details is essential for utilizing the function correctly. Appendix F in the programming resources provides information about commonly used header files and predefined functions, aiding programmers in effectively incorporating these functionalities into their code. 

### cin and the get Function
when using the extraction operator (>>) to input data, whitespace characters like spaces and newlines are often skipped. This can cause issues if you need to capture these characters as part of your input. For instance, if you want to input 'A', then a space, and finally '25', the extraction operator won't work as it skips spaces. To handle this, you can use the variable 'cin' with the 'get' function. This 'get' function reads the very next character from the input, including spaces and newlines, and stores it where specified. It allows you to process input character by character, ensuring you capture whitespace when needed, especially when dealing with data on a line-by-line basis.


### The putback and peek Functions
When dealing with mixed data containing both numbers and characters in C++ programming, it can be challenging to determine the type of input. One approach is to read the entire data set character by character, checking if each character is a digit to identify numbers. This method, however, can lead to complex and cumbersome code. Fortunately, C++ offers two helpful stream functions that simplify such situations. These functions provide effective ways to handle mixed data, allowing for easier identification and processing of numbers and characters in a more streamlined and efficient manner.


### Review questions
1) cin inputs data? T/F (T)
2) pow, called the power function, can be used to calculate xy T/F (T)
3) Input stream is a sequence of characters from an input device to the computer. T/F (T)
    The Dot Notation between I/O Stream Variables and I/O Functions: A Precaution
    Cin.get (ch);
    If there isn’t a dot separating the variable and the function name, just the function, or missing a parentheses, then it will result in a syntax error because it will input a new undeclared identifier in the system. 
    Examples:
    Correct 
    -	Cin.get (ch); 
    Incorrect 
    -	 Cinget (ch); 
    -	Cin.get ch;
    -	Get (ch);
    
    As you can see, the dot notations job is to separate the variable name from the function name and is categorized as a member access operator. Moreover, there are multiple functions (e.g. get, ignore, peek, etc) under istream with their own designated tasks. 
    Special Takes: Istream and ostream are called classes. Cin and cout are called objects. Stream variables are called stream objects, Cin is an istream object, cout is an ostream object and so forth. 
    
    ### Review Questions 
    Part A:
    1. Which of the following will result in a syntax error?
    A. Missing a dot notation
    B. Missing the variable name 
    C. Missing the parentheses
    D. All of the above
    Part B: 
    2. If there is a syntax error by one of the answers above, it’s because the programmer inputted in a(n) _____________________.
    A.	Ignore function
    B.	Undeclared identifier
    C.	Undeclared modifier 
    D.	Error message
    3. Yes/No: The dot notation is an operator.
	*Answers: 1. D. 2. B. 3. Yes.* 
    
    ## Input Failure
    Programming is trial and error, and even though the program is syntactically correct, it might produce incorrect results if the wrong variable or misplaced variable is used. Furthermore, mistakes like inputting a letter in the space of an int or double variable will result in an input failure. 
    Example:
    Incorrect
    Int x, y, z;
    Double  w;
    Input: 
    v 24
    The statement: 
    Cin >> x >> y; 
    Would result in an input failure because you’re putting a letter instead of an integer.
    Correct
    Input: 
    40, 80.93, 120
    The statement:
    Cin >> x>> w >> y;
    Would result in 40 in a, 80.93 in w, and 120 in y.
    Incorrect
    Input statement 
    Cin >> x >> y >> z;
    Would result in a fail state because it will end at the decimal since z is classified as an integer but not a double. A double allows for the function to go past the decimal.  The consequences of a fail state will cause all I/O statements using that stream are ignored. 
    	### The clear Function
    To combat the fail state, the programmer could use the clear stream function to restore the input stream to a working state. 
    The syntax to use the function clear is:
    Istream var.clear ();
    Istream var is an input stream variable. Even though you used clear to fix the program, the failed program needs to be thrown away using the function ignore. 
    Example: 
    Cin.clear ();
    Cin.ignore (200, ‘\n’);
    
    ### Review Questions:
    1. True/False: Once your input stream enters a fail state, the whole program can’t function
    2.  What happens when you place a letter character instead of an int or double variable?
    	A. Fail state
    B. Syntax error
    C. Input failure
    D. Nothing. Program continues to run 
    
    3. Yes/No: The ignore function has to be used after the clear function to clean the program
    
    *Answers: 1. False 2. C. 3. Yes
    
    
    ## Output and Formatting Output: Specific functions and manipulators to format the programmers desired output.
    The syntax of cout when used together with the insertion operator << is:
    Cout << expression/ manipulator << expression/manipulator ; 
	
	Expression evaluates and manipulator formats the output. 
    ### Setprecision Manipulator- controls the display of floating-point numbers, so decimal points or scientific notation. To set the desired decimal place your wold use the following syntax:
    	Cout << Setprecision (n)
    N= number of decimals.  
    To use this manipulator, iomanip must be included in the header file. We spoke about including a header file in chapter 2, but as a reminder the top of the file should format:
    #include <iostream>
    #include <iomanip>
    
    ### Fixed Manipulator- controls the floating-point numbers by making a sized decimal format, which is written as:
    Cout << fixed
    Once inputted, the format is executed to all floating-point numbers unless the fixed manipulator is disabled using a stream member function called unsetf:
    Cout.unsetf (ios::fixed);
     After getting disabled, the floating-point numbers go back to their original output
    Special Takes: Instead of cout<<fixed; and cout<< scientific; a programmer can use cout.setf (ios::fixed) and cout.setf (ios::scientific);.
    
    Example:
    #include <iostream>
    Using namespace std;
    Int main()
    {
    	Double hours = 32.30;
    	Double wages = 18.00;
    	Double tax = 0.07000;
    	Cout 	<< “hours = “ << hours << “, wages = “ << wages;
    		<< “, pay = “ << hours * wages ;
    		<< “, tax = “ <<  tax << endl << endl;
    	Cout << scientific;
    	Cout << “scientific notation: “ << endl;
    	Cout <<  “ hours = “ << hours << “, wage = “ << wage;
    	<< pay = “ << hours * wage
    	<< “, tax = “ << tax << endl << endl;
    	Cout << fixed;
    	Cout << “ fixed decimal notation: “ << endl;
    	Cout << “hours = “ << hours << “ ,  wage + “ << rate
    		<< “ , pay = “ << hours *  wage
    		<< “,  tax  = “ << tax << endl << endl;
    	Return 0;
    }
    Sample Run:
    Hours = 32.30, wage = 18, pay = 581.40, tax = 0.07
    Scientific notation:
    Hours = 3.23000e+01, wage = 1.800000e+01, pay = 5.814000e+02, tax = 7.000000e-02
    
    Fixed decimal notation:
    Hours = 32.300000, wage = 18.000000, pay = 581.400000, tax = 0.070000
    
    Special take: When coding, make sure you put a space between the function name and variable name or else there will be a syntax error. 
    From this, we see the difference between scientific notation and fixed decimal notation. 
    
    ### Showpoint Manipulator- forces the output to show the decimal point and trailing zeros using the preceding syntax:
    Cout << showpoint; 
    Or 
    Cout << fixed << showpoint;
    
    ### C++ 14 Digit Separator
    Commas can’t separate the digits of a number according to C++ rules, so they constructed a digit separator “ ‘ “ (an apostrophe).
    
    ### Setw – A manipulator that displays the value of an expression in a specific number of columns through a right-justified statement such as:
    Cout << setw (n) << x << endl
    N = number of columns and x is the int variable or expression. Note that the amount of columns expressed should not exceed the expression and vice versa. Similar to other manipulators, they also need the header file iomanip. Lastly, setw only controls the output of the next expression whereas set-precision is infinite until disabled. 
    
    
    
    ### Review Questions:
    1.	When including a manipulator, what header file should also be added in the program?
    2.	Which of the following manipulators controls the output of decimals or scientific notation?
    a.	Setw
    b.	Setprecision 
    c.	Fixed
    d.	Digit separator
    3.	Yes/No (and why): A fixed manipulator is only executed to the next floating-point number.
    *Answers: 1. #<iomanip> 2. B. 3. No because it is executed on all integers until disabled by the unsetf function.

    ## Additional Output Formatting Tools

### Setfill Manipulators
In this section, you will learn additional formatting tools that give you more control over your output. When using the setw manipulator in C++, if the number of columns specified is greater than the actual width required by the expression being formatted, the output is right-justified. The unused columns to the left are then padded with spaces by default. However, the setfill manipulator can be employed to specify a character other than a space to fill the unused columns, allowing for customized formatting.

### Left and Right Manipulators

When using the setw manipulator in C++, if the specified width exceeds the actual width required by the next expression, the default behavior is right-justified. To change the justification and make the output left-justified, the left manipulator is used. This manipulator ensures that the content is aligned to the left within the specified width. You can disable the manipulator left by using the stream function unsetf. Disabling the manipulator left returns the output to the settings of the default output format.

```cpp
#include <iostream>
#include <string>
#include <iomanip>

using namespace std;

int main()
{
    
}

```

### Review Questions

1.  True/False: There are left and right manipulators
2.  True/False: Disabling the manipulator left returns the output to the settings of the default output format.
3.  True/False: When using the setw manipulator in C++, if the number of columns specified is greater than the actual width required by the expression being formatted, the output is right-justified.

*Answers: 1. True 2. True 3. True*


## Input/Output and the String Type

In C++, you can utilize an input stream variable, such as cin, along with the extraction operator >>, to read a sequence of characters into a variable of the string data type. For instance, when the input is the string 'James', the following code snippet employs cin and the >> operator to store this input into the string variable named 'name':

```cpp
#include <iostream>
#include <string>

int main() 
{
    string name;

    // Using cin and >> to read a string
    cout << "Enter a name: ";
    cin >> name;

    cout << "You entered: " << name << endl;

    return 0;
}
```

This code prompts the user to enter a name, reads it using cin >> name, and then prints the entered name using cout.The extraction operator in C++ skips any leading whitespace characters and terminates reading when encountering the first whitespace character. Consequently, it cannot be used directly to read strings that may contain spaces. To read a string containing blanks, you can use the function getline.

### Review Questions

1.  True/False: >> is an extraction operator
2.  True/False: You can use a stream variable with a extraction operator 
3.  True/False: The extraction operator in C++ skips any leading whitespace characters and terminates reading when encountering the first whitespace character

*Answers: 1. True 2. True 3. True*

## Debugging: Understanding Logic Errors and Debugging with cout Statements

In programming, compilers are adept at detecting and reporting syntax errors, providing helpful explanations to aid in debugging. However, logic errors are often more subtle and might not be identified by the compiler, except for straightforward cases like using a variable without proper initialization. To address logic errors, developers often resort to using cout statements for debugging.

Let's consider a program that calculates the area of a rectangle. The formula for the area of a rectangle is given by: Area = Length * Width. However, imagine a scenario where the calculated area is not as expected due to a logic error. We can use cout statements for debugging. Here's an example:

```cpp
#include <iostream>

int main() 
{
    double length;
    double width;
    double area;

    // Input length of the rectangle
    cout << "Enter the length of the rectangle: ";
    cin >> length;

    // Input width of the rectangle
    cout << "Enter the width of the rectangle: ";
    cin >> width;

    // Calculation of area with a logic error
    area = length + width; // Logic error: should be area = length * width;

    // Output calculated area
    cout << "Calculated area of the rectangle: " << area << endl;

    return 0;
}
```

In this example, there is a logic error in the calculation of the area, where '+' is mistakenly used instead of '*'. To identify and correct this error, developers can insert cout statements to print the intermediate values of variables (length, width, and area) and identify the discrepancy between the expected and actual results.

### Review Questions
1. True/False: In programming, compilers are adept at detecting and reporting syntax errors
2. True/False: To address logic errors, developers often resort to using cout statements for debugging
3. True/False: logic errors are often more subtle and might not be identified by the compiler

*Answers: 1. True 2. True 3. True*

## File Input/Output

Working with input and output directly from the keyboard and screen has limitations, especially when dealing with large amounts of data. Manually typing extensive input data is inconvenient, error-prone, and time-consuming. Additionally, displaying output on the screen is impractical for large datasets or when you need to distribute the results in a printed format.

To overcome these challenges, C++ provides file I/O capabilities through the fstream header file. This allows programs to read data from and write data to secondary storage, such as a flash drive. In the context of file I/O, a file is an area in secondary storage used to store information.

The fstream header file introduces two essential data types: ifstream (input file stream), similar to istream, and ofstream (output file stream), similar to ostream. Unlike cin and cout, which are predefined for standard I/O devices, file stream variables must be declared and associated with specific files.

File I/O involves a five-step process:

```cpp
1. Include the fstream header file in the program:

    #include <iostream>

2. Declare file stream variables:

    ifstream inputFile;
    ofstream outputFile;

3. Associate file stream variables with I/O sources:

inputFile.open("input.txt");
outputFile.open("output.txt");

4. Use file stream variables with >>, <<, or other I/O functions:

int data;
inputFile >> data; // Reading from file
outputFile << "Result: " << result; // Writing to file

5. Close the files when done:

inputFile.close();
outputFile.close();
```
By leveraging file I/O, you can efficiently manage large datasets, pre-prepare input data, save program output for future use, and present results in a more organized and shareable manner, such as distributing printed reports before a meeting.

### Review Questions
1. True/False: C++ provides file I/O capabilities through the fstream header file
2. True/False: a file is an area in secondary storage used to store information
3. True/False: file stream variables must be declared and associated with specific files

*Answers: 1. True 2. True 3. True*
    
 ## Chapter Summary

- A stream in C++ serves as an unending flow of characters, traversing from a source to a destination. Distinctly, an input stream directs data towards a computer, while an output stream propels data away from a computer.

- The input stream object, 'cin' (common input), initializes to the standard input device, typically the keyboard. Conversely, the output stream object, 'cout' (common output), initializes to the standard output device, often the screen.

- The binary operator '>>' with an input stream, such as 'cin', is the stream extraction operator. It requires an input stream variable on the left (e.g., 'cin') and a variable on the right for data extraction.

- On the other hand, the binary operator '<<' with an output stream, like 'cout', is the stream insertion operator. The left-side operand is the output stream variable (e.g., 'cout'), and the right-side operand is an expression or a manipulator.

- While reading input into a variable, '>>' skips leading whitespace characters. To utilize 'cin' and 'cout', the program must include the 'iostream' header file.

- Functions like 'get' read data character by character without skipping whitespace, 'ignore' skips data within a line, 'putback' places the last character back into the input stream, and 'peek' returns the next character without removing it.

- Attempting to read invalid data puts the input stream into a fail state. To recover from an input failure, the 'clear' function is used.

- Manipulators like 'setprecision' format floating-point output to a specified decimal precision, 'fixed' outputs in a fixed decimal format, and 'showpoint' appends a decimal point with trailing zeros.

- In C++, the single-quote mark (' ') serves as a digit separator.

- The 'setw' manipulator formats expression output in a specified number of columns, right-justified by default. If specified columns are insufficient, the output expands to accommodate the expression.

- The 'setfill' manipulator fills unused columns with a character other than a space. To left-justify the output, 'left' manipulator is used.

- For stream functions 'get', 'ignore', 'putback', 'peek', 'clear', and 'unsetf', the 'iostream' header must be included. For manipulators 'setprecision', 'setw', and 'setfill', 'iomanip' must be included.

- In file I/O, the 'fstream' header file defines 'ifstream' and 'ofstream'. To conduct file operations, include '#include <fstream>', declare 'ifstream' for input and 'ofstream' for output, and use appropriate operators or functions with file stream variables. Closing files is done using 'close()' with the respective file stream variable.
   
    ### Key Terms:
    •	Input stream- Characters from an input device (keyboard, mic, etc) to the computer. 
    •	Output steam- Characters from the computer to an output device. 
    •	Iostream- the header file each C++ program must have. 
    o	Istream- input stream
    o	O stream – output stream
    •	Cin – commons input
    •	Cout – common output 
    •	Input/Output/Stream Variable- variables within their specific stream.
    •	Char – a character excluding blanks (spaces).
    •	Int – a number 
    •	Double – a decimal number
    •	Input failure – 
    •	Member functions/ stream (member) functions – Functions accompanied by istream.
    •	Predefined functions – Already written functions.
    •	Arguments/ Parameters – The place the number will be.
    •	Function call – Passes control within the expression.
    •	Member access operator – dot notation which separates the input stream variable. 
    
    
    
    
     
    
     
    
    
     
     
     
    
    
    
     
    
    
    
    
    
    
    
    
    
    
    
    
