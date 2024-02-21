# Control Structures Pt 1

## Objectives 
* Identify and use control structures
* Identify logical and relational operators, how they work, and order of precedence
* Distinguish the relationship of relational operators and simple data types
* Identify how to form and evaluate logical (Boolean) expressions
* Use one-way and/or two-way selection syntax
* Demonstrate a switch statement in a program

## Introduction 
Chapter 3 introduces control structures in C++ which are essential elements that determine the flow of execution in a program. They allow programmers to manage the order and repetition of statements based on specified conditions, enabling the creation of dynamic and responsive applications. There are three primary types of control structures in C++: sequence, selection, and iteration.

Understanding and effectively using control structures are crucial for creating structured and readable code. They provide the flexibility needed to handle different scenarios and make C++ programs dynamic and responsive to various conditions.

## Control Structures 
A computer can execute a program in various ways, each serving a specific purpose. It can follow a linear progression, processing instructions one after another, known as sequential execution. Alternatively, it can make decisions based on conditions, taking different paths through the program, referred to as branching or selective execution. Repetitive execution, facilitated by loop structures, allows the computer to perform a statement or group of statements iteratively. Lastly, programs can be organized by dividing tasks into modular units, or functions, which can be called upon when needed, promoting code reusability and maintainability.

### SELECTION: if AND if . . . else
Before delving into selection or repetition statements, it's crucial to grasp the concept of logical expressions and their evaluation. The execution of these statements hinges on logical expressions, which involve assessing the truth or falsehood of a condition. Thus, a fundamental step in programming is gaining an understanding of logical expressions and acquiring the skills to evaluate them effectively. This knowledge lays the groundwork for making decisions and controlling the flow of a program through conditions and loops. 

**Logical expression:** An expression that evaluates to true or false is called a logical expression. 

In C++, the double equal sign (==) is referred to as the equality operator. It serves the purpose of comparing two expressions to ascertain if they are equal. On the other hand, the single equal sign (=) is known as the assignment operator. Unlike the equality operator, the assignment operator is used to assign the value of an expression to a variable. It is essential to distinguish between the two, as the equality operator checks for equality, while the assignment operator assigns a value to a variable.

The relational operators in programming are binary operators, necessitating two operands for their operation. These operators facilitate comparisons between values, and the outcome of such comparisons is a boolean result - either true or false. Consequently, expressions utilizing these relational operators consistently yield a boolean outcome, encapsulating the logic of whether the relationship between the two operands holds true or false.

For Example:
```cpp
#include <iostream>

using namespace std;

int main() {
    
    bool isGreaterThan = (8 > 3);

    cout << "Is 8 greater than 3? " << isGreaterThan << endl;

    return 0;
}
```

### Review Questions 
1. Question: What is the greater than or equal to operator?
2. Question: What is the equality operator
3. True/False: Each of the relational operators is a binary operator; that is, it requires two operands. 

*Answers: 1. **<=** 2. **==** 3. **True***

### Relational Operators and Simple Data Types
Relational operators can be applied to all three fundamental data types—integers, real numbers (float or double), and characters. In the given example, expressions leverage both integers and real numbers to demonstrate the versatility of relational operators across these diverse data types.

```cpp
#include <iostream>
#include <iomanip>

using namespace std;

int main() {
    cout << setw(10) << "Expression" << setw(30) << "Meaning" << setw(10) << "Value" << endl;

    bool result1 = (8 < 15);
    cout << setw(10) << "8 < 15" << setw(30) << "8 is less than 15" << setw(10) << result1 << endl;

    bool result2 = (6 != 6);
    cout << setw(10) << "6 != 6" << setw(30) << "6 is not equal to 6" << setw(10) << result2 << endl;

    bool result3 = (2.5 > 5.8);
    cout << setw(10) << "2.5 > 5.8" << setw(30) << "2.5 is greater than 5.8" << setw(10) << result3 << endl;

    bool result4 = (5.9 <= 7.5);
    cout << setw(10) << "5.9 <= 7.5" << setw(30) << "5.9 is less than or equal to 7.5" << setw(10) << result4 << endl;

    bool result5 = (7 <= 10.4);
    cout << setw(10) << "7 <= 10.4" << setw(30) << "7 is less than or equal to 10.4" << setw(10) << result5 << endl;

    return 0;
}
```

### Review Questions
1. True/False: 8 < 15 means 8 is less than 15
2. True/False: 6 != 6 means	6 is not equal to 6
3. True/False: 5.9 <= 7.5 means	5.9 is less than or equal to 7.5

*Answers: 1. **True** 2. **False** 3. **True***

### Comparing Characters 
In the context of char values, the truth or falsehood of an expression involving relational operators is contingent upon the machine's collating sequence. The collating sequence establishes the order in which characters are arranged, influencing the outcome of comparisons. Notably, the relational operators for char values compare the ASCII or Unicode values assigned to the characters based on the collating sequence. Therefore, the result of such expressions varies depending on the specific character set and encoding used by the machine.

For example:
```cpp
#include <iostream>

using namespace std;

int main() {
    char char1 = 'A';
    char char2 = 'B';

    bool isCharLess = (char1 < char2);
    cout << "Is char1 less than char2? " << isCharLess << endl;

    bool isCharEqual = (char1 == char2);
    cout << "Is char1 equal to char2? " << isCharEqual << endl;

    return 0;
}
```

### Review Questions
1. True/False: The data type bool has two values
2. True/False: In C++, there are two selections, or branch control structures
3. True/False: The value for the char "/" equals 47

*Answers: 1. **True** 2. **True** 3. **True***

### One-Way Selection
One-way selection in C++ programming refers to the use of the if statement to conditionally execute a block of code based on a specified condition. It allows the program to make a decision: if the condition is true, the code inside the if block is executed; otherwise, it is skipped.

For example:
```cpp
#include <iostream>

using namespace std;

int main() {
    int num = 10;

    if (num > 5) 
        cout << "The number is greater than 5." << endl;
    

    return 0;
}
```
In this example, the if statement checks if the variable num is greater than 5. If the condition is true, it prints a message to the console. If the condition is false, the code inside the if block is not executed.

### Review Questions
1. True/False: The condition in the else statement is a boolean expression that determines whether the block of code inside the else statement should be executed.
2. True/False: One-way selection is typically implemented using the if statement.
3. True/False: One-way selection in C++ refers to a control flow structure where a program makes a decision based on a condition.

*Answers: 1. **False** 2. **True** 3. **True***

### Two-Way Selection
C++ offers the if...else statement to facilitate two-way selections in programming scenarios. In situations where a decision must be made between two alternatives, such as calculating a part-time employee's paycheck using an overtime payment formula if they worked extra hours, and using the regular formula otherwise, the if...else statement allows for the implementation of such choices in the code logic.

Consider a scenario where you are writing a program to determine whether a given number is even or odd. In this case, the program needs to make a decision and choose between two alternatives based on the nature of the number. C++ provides the if...else statement for such two-way selections:

```cpp
#include <iostream>

using namespace std;

int main() {
    int number;

    cout << "Enter a number: ";
    cin >> number;

    if (number % 2 == 0) 
        cout << number << " is an even number." << endl;
     else 
        cout << number << " is an odd number." << endl;
    

    return 0;
}
```

In this example, the program checks if the entered number is even or odd using the modulo operator (%). If the remainder after dividing by 2 is zero, the program executes the code inside the if block, indicating that the number is even. Otherwise, it executes the code inside the else block, indicating that the number is odd. The if...else statement helps in making decisions and executing the appropriate code based on the condition evaluated.

### Review Questions 
1. True/False: Two-way selection in C++ refers to a control flow structure where a program makes a decision between two alternatives based on a condition.
2. True/False: The else statement in a two-way selection structure provides an alternative block of code to be executed when the condition specified in the if statement is false.
3. True/False: : In a two-way selection structure, the condition specified in the if statement is evaluated. If the condition is true, the code inside the if block is executed, and the code inside the else block is skipped. If the condition is false, the code inside the if block is skipped, and the code inside the else block is executed.

*Answers: 1. **True** 2. **True** 3. **True***

### int Data Type and Logical (Boolean) Expressions
In earlier versions of C++, there were no dedicated built-in data types specifically designed for logical or Boolean values with "true" and "false." Instead, logical expressions were often represented using the int data type. In this context, logical expressions evaluated to either 1 (representing true) or 0 (representing false), and these values were stored in variables of type int. Therefore, developers utilized the int data type to handle and manipulate logical expressions.

It's important to note that in this convention, any nonzero value was considered as representing true. This means that when evaluating logical conditions, a result of 1 indicated true, while a result of 0 indicated false. This approach allowed for the use of integer variables to convey and work with Boolean logic in the absence of dedicated Boolean data types.

For Example:

```cpp
#include <iostream>

using namespace std;

int main() {
    int number;

    cout << "Enter a number: ";
    cin >> number;

    int isGreaterThan10 = (number > 10);

    if (isGreaterThan10) 
        cout << number << " is greater than 10." << endl;
     else 
        cout << number << " is not greater than 10." << endl;
    

    return 0;
}
```
In this example, the expression (number > 10) evaluates to either 1 (true) or 0 (false) depending on whether number is greater than 10 or not. This result is stored in the int variable isGreaterThan10.

When we evaluate isGreaterThan10 in the if statement, any nonzero value (in this case, 1) is treated as true, and the corresponding message is printed accordingly.

### Review Questions
1. Question: If a logical expression evaluates to true, what integer value is typically assigned when using the int data type?
2. Question: In modern C++, what dedicated data type is used for Boolean values?
3. True/False: Using bool is more expressive and provides clearer code. It explicitly represents true and false values without relying on non-zero and zero integers.

*Answers: 1. **1** 2. **bool** 3. **True***

### bool Data Type and Logical (Boolean) Expressions
In contemporary versions of C++, a dedicated data type, bool, is available to handle logical (Boolean) values, introducing clarity and specificity to Boolean expressions. This data type consists of the reserved words bool, true, and false. In this context, true is assigned the value 1, while false is assigned the value 0, providing a standardized and explicit representation for true and false within the language.

For Example:
```cpp
#include <iostream>

using namespace std;

int main() {

    bool isEven = false;

    int number;
    cout << "Enter a number: ";
    cin >> number;

    isEven = (number % 2 == 0);

    if (isEven) 
        cout << number << " is an even number." << endl;
     else 
        cout << number << " is an odd number." << endl;
    

    return 0;
}
```
In this example, the program checks if the entered number is even using the modulo operator (%). The result of the expression (number % 2 == 0) is assigned to the bool variable isEven. The if statement then evaluates the bool variable and executes the appropriate block of code based on whether the expression is true or false. The use of bool and the reserved words true and false enhances code readability and expressiveness.

### Review Questions
1. True/False:  The reserved words associated with the bool data type are bool, true, and false.
2. In older versions of C++, how were logical (Boolean) expressions typically represented without the bool data type?
3. What value does the identifier false represent in C++?

*Answers: 1. **True** 2. **int** 3. **0***

### Logical (Boolean) Operators and Logical Expressions
Logical operators are special symbols used to perform logical operations on Boolean values (true or false). In C++, the main logical operators are:

1. Logical AND (&&):
   * Returns true if both operands are true; otherwise, it returns false.

2. Logical OR (||):
   * Returns true if at least one of the operands is true; it returns false if both are false.

3. Logical NOT (!):
   * Returns true if the operand is false and vice versa. It negates the value of the operand.

Logical expressions are combinations of relational expressions and logical operators that evaluate to a Boolean value (true or false). They are used to express conditions or criteria that control the flow of a program.

For Example:
```cpp
#include <iostream>
using namespace std;

int main() {
    int x = 5, y = 10;

    bool resultAnd = (x > 0 && y > 0);
    bool resultOr = (x > 0 || y > 0);
    bool resultNot = !(x > y);

    cout << "Logical AND: " << resultAnd << endl;
    cout << "Logical OR: " << resultOr << endl;
    cout << "Logical NOT: " << resultNot << endl;

    return 0;
}
```
In this example, logical expressions are created using the logical AND (&&), logical OR (||), and logical NOT (!) operators. These expressions evaluate conditions based on the values of x and y and produce Boolean results.

Logical operators and expressions are crucial for controlling the flow of a program, making decisions, and implementing conditional statements like if, while, and for loops. They provide the foundation for creating dynamic and responsive code based on various conditions within a program.

### Review Questions
1. True/False: The three main logical operators in C++ are AND (&&), OR (||), and NOT (!).
2. True/False: A logical expression is a combination of relational expressions and logical operators that evaluates to a Boolean value (true or false).
3. Question: How is the result of a logical expression represented in C++ (data type)?

*Answers: 1. **True** 2. **True** 3. **bool***

### Order of Precedence
In C++, the order of precedence determines the sequence in which operators are evaluated within an expression. When an expression contains multiple operators, the order of precedence dictates the grouping and evaluation hierarchy. Operators with higher precedence are evaluated before operators with lower precedence.

Operators at a higher precedence level are evaluated before operators at a lower precedence level. Parentheses () can be used to override the default precedence and explicitly specify the order of evaluation within an expression.

Understanding the order of precedence is crucial for writing correct and predictable expressions in C++, as it influences how expressions are parsed and executed by the compiler.

For Example:
```cpp
#include <iostream>
using namespace std;

int main() {
    int a = 5, b = 3, c = 2;
    bool condition = true;

    int result = a + b * c - (a % c);
    cout << "Result: " << result << endl;

    bool isTrue = (a > b) && condition || (c != 0);
    cout << "Is True: " << boolalpha << isTrue << endl;

    int maxNumber = (a > b) ? a : b;
    cout << "Max Number: " << maxNumber << endl;

    return 0;
}
```
In this example:

The expression a + b * c - (a % c) involves addition, multiplication, and modulo operators. The order of precedence ensures that multiplication is performed before addition, and the modulo operation is given higher precedence than addition and subtraction.

The expression (a > b) && condition || (c != 0) includes logical AND (&&), logical OR (||), and relational operators. The order of precedence ensures that the logical AND is evaluated before the logical OR.

The conditional operator (a > b) ? a : b is used to determine the maximum of a and b based on a condition. The order of precedence ensures that the conditional operator is evaluated after the relational operator a > b.

### Rewview Questions
1. Question: What does the order of precedence determine in C++?
2. True/False: Operators with higher precedence are evaluated before operators with lower precedence. It defines the grouping and hierarchy of operators within an expression.
3. True/False:  Parentheses can be used to explicitly specify the order of evaluation within an expression, altering the default precedence.

*Answers: 1. **The order of precedence determines the sequence in which operators are evaluated within an expression.** 2. **True** 3. **True***

## Chapter Summary 
* Control structures alter the normal flow of execution.

* The two most common control structures are selection and repetition.

* Selection structures incorporate decisions in a program.

* The relational operators are == (equality), < (less than), <= (less than or equal to), > (greater than), >= (greater than or equal to), and != (not equal to).

* Including a space within the relational operators ==, <=, >=, and != creates a syntax error.

* Characters are compared using a machine’s collating sequence.

* Logical expressions evaluate to 1 (or a nonzero value) or 0. The logical value 1 (or any nonzero value) is treated as true; the logical value 0 is treated as false.

* There are two selection structures in C++.

* The expression in an if or if. . .else structure is usually a logical expression.

* Including a semicolon before the statement in a one-way selection creates a semantic error. In this case, the action of the if statement is empty.

* Including a semicolon before statement1 in a two-way selection creates a syntax error.

* There is no stand-alone else statement in C++. Every else has a related if.

* An else is paired with the most recent if that has not been paired with any other else.

* In C++, int variables can be used to store the value of a logical expression.

* In C++, bool variables can be used to store the value of a logical expression.

* In C++, the logical operators are ! (not), && (and), and || (or).

* A sequence of statements enclosed between curly braces, { and }, is called a compound statement or block of statements. A compound statement is treated as a single statement.

* You can use the input stream variable in an if statement to determine the state of the input stream.

* Using the assignment operator in place of the equality operator creates a semantic error. This can cause serious errors in the program.

* The switch structure is used to handle multiway selection.

* The execution of a break statement in a switch statement immediately exits the switch structure.

* If certain conditions are not met in a program, the program can be terminated using the assert function.

## Key Terms

## References 


