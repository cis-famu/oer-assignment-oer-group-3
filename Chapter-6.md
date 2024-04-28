# User-Defined Simple Data Types, Namespaces, and the string Type

## Objectives
By the end of this chapter, learners will:

* Understand the role and utility of arrays in programming.
* Learn to declare and initialize arrays effectively.
* Master techniques for organizing and manipulating data using arrays.
* Comprehend the limitations and constraints associated with array handling.
* Explore passing arrays as parameters to functions for enhanced functionality.
* Acquire skills in searching and sorting arrays for efficient data management.
* Implement auto declarations and leverage their advantages.
* Demonstrate proficiency in utilizing range-based for loops for array iteration.
* Utilize C-strings to input and output data efficiently.
* Distinguish between and effectively utilize parallel, two-dimensional, and multidimensional arrays for various programming needs.

## Introduction
In Chapter 2, you delved into the foundational elements of C++'s data types, which can be categorized into three main groups: integral, floating point, and enum. Subsequent chapters primarily focused on integral and floating-point data types. However, in this chapter, the spotlight shifts to exploring the enum type in depth. Additionally, the ubiquitous statement "using namespace std;" discussed earlier gains prominence, as it's a staple in every ANSI/ISO Standard C++ program utilizing C++ style header files. The latter portion of this chapter delves into the significance of this statement, shedding light on the namespace mechanism and its role. Furthermore, you'll delve into the intricacies of the string type, uncovering a plethora of functions designed to streamline string manipulation for enhanced programming efficiency.

### Enumeration Type 
Up until now, your programming endeavors have primarily revolved around common data types like int, bool, char, and double. While these data types suffice for most tasks, there are instances where they may fall short in addressing specific challenges. Thankfully, C++ offers a solution by empowering users to craft their own data types, thereby amplifying the language's adaptability and versatility.

In this segment, you'll uncover the art of fashioning custom data types called enumeration types. These serve as the stepping stones for more intricate data type creation in forthcoming chapters.

To define an enumeration type, you must specify:

* A distinctive name for the data type.
* A collection of values pertinent to the data type.
* The ability to perform operations with these values.

C++ provides a means to construct a fresh, straightforward data type wherein you define its name and associated values, although it restricts the creation of custom operations. This safeguard prevents potential system malfunctions.

When assigning values to the data type, it's imperative to use valid identifiers as per C++ standards.

For Example:
```cpp
#include <iostream>
using namespace std;

// Define an enumeration type called DayOfWeek
enum class DayOfWeek {
    Sunday,
    Monday,
    Tuesday,
    Wednesday,
    Thursday,
    Friday,
    Saturday
};

int main() {
    // Declare a variable of type DayOfWeek
    DayOfWeek today = DayOfWeek::Wednesday;

    // Check the value of today and output a corresponding message
    switch (today) {
        case DayOfWeek::Sunday:
            cout << "Today is Sunday." << endl;
            break;
        case DayOfWeek::Monday:
            cout << "Today is Monday." << endl;
            break;
        case DayOfWeek::Tuesday:
            cout << "Today is Tuesday." << endl;
            break;
        case DayOfWeek::Wednesday:
            cout << "Today is Wednesday." << endl;
            break;
        case DayOfWeek::Thursday:
            cout << "Today is Thursday." << endl;
            break;
        case DayOfWeek::Friday:
            cout << "Today is Friday." << endl;
            break;
        case DayOfWeek::Saturday:
            cout << "Today is Saturday." << endl;
            break;
        default:
            cout << "Invalid day!" << endl;
    }

    return 0;
}
```
In this code:

1. We define an enumeration type DayOfWeek using the enum class syntax. This enumeration contains the days of the week as its values.
2. Inside main(), we declare a variable today of type DayOfWeek and initialize it to DayOfWeek::Wednesday.
3. We use a switch statement to check the value of today and output a corresponding message based on the day of the week.

### Review Questions 
1. True/False: Enumeration types in C++ used to create custom data types?
2. Yes/No: Do you need to specify a distinctive name and a collection of values to define an enumeration type in C++?
3. Yes/No: Does C++ allow creating custom operations for enumeration types?

***Answers: 1. True 2. Yes 3. No***

### Declaring Variables 
In C++, declaring variables is fundamental to defining storage locations for specific data types. The syntax typically involves specifying the type followed by the variable name, like int count; or float value;. Variables can also be initialized during declaration, such as int age = 30; or double pi = 3.14159;. Variables in C++ can have various scopes, including block scope within curly braces {}, function scope, file scope (for global variables), or class scope for class member variables. Constants are declared using the const keyword, ensuring their values remain unchanged during program execution. Pointers and references provide ways to work with memory addresses and aliases to variables, respectively. With modern C++, type inference using auto simplifies variable declarations by letting the compiler deduce the variable's type based on its initialization. Additionally, namespaces help organize variables to avoid naming conflicts in larger projects. Properly declaring and initializing variables is crucial for writing robust and maintainable C++ code.\

For Example:
```cpp
#include <iostream>
using namespace std;


int globalVar = 100;

int main() {
  
    int localVar = 50;
    
    // Constant declaration
    const float PI = 3.14159;

    {
     
        int innerVar = 25;
        char letter = 'A';
        
       
        cout << "Global variable: " << globalVar << endl;
        cout << "Local variable: " << localVar << endl;
        cout << "Inner variable: " << innerVar << endl;
        cout << "Constant PI: " << PI << endl;
    }

 
    static int staticVar = 0;
    staticVar++;
    cout << "Static variable: " << staticVar << endl;

    return 0;
}
```
In this example:

* globalVar is a global variable accessible throughout the program.
* localVar is a local variable with function scope, available only within the main() function.
* innerVar and letter are variables with block scope, available only within the inner curly braces {}.
* PI is a constant with block scope, holding the value of pi.
* staticVar is a static variable with function scope, retaining its value between function calls.
* Compile and run this code to see how variables with different scopes behave.

### Review Questions
1. True/False: Syntax for declaring a variable in C++ specifying the type followed by the variable name?
2. True/False: Variables in C++ have only one scope?
3. Yes/No: Do namespaces help avoid naming conflicts in larger C++ projects?

***Answers: 1. True 2. False 3. Yes***

### Assignment 
In C++, assignment refers to the process of storing a value in a variable after it has been declared. The assignment operator = is used for this purpose, where the value on the right-hand side (RHS) of the operator is assigned to the variable on the left-hand side (LHS). For example, int num = 10; assigns the value 10 to the variable num. Assignments can involve literals, variables, expressions, or function calls that return values compatible with the variable's type. C++ allows compound assignment operators like +=, -= , *=, and /= which combine arithmetic operations with assignment. Additionally, C++ supports type conversion during assignment, where values are automatically converted to the variable's type if necessary, following implicit type conversion rules. Understanding assignment is crucial for manipulating variables and performing computations in C++ programs.

For example:
```cpp
#include <iostream>
using namespace std;

int main() {
    int num1, num2;  // Declaring two integer variables

    num1 = 10;  // Assigning the value 10 to num1
    num2 = num1 + 5;  // Assigning the result of an expression to num2

    cout << "num1: " << num1 << endl;  // Output: num1: 10
    cout << "num2: " << num2 << endl;  // Output: num2: 15

    // Compound assignment operators
    num1 += 5;  // Equivalent to: num1 = num1 + 5
    num2 *= 2;  // Equivalent to: num2 = num2 * 2

    cout << "num1 after compound assignment: " << num1 << endl;  // Output: num1 after compound assignment: 15
    cout << "num2 after compound assignment: " << num2 << endl;  // Output: num2 after compound assignment: 30

    // Type conversion during assignment
    double pi = 3.14159;
    int approxPi = pi;  // Type conversion from double to int (truncates decimal part)

    cout << "Approximate value of pi as an integer: " << approxPi << endl;  // Output: Approximate value of pi as an integer: 3

    return 0;
}
```
In this code:

* num1 and num2 are two integer variables declared initially.
* Values are assigned to these variables using the assignment operator =.
* num2 is assigned the result of an arithmetic expression involving num1.
* Compound assignment operators like += and *= are used to modify variables by combining arithmetic operations with assignment.
* Type conversion is demonstrated when assigning a double value to an int variable, which results in truncation of the decimal part.

### Review Questions
1. Yes/No: Is assignment in C++ the process of storing a value in a variable after it has been declared?
2. True/False: Assignments in C++ involve literals, variables, expressions, or function calls returning compatible values?
3. Yes/No: Does the assignment operator in C++ use = to assign the value on the right-hand side to the variable on the left-hand side?

***Answers: 1. Yes 2. True 3. Yes***
### Operations and Enumeration Types
In C++, enumerations (enums) and operation types are fundamental concepts that aid in organizing and categorizing data and operations within a program. Enums provide a way to define named integral constants, making code more readable and maintainable by associating meaningful names with specific values. Operation types, on the other hand, refer to the different kinds of operations that can be performed on variables or values, including arithmetic, relational, logical, bitwise, and assignment operations. Understanding enums helps in creating custom data types with a limited set of possible values, while knowledge of operation types is essential for performing various computations, comparisons, and logical manipulations in C++ programs. These concepts are core components of the language and are widely used in software development for structuring code and implementing algorithms effectively.

For Example:
```cpp
#include <iostream>
using namespace std;

// Enumeration for days of the week
enum Days {Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday};

int main() {
    // Enum variable declaration and initialization
    Days today = Monday;

    // Arithmetic operations
    int num1 = 10, num2 = 5;
    int sum = num1 + num2;
    int difference = num1 - num2;
    int product = num1 * num2;
    int quotient = num1 / num2;
    int remainder = num1 % num2;

    cout << "Sum: " << sum << endl;  // Output: Sum: 15
    cout << "Difference: " << difference << endl;  // Output: Difference: 5
    cout << "Product: " << product << endl;  // Output: Product: 50
    cout << "Quotient: " << quotient << endl;  // Output: Quotient: 2
    cout << "Remainder: " << remainder << endl;  // Output: Remainder: 0

    // Relational operations
    bool isEqual = (num1 == num2);  // false
    bool isNotEqual = (num1 != num2);  // true
    bool isGreaterThan = (num1 > num2);  // true
    bool isLessThan = (num1 < num2);  // false
    bool isGreaterOrEqual = (num1 >= num2);  // true
    bool isLessOrEqual = (num1 <= num2);  // false

    cout << "Is num1 equal to num2? " << isEqual << endl;  // Output: Is num1 equal to num2? 0 (false)
    cout << "Is num1 not equal to num2? " << isNotEqual << endl;  // Output: Is num1 not equal to num2? 1 (true)
    // Other relational operations follow similarly...

    // Logical operations
    bool condition1 = true, condition2 = false;
    bool logicalAnd = (condition1 && condition2);  // false
    bool logicalOr = (condition1 || condition2);  // true
    bool logicalNot = !condition1;  // false

    cout << "Logical AND: " << logicalAnd << endl;  // Output: Logical AND: 0 (false)
    cout << "Logical OR: " << logicalOr << endl;  // Output: Logical OR: 1 (true)
    cout << "Logical NOT: " << logicalNot << endl;  // Output: Logical NOT: 0 (false)

    // Bitwise operations
    int num3 = 5, num4 = 3;
    int bitwiseAnd = num3 & num4;  // 1
    int bitwiseOr = num3 | num4;  // 7
    int bitwiseXor = num3 ^ num4;  // 6
    int bitwiseNot = ~num3;  // -6 (assuming 32-bit integers)

    cout << "Bitwise AND: " << bitwiseAnd << endl;  // Output: Bitwise AND: 1
    cout << "Bitwise OR: " << bitwiseOr << endl;  // Output: Bitwise OR: 7
    cout << "Bitwise XOR: " << bitwiseXor << endl;  // Output: Bitwise XOR: 6
    cout << "Bitwise NOT: " << bitwiseNot << endl;  // Output: Bitwise NOT: -6

    // Assignment operations
    int value = 10;
    value += 5;  // Equivalent to: value = value + 5

    cout << "Value after assignment: " << value << endl;  // Output: Value after assignment: 15

    return 0;
}
```
This code demonstrates:

* Enumeration Days representing days of the week.
* Declaration and initialization of variables.
* Arithmetic operations (+, -, *, /, %).
* Relational operations (==, !=, >, <, >=, <=).
* Logical operations (&&, ||, !).
* Bitwise operations (&, |, ^, ~).
* Compound assignment operations (+=).

### Review Questions 
1. True/False: Enums in C++ provide a way to define named integral constants?
2. Yes/No: Are operation types in C++ limited to arithmetic operations only?
3. Yes/No: Do operation types in C++ include relational, logical, bitwise, and assignment operations?

***Answers: 1. True 2. No 3. Yes***

### Relational Operators 
Relational operators in programming, including those in C++, are essential for comparing values and determining relationships between variables or expressions. These operators evaluate whether a specific relationship holds true or false between two operands. In C++, the common relational operators are == (equal to), != (not equal to), > (greater than), < (less than), >= (greater than or equal to), and <= (less than or equal to). Relational operators are frequently used in decision-making structures like if statements and loops to control the flow of execution based on conditions. Understanding how to use relational operators effectively is crucial for writing logical and efficient code that responds appropriately to different scenarios and data comparisons.

For Example:
```cpp
#include <iostream>
using namespace std;

int main() {
    int num1 = 10, num2 = 20;

    // Equal to (==) operator
    if (num1 == num2) {
        cout << "num1 is equal to num2" << endl;
    } else {
        cout << "num1 is not equal to num2" << endl;
    }

    // Not equal to (!=) operator
    if (num1 != num2) {
        cout << "num1 is not equal to num2" << endl;
    } else {
        cout << "num1 is equal to num2" << endl;
    }

    // Greater than (>) operator
    if (num1 > num2) {
        cout << "num1 is greater than num2" << endl;
    } else {
        cout << "num1 is not greater than num2" << endl;
    }

    // Less than (<) operator
    if (num1 < num2) {
        cout << "num1 is less than num2" << endl;
    } else {
        cout << "num1 is not less than num2" << endl;
    }

    // Greater than or equal to (>=) operator
    if (num1 >= num2) {
        cout << "num1 is greater than or equal to num2" << endl;
    } else {
        cout << "num1 is less than num2" << endl;
    }

    // Less than or equal to (<=) operator
    if (num1 <= num2) {
        cout << "num1 is less than or equal to num2" << endl;
    } else {
        cout << "num1 is greater than num2" << endl;
    }

    return 0;
}
```
In this code:

* num1 and num2 are initialized with values 10 and 20, respectively.
* Relational operators (==, !=, >, <, >=, <=) are used in if statements to compare num1 and num2.
* Based on the comparisons, appropriate messages are displayed indicating the result of each comparison.
* When you run this code, you'll see output messages indicating the relationships between num1 and num2 based on the relational operators used.

### Review Questions 
1. Yes/No: Do relational operators in C++ compare values and determine relationships between variables or expressions?
2. True/False: the common relational operators in C++ ==, !=, >, <, >=, and <=?
3. Yes/No: Are relational operators primarily used in decision-making structures like if statements and loops?

***Answers: 1. Yes 2. True 3. Yes***

### Input /Output of Enumeration Types
In C++, input/output operations involving enumeration types are straightforward and intuitive. Enumerations, or enums, allow developers to define a set of named constants representing discrete values, making code more readable and expressive. When it comes to input/output with enumeration types, the primary concern is often converting between the enum's symbolic names and their underlying integral values. For input, you typically read user input as strings or numerical values and then map those inputs to the corresponding enum values. Conversely, for output, you convert enum values to their symbolic names or display them directly depending on the context. C++ provides mechanisms like static_cast or direct type conversion to facilitate these conversions between enum types and their underlying integral values, enabling seamless integration of enum types into input/output operations within programs.

For Example: 
```cpp
#include <iostream>
#include <string>
using namespace std;

// Enumeration for different days of the week
enum Days {Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday};

int main() {
    // Input: Reading day of the week as a string
    string userInput;
    cout << "Enter a day of the week (e.g., Monday): ";
    cin >> userInput;

    // Converting user input to enum value
    Days day;
    if (userInput == "Monday") {
        day = Monday;
    } else if (userInput == "Tuesday") {
        day = Tuesday;
    } else if (userInput == "Wednesday") {
        day = Wednesday;
    } else if (userInput == "Thursday") {
        day = Thursday;
    } else if (userInput == "Friday") {
        day = Friday;
    } else if (userInput == "Saturday") {
        day = Saturday;
    } else if (userInput == "Sunday") {
        day = Sunday;
    } else {
        cout << "Invalid input." << endl;
        return 1;  // Exit program with an error code
    }

    // Output: Displaying enum value as a string
    switch (day) {
        case Monday:
            cout << "You entered Monday." << endl;
            break;
        case Tuesday:
            cout << "You entered Tuesday." << endl;
            break;
        case Wednesday:
            cout << "You entered Wednesday." << endl;
            break;
        case Thursday:
            cout << "You entered Thursday." << endl;
            break;
        case Friday:
            cout << "You entered Friday." << endl;
            break;
        case Saturday:
            cout << "You entered Saturday." << endl;
            break;
        case Sunday:
            cout << "You entered Sunday." << endl;
            break;
    }

    return 0;
}
```
In this code:

* An enumeration Days representing days of the week is defined.
* User input is read as a string using cin.
* The input string is converted to the corresponding enum value using conditional statements.
* The converted enum value is then used in a switch statement to display the day of the week based on the user's input.

### Review Questions 
1. Yes/No: Do enums in C++ allow developers to define a set of named constants representing discrete values?
2. Yes/No: In C++, is it typical to read user input for enums as strings or numerical values and then map those inputs to the corresponding enum values?
3. Yes/No: For output with enums in C++, can you convert enum values to their symbolic names or display them directly based on the context?

***Answers: 1. Yes 2. Yes 3. Yes***
### Functions and Enumeration Types
Functions and enumeration types are foundational concepts in C++ programming, often used together to enhance code readability, organization, and reusability. Functions allow developers to encapsulate a set of instructions into a named block, making it easier to manage and reuse code. Enumerations, on the other hand, provide a way to define a set of named constants, which can be particularly useful for representing a limited range of related values. When used together, functions can accept enumeration types as parameters or return them as results, making code more expressive and self-documenting. For instance, a function that calculates the total price of items based on their type (represented by an enum) can improve code clarity and maintainability compared to using raw integers or strings. By leveraging functions and enumeration types effectively, developers can write cleaner, more organized, and easier-to-maintain C++ code.

For Example: 
```cpp
#include <iostream>
using namespace std;

// Enumeration for different types of items
enum ItemType {Book, Clothing, Electronics, Food};

// Function to calculate the price based on item type
double calculatePrice(ItemType type, double basePrice) {
    double totalPrice = 0.0;

    switch (type) {
        case Book:
            totalPrice = basePrice * 0.9;  // 10% discount for books
            break;
        case Clothing:
            totalPrice = basePrice * 1.2;  // 20% markup for clothing
            break;
        case Electronics:
            totalPrice = basePrice * 1.15;  // 15% markup for electronics
            break;
        case Food:
            totalPrice = basePrice * 1.05;  // 5% markup for food
            break;
    }

    return totalPrice;
}

int main() {
    double basePrice = 100.0;

    // Calculate prices for different item types
    double bookPrice = calculatePrice(Book, basePrice);
    double clothingPrice = calculatePrice(Clothing, basePrice);
    double electronicsPrice = calculatePrice(Electronics, basePrice);
    double foodPrice = calculatePrice(Food, basePrice);

    // Output the calculated prices
    cout << "Price for a book: $" << bookPrice << endl;
    cout << "Price for clothing: $" << clothingPrice << endl;
    cout << "Price for electronics: $" << electronicsPrice << endl;
    cout << "Price for food: $" << foodPrice << endl;

    return 0;
}
```
In this code:

* An enumeration ItemType is defined to represent different types of items (Book, Clothing, Electronics, Food).
* The calculatePrice function accepts an ItemType parameter along with a base price and calculates the total price based on the item type.
* In the main function, prices are calculated for each item type using the calculatePrice function, and the results are outputted.

This example demonstrates how functions can be used with enumeration types to perform specific operations based on different cases or types.

### Review Questions
1. True/False: Functions in C++ allow developers to encapsulate a set of instructions into a named block?
2. Yes/No: Are enumerations in C++ used to define a set of named constants representing related values?
3. True/False: Functions in C++ accept enumeration types as parameters or return them as results?

***Answers: 1. True 2. Yes 3. True***

## Introduction
Large programs typically use user-defined functions rather than the previously described functions. Functions are called modules and user-defined functions are used to form a larger program whereas predefined functions make it more difficult because their code is not available for us. 

## Predefined Functions 
Every function has a name and does some computation. 

For example:
Predefined mathematical functions:

Pow (x, y) = x^y and these are the parameters

Pow (3.0, 3) - 3.0^3 = 27

Sqrt (x) = nonnegative square root of x for x >= 0.0. 

Sqrt 9.0 is 3.0

Floor (x) = largest whole number that is less than or equal to x. 

Floor (36. 23) is 36
All these predefined functions are considered doubles. 

### Review Questions 
1. Yes/No: Do functions have a computation?
2. Name three different predefined mathematical functions.
3. True/False: All predefined mathematical functions are doubles.

***Answers: 1. Yes 2. Pow, Srt, Exp (and more) 3. True ***

### User-Defined Functions 
Function	Header File	Purpose	Parameter(s) Type	Result
abs(x)	<cmath>	Returns the absolute value of its argument: abs(-7) = 7	int (double)	int (double)
ceil(x)	<cmath>	Returns the smallest whole number that is not less than x: ceil(56.34) = 57.0	double	double
cos(x)	<cmath>	Returns the cosine of angle x: cos(0.0) = 1.0	double (radians)	double
exp(x)	<cmath>	Returns ex, where e = 2.718: exp(1.0) = 2.71828	double	double
fabs(x)	<cmath>	Returns the absolute value of its argument: fabs(-5.67) = 5.67	double	double
floor(x)	<cmath>	Returns the largest whole number that is not greater than x: floor(45.67) = 45.00	double	double
islower(x)	<cctype>	Returns true if x is a lowercase letter; otherwise it returns false; islower('h') is true	int	int
isupper(x)	<cctype>	Returns true if x is a uppercase letter; otherwise it returns false; isupper('K') is true	int	int
pow(x, y)	<cmath>	Returns xy; If x is negative, y must be a whole number: pow(0.16, 0.5) = 0.4	double	double
sqrt(x)	<cmath>	Returns the nonnegative square root of x, x must be nonnegative: sqrt(4.0) = 2.0	double	double
tolower(x)	<cctype>	Returns the lowercase value of x if x is uppercase; otherwise, returns x	int	int
toupper(x)	<cctype>	Returns the uppercase value of x if x is lowercase; otherwise, returns x	int	int

We spoke about this before but to use the predefined function in a program, the user must input the header file that has the purpose you want using the include statement. 

For example:
include <iostream>
#include <cmath>
 
using namespace std;
 
int main () {
    double num;
    
    // Prompt the user to enter a number
    cout << "Enter a number to find its square root: ";
    cin >> num;
    
    // Check if the number is non-negative
    if (num >= 0) {
        // Calculate the square root using sqrt() function
        double squareRoot = sqrt(num);
        
        // Display the result
        cout << "Square root of " << num << " is: " << squareRoot << endl;
    } else {
        cout << "Square root of a negative number is undefined." << endl;
    }
    
    return 0;
}

This program works as follows. It inputs the number to find the square root and if it is a nonnegative number then it finds the value, but if it is, then the program would say it is undefined. 

## User Defined Functions 
User-defined functions in C++ are separated into two categories:
•	Value-returning functions – Returns a value of a specific data type using the return statement.  have a return type. 
•	Void functions – don't have a return type

### Review Questions 
1. What are the two types of user-defined functions in C++?
2. What must you do before you usr a predefined/user-defined function?
3. True/False: Void functions have a return type.

***Answers: 1. Void and value-returning 2. Include the file name in the header file. 3. False***

## Value- Returning Functions
To use any of the predefined value returning functions such as pow, abs, islower, and toupper, you must know the name of the header file (for that function), input that header file using an include statement along with the following: the name of the function, parameters, data type of parameters, the data type of the value(value returned) by the function, and the code required to accomplish the task.  
The first four are the heading/ function header and the fifth is the body of the 		function and together, these five properties are called the definition. 
Note! Value-returning function only returns ONE value so to keep the function you must save the value for further calculation, use it some calculation, or print the value. 
Furthermore, this function is used for an assignment, a parameter in a function call, or an output statement. These are called expressions. 

For example 
Int abs (int number)
Abs is called a formal parameter, so it’s a number. 

For example: 
Double u = 2.5;
Double v = 3.0;
Double x, y;
X = pow (u, v) ; 
Y = pow (2.0, 3.2) + 5.1;
Cout << u << “ to the power of 7 = “ << pow (u, 7) << endl; 
The variables u and v that appear in the call to the function pow in Line 1 are called the actual parameters of that call.
Formal is declared in the function heading, but the actual parameter is in the call to a function. 

### Syntax: Value- Returning Function
FunctionType functionName (formal parameter list)
{
Statements
}
Aka data type or return type. 

### Syntax: Formal Parameter List
DataType identifier, dataType identifer, ...

### Function Call 
FunctionName (actual parameter list)

### Syntax: Actual Parameter List
Expression or variable,  expression or variable, ...
Expression is one constant value and can be empty. If it is empty , use the following form:
FunctionType functionName () 
Because both are empty. If everything is empty use the following:
FunctionName ()
The number of actual parameters must match the formal parameters. “one- to- one correspondence for formal and actual parameters.

### Return Statement 
After being computed, the functions return this value through the return statement. 

### Syntax: return Statement 
Return expr;
Expr can be a variable, constant value, or expression. 
Return is a reserved word. Once the return statement is executed, the function ends, and the control goes back to the calling function. If a return statement is executed in the function main, the program terminates. 
Function Prototype - the function heading, terminated by a semicolon; without the body of the function. It is not a definition and can be placed before any function definition. 

### Syntax: Function Prototype
FunctionType functionName (parameter list);

### Value Returning Functions: Some Peculiarities:
If a return statement contains more than one expression, only the value of the last expression is returned. To save yourself from the headache, don’t have more than one. 
More Examples of Value-Returning Functions
Flow of Compilation and Execution
Must declare an identifier before you can use it. If main appears first, it is compiled first, but if it appears anywhere else than all the functions outside of prototypes are compiled before the function main in the order placed (top to bottom).

### Review Questions 
1. How many values does the value-returning type return?
2. What would happen if there was more than one value in the return?
3. True/False: The syntax for both expressions in the actual parameter list to be empty is FunctionType functionName ().

***Answers: 1. 1 2. Returns the last data. 3. False***

## Void Functions
Both void and value-returning functions have a heading and body, can place user-defined void functions before or after the function main.A void function does not have a data type, so functionType is the return type. Since they don’t have a data type, they’re not considered an expression but a standalone statement. 	
Function Definiton
Void functionName (formal parameter list)
{ 
Statements
}
Formal Parameter list
DataType & variable, dataType & variable, ...
Both must be specified. 
Function Call 
FunctionName (actual parameter list) ; 
Actual Parameter List
Expression or variable, expression or variable, ...
Same rules apply for void functions when it comes to actual and formal parameters.


## Value Parameters
An observation about void functions and value parameters is that when a function is called for a value parameter, the actual parameter value is copied into the correspondence formal parameter. During program execution, the formal parameter manipulates the data stored in its own memory space by copying the actual parameter and making it a separate variable. 

## Reference Vairables as Parameters
Calculates grade 

## Chapter Summary 
1. An enumeration type is a set of ordered values.

1. C++’s reserved word enum is used to create an enumeration type.

1. No arithmetic operations are allowed on the enumeration type.

1. Relational operators can be used with enum values.

1. Enumeration type values cannot be input or output directly.
 
1. Enumeration types can be passed as parameters to functions either by value or by reference.

1. A function can return a value of the enumeration type.

1. An anonymous type is one in which a variable’s values are specified without any type name.

1. C++’s reserved word typedef is used to create synonyms or aliases to previously defined data types.

1. Anonymous types cannot be passed as parameters to functions.

1. The namespace mechanism is a feature of ANSI/ISO Standard C++.

1. A namespace member is usually a named constant, variable, function, or another namespace.

1. The scope of a namespace member is local to the namespace.

1. One way to access a namespace member outside the namespace is to precede the namespace member name with the namespace name and scope resolution operator.

1. In C++, namespace is a reserved word.

1. To use the namespace mechanism, the program must include the ANSI/ ISO Standard C++ header files—that is, the header files without the extension h.

1. The using statement simplifies the accessing of namespace members.

1. In C++, using is a reserved word.

1. The keyword namespace must appear in the using statement.

1. When accessing a namespace member without the using statement, the namespace name and the scope resolution operator must precede the name of the namespace member.

1. A string is a sequence of zero or more characters.

1. Strings in C++ are enclosed in double quotation marks.

1. To use the type string, the program must include the header file string. The other header files used in the program should be ANSI/ ISO Standard C++ style header files.

1. The assignment operator can be used with the string type.

1. The operator + can be used to concatenate two values of the type string. For the operator + to work with the string data type, one of the operands of + must be a string variable.

1. Relational operators, discussed in Chapter 4, can be applied to the string type.

1. In a string, the position of the first character is 0, the position of the second character is 1, and so on.

1. The length of a string is the number of characters in the string.

1. In C++, [] is called the array subscript operator.

1. To access an individual character within a string, use the array subscript operator together with the position of the character.

1. The string type contains functions such as at, append, clear, compare, erase, find, find_first_of, find_first_not_of, insert, length, replace, size, substr, and swap to manipulate strings. These functions are described in Table 7-1.

## Key Terms 
* **Function**: A named block of code that performs a specific task or operation. Functions can accept parameters, execute statements, and optionally return a value.
* **Parameter**: A variable declared in a function's parameter list, used to pass values to the function when it is called.
* **Return Type:** The data type of the value returned by a function, specified before the function name in its declaration.
* **Return Statement:** A statement within a function that returns a value to the caller and exits the function.
* **Function Call:** The act of invoking a function to execute its code, providing arguments as inputs if required.
* **Enumeration (Enum):** A user-defined data type used to define a set of named integral constants (enumerators) representing related values.
* **Enumerator**: An individual constant within an enumeration type, defined using the enum keyword.
* **Underlying Type:** The integral type (e.g., int, char) associated with an enumeration type's values, determined by the compiler unless specified explicitly.
* **Enum Declaration:** The syntax for defining an enumeration type, typically done using the enum keyword followed by a list of enumerator names.
* **Enum Variable:** A variable of an enumeration type, capable of holding one of the enumerator values defined within the enum.

## References
C++ Programming: From Problem Analysis to Program Design by D.S. Malik
