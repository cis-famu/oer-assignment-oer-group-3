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
