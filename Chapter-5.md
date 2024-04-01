# User-defined Functions

## Objectives

1. Understanding the Purpose of Functions:

* A function is a reusable block of code that performs a specific task.
* Functions are used in programming to organize code, promote code reusability, improve modularity, and provide abstraction.

2. Benefits of Using Functions:

* Code Reusability: Write code once and use it multiple times.
* Modularity: Break down programs into smaller, manageable units.
* Abstraction: Hide implementation details and provide an interface for interaction.

3. Function Syntax and Structure:

* Return Type: Specifies the type of value the function returns (void for no return).
* Function Name: Identifier used to call the function.
* Parameters: Input values passed to the function for processing.
* Function Body: Contains the code defining the function's behavior.
* Return Statement: Used to return a value from the function (for value-returning functions).

4. Void vs. Value-Returning Functions:

* Void Function: Returns no value (void return type), used for tasks without returning results.
* Value-Returning Function: Returns a value using the return statement.

5. Demonstrating the Return Statement:

* Example: int add(int a, int b) { return a + b; }

6. Function Prototypes:

* Declare function name, return type, and parameters without defining the body.
* Informs the compiler about the function before it is called.

7. Writing Basic Functions in C++:

8. Calling Functions:

* Functions can be called from within other functions or the main function, passing arguments correctly.
* Arguments can be passed by value or by reference.

9. Passing Arguments:

* By Value: Copies the argument's value into the function's parameter.
* By Reference: Passes a reference to the argument's memory location.

10. Function Overloading:

* Define multiple functions with the same name but different parameter lists.
* Provides flexibility and readability in code.

## Introduction
In C++, user-defined functions play a fundamental role in structuring programs by encapsulating specific tasks or functionalities into reusable blocks of code. These functions are created by the programmer to perform custom operations, enhance code readability, and promote modularity. By defining user-defined functions, programmers can break down complex problems into smaller, manageable units, making the codebase easier to understand, maintain, and debug. These functions can have various return types, accept parameters, and be called from different parts of the program, offering flexibility and efficiency in software development. Overall, user-defined functions empower programmers to write more structured and organized code, leading to improved software quality and development productivity.

### Value and Reference Parameters and Memory Allocation
When a function is invoked, the computer allocates memory for its formal parameters and local variables within the function's data area. For value parameters, the value of the actual parameter gets copied into the memory assigned to the corresponding formal parameter. However, in the case of reference parameters, the formal parameter contains the address (or pointer) of the actual parameter's memory location. This means that both the formal and actual parameters point to the same memory location. Therefore, any modifications made to the formal parameter directly affect the data stored at that memory location, resulting in permanent changes to the actual parameter's value during program execution.

For Example:
```cpp
#include <iostream>

// Using namespace std for convenience
using namespace std;

// Function that modifies the value using reference parameter
void modifyValue(int &num) {
    num += 10; // Add 10 to the original value
}

int main() {
    int number = 5;
    
    cout << "Original value: " << number << endl;
    
    // Call the function with the original value as argument
    modifyValue(number);
    
    cout << "Modified value: " << number << endl;

    return 0;
}
```
In this example:

* The modifyValue function takes an integer reference parameter num.
* Inside modifyValue, num refers directly to the original variable number from main.
* When modifyValue is called with number as an argument, it modifies the original value of number by adding 10 to it.
* After calling modifyValue, the modified value of number is printed in main, demonstrating that changes made by the function affect the original variable.

### Review Questions
1. Yes/No: Can a function return a reference to a variable or data structure?
2. True/False: Using reference parameters creates a direct connection between the actual and formal parameters, as they both point to the same memory location. 
3. Question: What happens when a function with a value parameter is called?

***Answers**: 1. **Yes** 2. **True** 3. **When a function with a value parameter is called, the value of the actual parameter is copied into the memory cell of its corresponding formal parameter within the function's data area.**
*
### Reference Parameters and Value-Returning Functions
While it's possible to use reference parameters in a value-returning function, it's generally not recommended for good programming practices. Value-returning functions are designed to return a single value using the return statement. If a function requires returning multiple values, it's better to change it to a void function and utilize reference parameters to return those values. This approach aligns with clean coding principles and helps improve code readability and maintainability.

For Example:
```cpp
#include <iostream>

// Using namespace std for convenience
using namespace std;

// Function to calculate both sum and product of two numbers
void calculateSumAndProduct(int a, int b, int &sum, int &product) {
    sum = a + b;      // Calculate sum
    product = a * b;  // Calculate product
}

int main() {
    int num1 = 5, num2 = 7;
    int resultSum, resultProduct;

    // Call the function to calculate sum and product
    calculateSumAndProduct(num1, num2, resultSum, resultProduct);

    cout << "Sum: " << resultSum << endl;
    cout << "Product: " << resultProduct << endl;

    return 0;
}
```
In this example:

* The calculateSumAndProduct function takes two integers a and b as input parameters and two integer reference parameters sum and product.
* Inside the function, it calculates the sum of a and b and assigns it to sum, and calculates the product of a and b and assigns it to product.
* The function does not return anything (void), but it modifies the values of resultSum and resultProduct in the main function using reference parameters.
* Finally, the main function prints the calculated sum and product values.

### Review Questions
1. True/False: Value-returning functions with clear return statements provide a straightforward way to communicate the output of the function. 
2. True/False: Using reference parameters in value-returning functions can make the code less readable and harder to understand, as it may not be immediately clear that the function is modifying external variables.
3. Question: In what scenarios would using reference parameters in a value-returning function be appropriate?

***Answers**: 1. **True** 2. **True** 3. **Using reference parameters in a value-returning function may be appropriate in rare cases where modifying external variables directly within the function is a critical requirement and well-documented.***
### Scope of an Identifier
In C++, identifiers like variable or function names are declared within specific scopes, such as a function heading or within a block of code. However, it's important to note that not all identifiers can be accessed from anywhere in the program. Access to an identifier is governed by scope rules, which define where in the program an identifier is visible or accessible. In simpler terms, the scope of an identifier determines where it can be used or referenced within the code. Identifiers must adhere to these scope rules for proper access and usage throughout the program.

```cpp
#include <iostream>

using namespace std;

int globalVar = 10;

void func1() {
    int localVarFunc1 = 20;
    
    cout << "Inside func1 - Global Variable: " << globalVar << endl;
    cout << "Inside func1 - Local Variable: " << localVarFunc1 << endl;
}

void func2() {
    int localVarFunc2 = 30;

    cout << "Inside func2 - Global Variable: " << globalVar << endl;
    cout << "Inside func2 - Local Variable: " << localVarFunc2 << endl;
}

int main() {
    cout << "Inside main - Global Variable: " << globalVar << endl;

    func1();
    func2();

    return 0;
}
```
In this example:

* globalVar is a global variable accessible throughout the program.
* localVarFunc1 and localVarFunc2 are local variables within the respective functions' scopes (func1 and func2).
* Attempts to access local variables from outside their respective functions (e.g., from main) will result in compile-time errors because of scope rules.
* Global variables can be accessed from any part of the program, while local variables are limited to their respective function scopes.

### Review Questions
1. Question: What are scope rules in C++?
2. True/False: The scope of an identifier dictates where it can be used or referenced within the program.
3. Yes/No: Can identifiers from different scopes have the same name?

***Answers**: 1. **Scope rules in C++ define where an identifier (such as a variable or function name) is visible or accessible within the code. They determine the range or extent of an identifier's visibility and usage**. 2. **True** 3. **Yes*** 
### Global Variables, Named Constants, and Side Effects
While it's possible to have global variables in a C++ program, relying solely on them for all variables may seem convenient as it avoids concerns about variable visibility in functions. However, excessive use of global variables can lead to unintended consequences. If multiple functions rely on the same global variable and errors occur, pinpointing the source of the problem becomes challenging. Issues arising from global variables in one part of the program might be misinterpreted as problems originating from elsewhere. This lack of localized context can make debugging and troubleshooting complex and time-consuming.

For Example:
```cpp
#include <iostream>

using namespace std;

int globalVar = 10;

void modifyGlobalVar() {
    globalVar += 5; 
}

void printGlobalVar() {
    cout << "Global Variable: " << globalVar << endl;
}

int main() {
    
    cout << "Initial Global Variable: " << globalVar << endl;
    
    modifyGlobalVar();

    printGlobalVar();

    return 0;
}
```
In this example:

* globalVar is a global variable accessible throughout the program.
* The modifyGlobalVar function modifies the value of globalVar by incrementing it by 5.
* The printGlobalVar function simply prints the value of globalVar.
* In the main function, modifyGlobalVar is called to modify globalVar, and then printGlobalVar is called to print the modified value.
* Running this code will demonstrate how changes made to a global variable by one function can affect its value across the program, potentially leading to unexpected behavior or difficulties in identifying the source of problems related to the global variable.

### Review Questions
1. Question: What are global variables in C++?
2. True/False: Global variables can be accessed and modified by any part of the program, simplifying variable visibility concerns within functions.
3.  True/False: When multiple functions depend on the same global variable, errors or unexpected behavior in one function can affect others.

***Answers**: 1. **Global variables in C++ are variables declared outside of any function or block, making them accessible from anywhere in the program.** 2. **True** 3. **True***
### Static and Automatic Variables
The variables discussed so far have followed two simple rules:

1. Memory for global variables remains allocated as long as the program executes.
 
2. Memory for a variable declared within a block is allocated at block entry and deallocated at block exit. For example, memory for the formal parameters and local variables of a function is allocated when the function is called and deallocated when the function exits.

A variable for which memory is allocated at block entry and deallocated at block exit is called an automatic variable. A variable for which memory remains allocated as long as the program executes is called a static variable. Global variables are static variables, and by default, variables declared within a block are automatic variables. You can declare a static variable within a block by using the reserved word static. The syntax for declaring a static variable is:

For Example:
```cpp
#include <iostream>

using namespace std;

void incrementCount() {
    static int count = 0; 

    count++;
    cout << "Count: " << count << endl;
}

int main() {
    
    incrementCount();  
    incrementCount();  
    incrementCount();  

    return 0;
}
```
In this example:

* We have a function incrementCount() that contains a static variable count.
* The static variable count is initialized to 0 and retains its value between function calls.
* Each time incrementCount() is called, count is incremented by 1 and its value is displayed.
* As a result, the output shows the incremented count value with each function call.
* The key point to note here is that the static variable count maintains its value between function calls, unlike automatic variables that get reinitialized each time the function is called.

### Review Questions
1. Question: What is the term used to describe variables with memory allocated at block entry and deallocated at block exit?
2. True/False: Memory for variables declared within a block, such as formal parameters and local variables of a function, is allocated when the block is entered and deallocated when the block exits.
3. True/False: Memory for global variables remains allocated as long as the program executes, making them accessible from anywhere in the program.

***Answers**: 1. **Variables with memory allocated at block entry and deallocated at block exit are called automatic variables in C++.** 2. **True** 3. **True***
### Debugging: Using Drivers and Stubs
In previous chapters, you've learned the approach of breaking down a problem into smaller, manageable parts by writing functions. These functions are then tested and debugged independently to ensure they work correctly. To test a function, you can write a separate program known as a "driver program." This driver program is responsible for testing the functionality of individual functions.

In complex programs, multiple functions are often used, each solving specific subproblems. However, there are situations where one function's results are needed as input for another function. In such cases, the dependent function cannot be adequately tested in isolation because it relies on the correct functioning of another function.

For Example:
```cpp
#include <iostream>

using namespace std;

int square(int num) {
    return num * num;
}

int sum(int a, int b) {
    return a + b;
}

int main() {

    int number = 5;
    int squared = square(number);
    cout << "Square of " << number << " is: " << squared << endl;

    int num1 = 10, num2 = 20;
    int sumResult = sum(num1, num2);
    cout << "Sum of " << num1 << " and " << num2 << " is: " << sumResult << endl;

    return 0;
}
```
In this example:

* The square function calculates the square of a number.
* The sum function calculates the sum of two numbers.
* The main function serves as the driver program that tests both functions by calling them with different inputs and printing the results.

When you run this code, you'll see the output showing the square of 5 and the sum of 10 and 20, which demonstrates the functionality of the square and sum functions respectively. This is a simple example of how a driver program can be used to test multiple functions within a program.

### Review Questions

### Function Overloading: An Introduction
Two functions are considered to have different formal parameter lists if they satisfy one of the following conditions:

1. They have a different number of formal parameters.
2. They have the same number of formal parameters, but the data types of the parameters, arranged in the order listed, differ in at least one position.

For Example:
```cpp
#include <iostream>

using namespace std;

int square(int num) {
    return num * num;
}

double square(double num) {
    return num * num;
}

int main() {
    int intNum = 5;
    double doubleNum = 2.5;

    int squaredInt = square(intNum);
    cout << "Square of " << intNum << " is: " << squaredInt << endl;

    double squaredDouble = square(doubleNum);
    cout << "Square of " << doubleNum << " is: " << squaredDouble << endl;

    return 0;
}
```
In this example:

* There are two functions named square, one that takes an integer argument and another that takes a double argument.
* Both functions calculate the square of their respective arguments and return the result.
* The main function demonstrates function overloading by calling the square function with different argument types (integer and double) and printing the squared values.
Function overloading allows us to define multiple functions with the same name but different parameter lists, making the code more flexible and expressive.

### Review Questions
1. True/False: Two functions can have the same number of formal parameters but differ in their formal parameter lists if the data types of the parameters, arranged in the order listed, differ in at least one position. 
2. True/Fasle: Having different formal parameter lists for functions allows for function overloading
3. Question: How does C++ handle function calls with different formal parameter lists?

***Answers**: 1. **True** 2. **True** 3. **When a function is called, C++ determines the appropriate function to execute based on the number and types of arguments passed.***
### Functions with Default Parameters
Functions in C++ can have default parameters, allowing the caller to omit certain arguments during a function call. When defining a function with default parameters, you specify the default values in the function's prototype. Here are the key rules for functions with default parameters:

1. If you don't provide a value for a default parameter during a function call, the default value specified in the function's prototype is used.

2. All default parameters must be placed at the far-right end of the parameter list.
 
3. If a function has multiple default parameters and you want to omit a default value for a parameter, you must also omit all arguments to the right of that parameter in the function call.

4. Default values can be constants, global variables, or even function calls.
 
5. The caller has the flexibility to provide a different value for any default parameter if needed.
 
6. It's important to note that you cannot assign a constant value as a default value to a reference parameter.

In essence, functions with default parameters offer a way to simplify function calls by providing default values for parameters, which can be overridden by the caller if necessary.

For Example: 
```cpp
#include <iostream>
#include <string>

using namespace std;

void printMessage(string message = "Hello, World!", int count = 1) {
    for (int i = 0; i < count; ++i) {
        cout << message << endl;
    }
}

int main() {
  
    printMessage();  
    printMessage("Welcome to C++ Programming!");  
    printMessage("Goodbye!", 3);


    return 0;
}
```
In this example:

* The printMessage function has default parameters for message (default is "Hello, World!") and count (default is 1).
* When the function is called without specifying any arguments, it uses the default values.
* If a custom message is provided during the function call, it overrides the default message.
* Similarly, if a custom count is provided, it overrides the default count.
This demonstrates how default parameters allow flexibility in function calls by providing sensible defaults that can be customized as needed.

### Review Questions
1. Yes/No: Can default parameters be overridden by explicitly passing arguments during a function call?
2. Question: What happens if a caller omits an argument with a default parameter during a function call?
3. True/False: Using default parameters can reduce the need for function overloading in some cases

***Answers**: 1. **Yes** 2. **If a caller omits an argument with a default parameter during a function call, the default value specified in the function's prototype is used for that parameter.** 3. **True** *
## Chapter Summary 
* Functions in C++ act like independent units within a program, allowing you to break down tasks into manageable pieces. The C++ system comes with predefined standard functions that you can use by following a few rules:

* To use a standard function, you need to know the name of the header file containing its specification and include that header file in your program.

* You must also know the name, type, and number of parameters required by the function.

* User-defined functions in C++ can be of two types: value-returning functions and void functions.

* Value-returning functions return a value and can be used in expressions, output statements, or as parameters in other function calls.

* Void functions do not return a value and are typically used as standalone statements or for performing actions without returning a value.

* Formal parameters are variables declared in a function's heading, while actual parameters are expressions, variables, or constants used in a function call.

* Function prototypes announce the function's type, as well as the type and number of parameters used in the function. They help the compiler correctly translate each function call and allow user-defined functions to appear in any order in the program.

* C++ also supports function overloading, where functions with the same name can have different formal parameter lists. This allows you to use the same function name for similar tasks but with different parameter types or numbers.

* Functions with default parameters provide flexibility by allowing you to specify default values for parameters. If a value is not specified during a function call, the default value is used. However, default values cannot be assigned to reference parameters using constant values.

* Variables in C++ can be local (within a function or block) or global (outside of any function or block). Local variables are automatic and have their memory allocated and deallocated as functions are called and exited, while global variables are static and retain their memory throughout program execution.

* C++ does not allow function nesting, but functions can access variables based on scope rules, which define where identifiers are accessible within the program.
