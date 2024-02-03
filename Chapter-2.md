
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
    
    
    
    
     
    
     
    
    
     
     
     
    
    
    
     
    
    
    
    
    
    
    
    
    
    
    
    