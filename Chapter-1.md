# Basic Elements of C++

## Objectives
After completing this chapter students will be able to:
1. Identify basic components of a C++ program, including functions, special symbols, and identifiers
2. Classify simple data types and use them in assignment statements
3. Use arithmetic operators, precedence, and expressions
4. Create assignment and input statements and the use of variables within statements.
5. Differentiate between type conversion and type casting
6. Develop output results using output statements
7. Identify syntax errors and debugging techniques
8. Write a basic C++ program

## Introduction 
In this chapter, you will learn the basic elements and concepts of the C++ programming language to create C++ programs. In addition to giving examples to illustrate various concepts, we will also show C++ programs to clarify these concepts. 

## Basics of C++
As individuals begin their quest to master C++, they come across essential elements that lay the groundwork for this robust and flexible programming language. In this segment, we delve into four primary aspects of C++: comments, reserved words, identifiers, and functions.

### Comments 
In programming languages, comments hold significant importance as they offer a way for developers to add annotations to their code. These lines of text, not executed by the compiler during code compilation, are designed for human readers. Comments function as documentation, clarifications, or prompts for understanding the code's logic, facilitating better project comprehension, maintenance, and collaboration among developers.

C++ allows for two styles of comments. The first is the in-line comment. This is done by using // (two forward slashes). All text following this symbol is part of the comment.

For example:

```cpp
cout << "7 + 8 = " << endl; //prints: 7 + 8 = 15
```

The second type of comment allowed is multiple-line comments. This allows the programmer to write longer comments that cover multiple lines. Multiple-line comments are enclosed in /* and */.

For example:

```cpp
/*
    You can include comments that can 
    occupy several lines 
*/
    
```

### Reserved Words (Keywords)
Reserved words, commonly referred to as keywords, play a crucial role in the C++ programming language by having predefined meanings. These words serve as the fundamental elements for constructing instructions, expressions, and various program structures. Due to their specific purposes, programmers are restricted from using them as identifiers, such as variable or function names, in their code. A comprehensive grasp of these reserved words is vital as they establish the foundation of C++ syntax and define the grammar of the language.

For example:

```cpp
if, char, bool, else, compl, const, double, return, short, namespace 
```

### Identifiers 
In the realm of programming, identifiers hold significant importance as they serve as the designated names for various elements within a codebase. In C++, these identifiers encompass variables, functions, classes, objects, labels, and user-defined types. Essentially, they act as labels that empower programmers to refer to and manage these entities seamlessly within their code. This segment strives to offer an in-depth comprehension of C++ identifiers, delving into their regulations, optimal approaches, and the pivotal role they play in shaping the structure and clarity of a C++ program.

#### Rules for Naming Identifiers 

C++ enforces specific guidelines and conventions when it comes to naming identifiers, aiming to uphold code clarity and mitigate conflicts. Adhering to these rules is crucial for ensuring readability and cross-platform compatibility. The key principles for naming C++ identifiers include:

1. Permissible Characters: Identifiers can comprise letters (both uppercase and lowercase), digits, and underscores (_). The initial character must be a letter or an underscore. It's important to note that C++ is case-sensitive, distinguishing between identifiers like "myVariable" and "MyVariable."

2. Reserved Keywords: Certain words in C++ are reserved keywords and carry predefined meanings. Examples include "if," "else," "while," "class," "int," and "return." These keywords cannot be used as identifiers.

3. Length Considerations: While identifiers can be of any length, most compilers focus on the first few characters. Compiler limitations often restrict identifier length, commonly to 255 characters.

4. Unicode Support: C++ embraces Unicode characters in identifiers, offering a broader spectrum for naming possibilities.

5. Namespace Scope: Identifiers within a namespace scope should be unique to prevent naming conflicts. Opt for descriptive names that convey the content or purpose of the entity.

6. Global Scope: Exercise caution when using identifiers in the global scope to avoid naming clashes in extensive projects. Consider employing unique prefixes or namespaces for global identifiers.

7. Underscore Convention: Identifiers starting with an underscore followed by a capital letter (e.g., "_MyIdentifier") and those with two consecutive underscores are reserved for the compiler and standard library. To prevent unintended behavior, it's advisable to steer clear of using such names.

#### Best Practices for Naming Identifiers 

1. Descriptive Naming: Opt for meaningful and clear names for variables, functions, and classes. For example, instead of using "n," go for something like "numStudents" to convey the purpose or content accurately.

2. CamelCase Convention: For identifiers with multiple words, adhere to the CamelCase convention. Capitalize the first letter of each word, as seen in "calculateGrossSalary."

3. Avoiding Abbreviations: Reduce the reliance on abbreviations to enhance clarity for other developers. Prioritize readability by using full words. For instance, favor "calculate" over unclear abbreviations.

4. Consistency in Naming Style: Maintain a uniform naming style across the entire codebase. This practice simplifies the code review process and facilitates a better understanding of the code by different developers.

5. Steer Clear of Hungarian Notation: Refrain from using prefixes that indicate the data type of a variable. The use of Hungarian Notation, like "i" for integers or "sz" for zero-terminated strings, is discouraged for improved code readability.

6. Action-Indicative Function Names: When naming functions, incorporate verbs to signify actions. Examples include "calculate," "initialize," or "print." This approach helps in understanding the purpose and behavior of functions.

Identifiers serve as the fundamental elements of a C++ program, enabling developers to establish, refer to, and manage different entities. Adhering to naming conventions and optimal practices for identifiers empowers programmers to craft code that is clear, understandable, and easier to maintain, reducing the likelihood of errors. Investing effort in selecting meaningful and descriptive names for identifiers contributes significantly to the resilience and comprehensibility of your codebase, fostering effective collaboration within a team.

### Review Questions 

1. True/False: char is a reserved word/keyword in C++ programming.

2. True/False: float is a valid identifier name.

3. Does // or /* allow multiple line comments?

*Answers: 1. True 2. False 3. /* * 

## Data Types 

In the realm of C++, data types serve as fundamental constructs, shaping the nature of information that a variable can encompass. These entities hold significant sway in dictating the size and characteristics of variables as a program unfolds. A comprehensive grasp of the foundational data types in C++ proves indispensable for crafting code that is not only proficient but also adaptable across different platforms, fostering a resilient and error-resistant programming experience. Delving into this section unveils a thorough examination of the elemental data types at one's disposal in C++, shedding light on their memory structures and the spectrum of values within their grasp.

### Simple Data Types 

C++ encompasses a variety of fundamental data types that can be broadly classified into distinct groups:

1. Integer Types:
      - **int**: Signifies signed integers and typically occupies 4 bytes on most systems. Its value range spans approximately from -2 billion to +2 billion.
      - **short**: Denotes short signed integers and utilizes 2 bytes. The range typically lies between -32,768 to +32,767.
      - **long**: Represents long signed integers and utilizes 4 bytes (or 8 bytes on specific systems). The range depends on the platform but is usually larger than that of int.
      - **long long**: Represents very long signed integers and utilizes 8 bytes. Introduced in C++11, it offers a broader range than long.

2. Floating-Point Types:

      - **float**: Represents single-precision floating-point numbers using 4 bytes. It provides an approximate precision of 7 decimal digits.
      - **double**: Signifies double-precision floating-point numbers with an allocation of 8 bytes. It offers an approximate precision of 15 decimal digits.
      - **long double**: Denotes extended-precision floating-point numbers, surpassing the precision of double.

3. Character Types:

      - **char**: Represents a single character and occupies 1 byte. It can store ASCII characters or small integer values.

4. Boolean Type:

      - **bool**: Represents a Boolean value, which can be either true or false. Internally, it uses 1 byte to store the value.

### Floating-Point Data Types

In this section, we'll explore how C++ addresses decimal numbers through the use of the floating-point data type. To represent decimal numbers, C++ uses a form of scientific notation called floating-point notation. C++ offers three data types for handling decimal numbers: float, double, and long double. Similar to integral data types, these numeric types vary in the range of values they can represent.

The range of values for the data types float and double is contingent upon the specific system being used. To determine these limits on a particular system, one can refer to the compiler's documentation or execute a program provided in Appendix F (Header File **cfloat**). In addition to the range of values, there exists another distinction between the float and double data types. The float type has a maximum precision of six or seven significant digits, representing the number of decimal places. Conversely, the double type can accommodate values with a precision of up to 15 significant digits.

Precision refers to the maximum number of significant digits in a numerical value. In certain contexts, floating-point values are categorized as either single precision or double precision. The term "single precision" is often associated with float values, while "double precision" is used for values of type double. When working with decimal numbers, the float type is generally sufficient for most applications. However, if you require precision beyond six or seven decimal places for increased accuracy, the double type can be utilized.

For example:

```cpp
7.9927347E1
```

This example shows the number in floating point notation.

### Review Questions

1. What data type represents a Boolean value?

2. How many data types are offfered for handling decimal numbers?

3. True/False: char represents a single character and occupies 1 byte

*Answers: 1. bool 2. three 3. True*

## Data types, Variables, and Assignment Statements 

### Data Types
Having gained an understanding of identifier definition, data types, and the concept of variables, let's delve into the process of declaring a variable. When declaring a variable, it involves more than just assigning a name to it; we also explicitly indicate the type of data that the variable is capable of storing. The general syntax for this is 

```cpp
dataType identifier;
```
### Variables

For example:

```cpp
int age;
double tax rate;
char grade;
```

In the initial declaration, we instruct the system to reserve a block of memory comprising four bytes for the storage of an integer value. This allocated memory space is then assigned the identifier "counter," effectively creating a variable capable of holding an integer value. Likewise, the variable "tax rate" is defined to accommodate a value of type double, while the variable "grade" is designed to store a value of type char. Essentially, we are specifying distinct variables with specific data types and memory allocations.

### Assignment Statements 

A common method to store a value in a variable involves using an assignment statement. This statement follows a specific structure:

```cpp
variable = expression;
```

In C++, the assignment operator, denoted by "=", is used to evaluate an expression and assign its value to a variable.

For example:

```cpp
counter = 7;
tax rate = 0.07;
grade = 'B';
```

The first statement stores 7 in the variable counter, the second statement stores 0.07 in tax rate, and the third statement stores the character 'B' in grade.

### Review Questions

1. True/False: Declaring a variable indicates the type of data that the variable is capable of storing.

2. What operator is used to evaluate an expression and assign its value to a variable.

3. True/False: "counter" is an identifier capable of storing integer numbers.

*Answers 1. True 2. "=" 3. True*

## Arithmetic Operators, Operator Precedence, and Expressions 

In C++, arithmetic operators play a crucial role as essential elements that empower programmers to execute diverse mathematical computations on numeric data types. These operators serve as tools for manipulating variables and constants, facilitating the solution of mathematical problems and the execution of numerical calculations within a program. This segment delves into the prevalent arithmetic operators found in C++, illustrating their application and demonstrating the construction of expressions to carry out intricate mathematical operations.

C++ provides the following arithmetic operators:

1. Addition (+): Combines two values to produce their sum.
2. Subtraction (-): Takes the right operand away from the left operand, resulting in the difference.
3. Multiplication (*): Multiplies two values, yielding the product of the operands.
4. Division (/): Divides the left operand by the right operand, giving the quotient.
5. Modulus (%): Computes the remainder when the left operand is divided by the right operand.

### Order of Precedence 

In C++, the order of operations is determined by operator precedence rules when multiple arithmetic operators are present in an expression. The operators *, /, and % hold a higher precedence compared to + and -. It's worth noting that among themselves, * , /, and % share the same level of precedence, as do + and -.

When operators share the same level of precedence, the evaluation is carried out from left to right. To enhance clarity and avoid ambiguity, you have the option to employ parentheses to group specific arithmetic expressions. This allows you to explicitly define the order in which operations should be performed, ensuring the desired outcome of the expression.

For example: 

```cpp
int result = 7 + 2 * 3; // result will be 13 (2 * 3 is evaluated first, then added to 7)
int anotherResult = (7 + 2) * 3; // anotherResult will be 27 (7 + 2 is evaluated first, then multiplied by 3)
```

### Expressions

In C++, expressions are constructed by combining variables, constants, and operators. These expressions enable programmers to tackle intricate mathematical challenges within their code using arithmetic operators.

For example:

```cpp
// Area of a rectangle
int length = 2, width = 4;
int area = length * width;

// Celsius to Fahrenheit conversion
double celsius = 22.0;
double fahrenheit = (celsius * 9.0 / 5.0) + 32.0;
```

In the first example, the expression `length * width` calculates the area of a rectangle. In the second example, the expression `(celsius * 9.0 / 5.0) + 32.0` converts a temperature in Celsius to Fahrenheit.

### Mixed Expressions 

A mixed expression is characterized by the inclusion of operands with diverse data types, combining both integers and floating-point numbers. The following expressions serve as illustrations of mixed expressions:

An example is: 

```cpp
3 + 4.5
7 / 3 + 2.3
2.8 * 3 - 4.2 + 7.9 / 2
```

When dealing with mixed expressions in C++, certain rules come into play to determine how the evaluation takes place. These rules apply based on the types of operands involved:

1. **Same Operand Types:**

    * If the operator in a mixed expression has operands of the same type (either both integers or both floating-point numbers), the operator is evaluated according to the type of operands.
     * Integer operands result in an integer outcome.
     * Floating-point operands result in a floating-point outcome.

2. **Mixed Operand Types:**

    * If the operator in a mixed expression involves operands of different types (one integer and one floating-point number), the integer operand is temporarily converted into a floating-point number (with a decimal part of zero) during calculation. 
     * The operator is then evaluated, and the result is a floating-point number.

3. **Expression Evaluation:**

   * The entire expression is evaluated following precedence rules. Multiplication, division, and modulus operators take precedence over addition and subtraction operators.
    * Operators with the same level of precedence are evaluated from left to right.
    * Parentheses can be used for grouping to enhance clarity.

In summary, when evaluating a mixed expression in C++, focus on one operator at a time, adhering to precedence rules. If the operator involves operands of the same data type, apply Rule 1(a) accordingly. If the operator has mixed operand types, convert the integer operand to a floating-point number before evaluation. The examples provided illustrate how to apply these principles in practice.

### Review Questions 

1. How many types of operands are there

2. True/False: A mixed expression has both integers and floating-point numbers.

3. Which Operator has the highest precedence 
     a) ()
     b) +
     c) /
     
*Answers: 1. Three 2. True 3. "()"*

## Type Conversion (Casting)

In the earlier section, you gained insight into the process of evaluating arithmetic expressions in C++. When dealing with operators that involve operands of different types, the integer value is converted to a floating-point value, with the decimal part set to zero. This automatic conversion of one data type to another is referred to as implicit type coercion. The examples in the previous section demonstrated that if you're not cautious about data types, implicit type coercion can lead to unexpected outcomes.

To address this issue, C++ offers a mechanism for explicit type conversion through the use of a cast operator. This operator, also known as type conversion or type casting, is structured as follows:

```cpp
static_cast<dataTypeName>(expression)
```

Initially, the expression undergoes evaluation, and subsequently, its outcome is transformed into a type determined by dataTypeName. In C++, the term static_cast is reserved for this purpose. In the process of converting a floating-point (decimal) number to an integer through the cast operator, the approach involves discarding the decimal portion of the floating-point number.

To incorporate the result of one expression into another, it is essential to store the initial expression's value. This practice is crucial for various reasons. Complex expressions may demand substantial computational resources and time for evaluation. By computing and preserving these values for future reference, not only does it optimize program execution speed, but it also mitigates the risk of potential typographical errors. In the context of C++, expressions undergo evaluation, and without saving the outcome, it becomes inaccessible for subsequent calculations. In essence, unless the value is stored, the output of an expression cannot be harnessed for future computations.

### Review Questions

1. True/False: Type conversion is converting a floating-point number into a integer number.

2. Yes/No: is "static_cast" a reserved word?

3. What is it called when one data type is automatically converted to another?

*Answers: 1. True 2. Yes 3. Implicit Type*

## String Type

The string data type in programming is not an inherent, built-in type like the simple data types discussed earlier. Instead, it is a user-defined data type that requires accessing program components from the library, a topic that will be covered later in this chapter. It's worth noting that the string data type is part of the ANSI/ISO Standard C++.

A string is a series of characters, which can be empty or contain zero or more characters. In C++, strings are represented within double quotation marks. When a string has no characters, it is referred to as a null or empty string. Here are some examples of strings, with the acknowledgment that "" represents the empty string.

Example: 

```cpp
"Jalen Hughes"
"Chloe"
""
```

In a string, each character holds a specific position, with the first character positioned at 0, the second at 1, and so forth. The length of a string is the total count of characters within it, and this count includes any spaces present in the string.


Strings are a versatile and intricate data type, offering more than just a storage space for textual information. They come equipped with a range of operations that allow for string manipulation. These operations include determining the length of a string, extracting specific segments from a string, and comparing different strings.

### Review Questions 

1. True/False: Strings are not a data type.

2. Yes/No: Are strings a series of characters?

3. True/False: You can have an empty string

*Answers: 1. False 2. Yes 3. True*


### Saving and Using the Value of an Expression 

In programming, you can save the result of an expression for later use by following these steps: 
*Declare a Variable: Choose the appropriate data type for your result (e.g., int for integers) and declare a variable. For instance, if your expression yields an integer, declare an int variable. 
*Assign Value: Use an assignment statement to assign the result of your expression to the declared variable. This stores the expression's value in the variable. 
*Utilize the Variable: In subsequent expressions or calculations, use the variable instead of repeating the entire expression. This improves efficiency and avoids redundancy. 
*For example, consider calculating the values of expressions -b + (b^2 - 4ac) and -b - (b^2 - 4ac) and storing them in variables x and y. To avoid redundant calculations of b^2 - 4ac, you can first calculate this expression, save it in a variable (let's say d), and then use d in both expressions. 
*Remember that initializing a variable (assigning it an initial value) is crucial before using it in an expression. You can declare and initialize a variable simultaneously. This understanding is fundamental in programming. 


### Declaring and Initializing Variables 

In C++ programming, when you declare a variable, it doesn't automatically have a meaningful value like 0, unlike some other programming languages. Instead, the variable holds whatever value was in the memory location assigned to it, which could be random and unpredictable (referred to as "garbage"). In the computer's memory, data is represented as sequences of 0s and 1s (bits). When you declare a variable but don't explicitly assign a value, it retains whatever bits were previously stored in that memory location. If you use this uninitialized variable in an expression, it can lead to incorrect results.To avoid this, C++ allows you to initialize variables when you declare them. Initialization means assigning a specific value to the variable right from the start. For instance, you can declare and initialize an integer variable named 'first' with the value 13, and another named 'second' with the value 10 in a single statement. While not all variables need to be initialized during declaration, it's essential to initialize a variable before using it in any calculations or expressions to ensure accurate and reliable results in your program. 


### Input (Read) Statement 

In C++ programming, you can take input from the user through the keyboard using the cin statement and the >> operator. This process is known as an input or read statement. The standard input device, in most cases, is the keyboard, and this interactive interaction is common in programs. For instance, if you have a variable 'miles' of type double, you can use cin >> miles to get input from the user and store it in the 'miles' variable. Similarly, you can input multiple values on a single line, separated by spaces or tabs. 
An example program illustrates taking input for variables like 'feet,' 'inches,' 'firstName,' 'lastName,' 'age,' and 'weight.' The program prompts the user to enter values, reads, and stores them appropriately. It uses the >> operator to handle different types of input, including strings, integers, and doubles. It's important to note that during execution, values entered in a line should be separated by at least one blank or tab. This approach allows for interactive and dynamic input from users, enhancing the versatility of C++ programs.  

### Variable Initialization 

In C++ programming, you can initialize variables using two methods: assignment statements and input (read) statements. Assignment statements set a specific value for a variable within the code, while input statements, using cin and >> operator, allow users to interactively input values during program execution. When variables are initialized by assignment statements, their values remain constant unless the code is manually edited and recompiled. On the other hand, using input statements makes the program more versatile, as users can input different values each time the program runs. It's essential to note that C++ doesn't automatically initialize variables, and some may need explicit initialization using assignment or input statements. Ignoring proper initialization may lead to warning messages during compilation and potential abnormal program termination. Example 2-19 provides a detailed illustration of initializing variables through assignment and input statements. It demonstrates how to walk through the program, executing each statement and updating variable values accordingly. This process is a valuable debugging technique to understand and correct unexpected program results. Additionally, the example highlights the use of explicit type casting and warns about potential issues when assigning floating-point values to integer variables without proper casting. 

### Review Questions 
1) If a variable is used in an expression, the expression would yield a meaningful value only if the variable has first been initialized. T/F (T)
2) cout << is whats used to input data in a program T/F (F)
3) A keyboard is a output device. T/F (F)

Increment and Decrement Operators: operators used to fasten when counting statements.  
Increment operator (++): increases the value of a variable by 1, and their types are pre-increment: ++variable and post-increment: variable++. Decrement operative (- -) decreases the value of a variable by 1 (Pre-decrement: - - variable and post-decrement: variable- -).  The difference between pre- and post- increment statements is that this incrementing is only classified when it occurs before or after the assignment. 
Output
Output statement- displayed when using the following syntax “count << expression < expression. “<<“is a stream insertion operator, and with generating output with count follows two rules:
1.	Expression evaluated and value placed at the insertion point on the output device.
2.	To format the output, there needs to be a manipulator such as endl, which causes the coder to spawn to the next line. 
In an output statement, a string or an expression involving only one variable or a single value evaluates to itself. Char values or values of a string only have an output of the value, but not the quotations unless included in the output. “\” is called escape character and “\n” is called the new line escape sequence. ALL VARIABLES MUST BE PROPERLY INITIALIZED because C++ doesn’t automatically initialize variables and won’t make sense. Input Variable table (77) Header file is needed when using cin and cout.
Preprocessor Directives: Few operations are explicitly defined in C++, so the rest are stored in libraries. They all have a name and referred to by a header file. These are needed to tell the computer where to find the code to unlock the additional functions. 
Program used to process these directives is called a preprocessor. These directives are commands provided to the Preprocessor to manipulate the text of the program before it is compiled, and they all start with #. Since they are not C++, they do not end with semicolons. To input a Preprocessor directive in a program, you need to input #include, and then the file name. These preprocessor directives are inputted in the first line, so it can be used throughout the whole program.
Namespace and using cin and cout in a Program

Creating a C++ Program
All statements are placed within the main function except for declaring named constants.  In the syntax of the function main, each statement is usually a declarative statement or an executable statement. “Return 0” must be included in the main function and the last statement.Preprocessor directives tell the compiler which header files to include in the program. Program contains the statements to develop output. Together, the make the source code, which must be saved in a file with the extension .cpp. Source [code] file – file containing the source code. Compiler generates object code, with a .obj file extension, and when linked to the executable code, it’s saved in a with an extension called .exe, yet all are system dependent.  

The general format of the main function is the heading and body. The first line is “int main ()” and this is the called the heading. The curly braces contain the body of the function which holds two types of statements: 
•	Declaration- used to declare things such as integers (int), floating numbers (double), etc.
•	Executable statements-  Conducts calculations, outputs, accepts inputs and manipulates data. 


Debugging: Understanding and Fixing Syntax Errors: Typing a program is bound to result in errors. Majority of these are due to syntax errors. 

Program Style and Form: It’s important to make a well-structured C++ program to make it easier to manipulate, understand, and use. Also, there are certain rules for the language in order for it to function accordingly. The code must abide by the syntax rules in terms of ethics, clarity, and technical legalities. It must also contain the function main and support the language’s semantics.
SYNTAX identifies what is legal and illegal both grammatically and semantically according to the language being used. Errors in syntax are detected during compilation. Some errors commonly found include a missing semicolon or other punctuation, or using a variable that has yet to be declared. Also, errors can cause other statements to be misinterpreted ss well. Syntax prevents these errors from spreading by finding them and hinting to the users where they are and how to fix them.
Blanks are separators for numbers when inputting data, reserved words, and identifiers from each other and from other symbols. Blanks must never appear within a reserved word or identifier.
Special types of punctuation are used uniquely to separate statements. Semicolons end all C++ statements and are also known as statement terminators. Curly braces are not included as C++ statements. Brackets are delimiters, whose job is to separate their function from other parts of the program. Lastly, commas are used to separate items in a list, much like in a sentence. Semantics are a set of rules that gives meaning to a language, similar to the order-of-precedence rules for arithmetic operators.
*Input example of different semantics but same values. *
Self-documenting lines of code by naming identifiers makes commenting less necessary because the purpose is outlined for you. Additionally, make sure to watch out for run-together words and phrasings as they cause less clarity and conciseness, so it's important to combine them together to clear up statements. Prompt lines are executable statements that inform the user what to do. Whenever an input is needed, there must be well-detailed prompt lines to describe the action needed. Statements must be able to be understood and interpreted correctly by others, so the following should be expressed: comments, references, and explanation. There's versatility and freedom when coding because you can write a statement differently if you abide by the syntax rules like correctly formatting blanks and punctuation. Documentation must be able to be understood by others, so the following should be expressed: comments, references, and explanations.
Form and Style
There’s versatility and freedom when coding because you can write a statement in different ways as long as you abide by the syntax rules such as including a blank between values causes an error. Input example of a clustered compiler and more indented program. Basic formality rules: 
3.	One variable per line
4.	Put a space before and after an operator.
5.	Keep the indents when using an IDE.

More on Assignment Statements: There are simple assignment statements- (input definition) and compound assignment statements, which is essentially a more concise version of writing simple assignment statements. 
In addition to the five arithmetic operators +, -, *, /, and %, C++ also has compound operators which are: +=, *=, and %=. *Input example showing difference of different operators*. Note- A converted assignment can be converted to a simple assignment, but a simple assignment can’t be converted to a compound assignment.


## Key Terms

algortihm 
   : a process or set of rules to be followed in calculations or other problem-solving operations, especially by a computer
   
String
   : a series of characters, which can be empty or contain zero or more characters.
 
Expressions
   : enable programmers to tackle intricate mathematical challenges within their code using arithmetic operators.

Identifiers
   : serve as the designated names for various elements within a codebase.
   
Null/Empty String
   : a string containing no characters
   
Simple Data type
   : A data type is called simple if the variable or named constant of that type can store only one value at a time.

## Programming Exercises

Write a function in a programming language of your choice that checks whether a given string is a palindrome or not. A palindrome is a word, phrase, number, or other sequence of characters that reads the same forward and backward (ignoring spaces, punctuation, and capitalization).

For example:

"level" is a palindrome.
"hello" is not a palindrome.
Your function should return True if the input string is a palindrome and False otherwise. Feel free to include additional features or constraints as you see fit.

## References 

Malik, D. S. (2018). C++ programming: From problem analysis to program design. Cengage Learning.
