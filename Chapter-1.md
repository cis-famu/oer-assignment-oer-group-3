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
