# Control Structures Pt 2

## Objectives 
**I. Recognizing the Power of Repetition**

- Outcome 1: Explain the core concept of repetition in programming.
- Outcome 2: Identify real-world scenarios where repetition control structures streamline code.
- Outcome 3: Compare the efficiency of code written with and without repetition structures.

**II. Demystifying While Loops**

* Outcome 1: Construct basic while loops with correct initialization, condition checking, and updates.
* Outcome 2: Differentiate between for loops, do-while loops, and EOF-controlled loops, using examples.
* Outcome 3: Modify loops to iterate a specific number of times or until a user-defined condition is met.

**III. Conditional Logic: Controlling Flow with If and Else**

* Outcome 1: Write 'if' statements to implement decision-making within loops.
* Outcome 2: Incorporate 'else' and 'else if' statements to create multi-branch conditional logic.
* Outcome 3: Apply nested 'if' statements to handle complex decision scenarios within loops.

**IV. Manipulating Loop Behavior: Break and Continue**

* Outcome 1: Demonstrate the use of 'break' to prematurely exit a loop.
* Outcome 2: Apply 'continue' to skip the remaining portion of a loop iteration and advance to the next.
* Outcome 3: Design scenarios where the strategic use of 'break' and 'continue' enhances code readability and efficiency.

**V. Nesting Control Structures: Loops within Loops**

* Outcome 1: Create nested loops to solve problems requiring multiple levels of iteration.
* Outcome 2: Control the execution flow of nested loops effectively to achieve the desired outcome.
* Outcome 3: Debug nested loops with multi-dimensional iteration patterns.

**VI. Debugging Strategies: Perfecting Your Loops**

* Outcome 1: Identify common logical errors arising in repetition control structures.
* Outcome 2: Utilize debugging tools to trace code execution and locate the source of errors within loops.
* Outcome 3: Develop preventive coding practices to minimize the occurrence of logic errors in loops.

## Introduction 
Upon successfully completing this unit, students will acquire the ability to recognize the necessity for employing repetition control structures in programming. They will develop the skill to differentiate between various types of loops, such as While loops, For loops, Do loops, and loops based on End-of-File (EOF) conditions. Additionally, students will be proficient in crafting If and Else statements to control program flow based on specified conditions. The unit will also equip them with the capability to effectively test and utilize break and continue statements within loops. Furthermore, students will gain expertise in constructing nested control structures to handle complex scenarios in their code. Lastly, they will be able to identify methods to proactively prevent bugs and adeptly debug loops, ensuring the robustness and reliability of their programming endeavors.

### Break and Continue Statements
When employed within a switch structure, the break statement functions to promptly exit the entire switch construct. Similarly, its application in while, for, and do...while loops enables an immediate termination of the loop structure. The break statement serves two primary purposes: firstly, it allows for an early exit from a loop, offering a streamlined way to conclude loop execution prematurely; secondly, it facilitates the bypassing of the remaining sections within the switch structure. Once the break statement is executed, the program seamlessly progresses to the initial statement following the respective structure. Integrating a break statement within a loop can obviate the need for certain flag-based mechanisms, enhancing the clarity and efficiency of the code.

For example:
```cpp
// Using break to exit a loop prematurely
for i in range(1, 10):
    print(i)
    if i == 5:
        print("Breaking the loop at i =", i)
        break
```
In this example, the loop iterates from 1 to 9, but when i becomes 5, the break statement is encountered, causing an immediate exit from the loop. 

```cpp
// Using continue to skip an iteration
for i in range(1, 6):
    if i == 3:
        print("Skipping iteration at i =", i)
        continue
    print(i)
```
In this example, when i equals 3, the continue statement is executed, skipping the rest of the loop's body for that iteration. 

### Review Questions
1. True/False: In a switch structure, break immediately exits the switch.
2. Question: what is a  nested control structure?
3. True/False: "continue" doesnt skip the remaining code in a loop's iteration.

***Answers**: 1. **True** 2. **involve placing one control structure within** **another**. 3. **False***

### Nested Control Structures
In programming, a nested control structure refers to the practice of incorporating one or more control structures within another. Control structures, such as loops (e.g., While, For, Do...While) or conditional statements (If, Else), dictate the flow of a program by determining which blocks of code should be executed based on specified conditions. When these structures are nested, it means that one control structure encapsulates another within its block.

The primary motivation for using nested control structures is to address scenarios that require a more intricate and layered approach to programming logic. By nesting control structures, programmers gain the ability to create complex decision-making processes or repetitive patterns that involve multiple levels of conditions and iterations.

Consider a common example of a nested control structure involving loops. In this case, an outer loop may iterate through a set of values, and within each iteration, an inner loop executes its own set of instructions. This allows for a fine-grained control over the execution flow, enabling the program to handle diverse situations with greater flexibility.

For example:
```cpp
// Nested control structure example: Nested loop
for i in range(1, 6):  // Outer loop for rows
    for j in range(1, i + 1):  // Inner loop for columns
        print(j, end=" ")
    print()  // Move to the next line after each row
```
This example illustrates how nesting loops can be used to control the flow of the program, creating more intricate patterns or handling situations where multiple levels of iteration are required.

### Review Questions 
1. What does "nested control structures" mean in programming?
2. True/False: The relationship between nested control structures is visually shown by using indentation in code.
3. True/False: Nested control structures help handle more complex tasks by allowing for layered decision-making or repetitive processes in a program.

***Answer**: 1. **In programming, nested control structures mean putting one control structure (like a loop or conditional statement) inside another.** 2. **True** 3. **True** ***

### Avoiding Bugs by Avoiding Patches
The concept of "Avoiding Bugs by Avoiding Patches" in C++ suggests that rather than relying on quick fixes or patches to resolve issues in your code, it is often more effective to adopt a proactive approach to writing clean and robust code from the beginning. This approach emphasizes careful planning, clear design, and thorough testing during the development process, aiming to prevent the introduction of bugs rather than dealing with them after they occur. By focusing on creating solid foundations and understanding the underlying principles of C++, developers can reduce the need for reactive bug fixes and minimize the risk of introducing new issues when making changes to the code.

For example:
```cpp
#include <iostream>

using namespace std;

double calculateRectangleArea(double length, double width) {
    return length * width;
}

int main() {
    double length = 5.0;
    double width = 3.0;

    double area = calculateRectangleArea(length, width);

    cout << "Rectangle Area: " << area << endl;

    return 0;
}
```
In this example it calculates the area of a rectangle based on the provided length and width values.

### Review Questions 
1. Q: What does "Avoiding Bugs by Avoiding Patches" mean in C++?
2. True/False: Adding a patch is a poor programming practice.
3. True/False: A software patch is a piece of code written on top of an existing piece of code intended to fix a bug in the original code.

***Answers**: 1. **It means focusing on writing solid code initially, rather than fixing problems later.** 2. **True** 3. **True***

### Debugging Loops
In the preceding debugging discussions, we've acknowledged that, despite careful design and coding, errors are inevitable. While syntax errors are easily caught by the compiler, logical errors demand a close examination of the code or even the overall design. To enhance program reliability, it's crucial to detect and rectify errors before releasing the program to users.

After crafting an algorithm, the next crucial step is verification. For simple sequential flows or branches, manual tracing or utilizing the IDE's debugger is effective. However, debugging loops, which are often trickier, requires additional consideration. Loop invariants play a role in ensuring loop correctness. These are statements that remain true with each iteration of the loop. While a comprehensive discussion on loop invariants is beyond our scope, resources like "Discrete Mathematics: Theory and Applications" by D.S. Malik and M.K. Sen provide in-depth exploration.

For effective loop debugging, common pitfalls such as off-by-one errors must be addressed. Infinite loops, for instance, often signal issues in the logical expression controlling the loop. Checking for reversed inequalities, incorrect assignment symbols, or using && instead of || is essential. If the loop involves variable modifications, printing variable values before and after each iteration or using the IDE's debugger can be invaluable.

While the debugging sections in this book aim to guide you through the debugging process, it's important to recognize that debugging can be a challenging task. In cases where the program is severely flawed, consider the option to refrain from debugging. Sometimes, it's more efficient to discard the problematic code and start afresh.

For example:
```cpp
#include <iostream>

using namespace std; // Use the std namespace

int main() {
    int n;
    int sum = 0;

    // Get user input for n
    cout << "Enter a positive integer n: ";
    cin >> n;

    // Corrected loop to calculate sum
    for (int i = 1; i <= n; i++) {
        // Debug statement: print variable values
        cout << "i: " << i << " sum: " << sum << endl;

        sum = sum + i;  // Corrected addition operation
    }

    // Display the result
    cout << "The sum of numbers from 1 to " << n << " is: " << sum << endl;

    return 0;
}
```

### Review Questions
1. Q: What is a loop invariant?
2. Q: What is a common error associated with loops?
3. Q: How can you debug loops that involve variable modifications?

**Answers**: 1.  **A loop invariant is a set of statements that remains true with each iteration of a loop.** 2. **A common error is the off-by-one mistake.** 3. **You can print the values of variables before and after each iteration to trace their changes.** 

## Chapter Summary 
1. C++ has three looping (repetition) structures: while, for, and do. . .while.
2. In C++, while is a reserved word.
3. In the while statement, the parentheses around the expression (the decision maker) are important; they mark the beginning and end of the expression.

4. The statement is called the body of the loop.

5. The body of the while loop must contain a statement that eventually sets the expression to false.

6. A counter-controlled while loop uses a counter to control the loop.

7. In a counter-controlled while loop, you must initialize the counter before the loop, and the body of the loop must contain a statement that changes the value of the counter variable.

8. A sentinel is a special value that marks the end of the input data. The sentinel must be similar to, yet differ from, all the data items.

9. A sentinel-controlled while loop uses a sentinel to control the loop. The while loop continues to execute until the sentinel is read.

10. An EOF-controlled while loop uses an end-of-file marker to control the loop. The while loop continues to execute until the program detects the end-of-file marker.

11. In the Windows console environment, the end-of-file marker is entered using Ctrl+z (hold the Ctrl key and press z).

12. A for loop simplifies the writing of a counter-controlled while loop.

13. In C++, for is a reserved word.

14. Putting a semicolon at the end of the for loop (before the body of the for loop) is a semantic error. In this case, the action of the for loop is empty.

15. Both while and for loops are called pretest loops. A do. . .while loop is called a posttest loop.

16. The while and for loop bodies may not execute at all, but the do. . .while loop body always executes at least once.

17. Executing a break statement in the body of a loop immediately terminates the loop.

18. Executing a continue statement in the body of a loop skips the loop’s remaining statements and proceeds with the next iteration.

19. When a continue statement executes in a while or do. . .while loop, the expression update statement in the body of the loop may not execute.

20. After a continue statement executes in a for loop, the update statement is the next statement executed.

## Key Terms




## Programming Exercises 
```cpp 
#include <iostream>
#include <cstdlib>
#include <ctime>

using namespace std;

int main() {
    // Seed the random number generator
    srand(time(0));

    char playAgain;

    do {
        // Generate a random number between 1 and 100
        int secretNumber = rand() % 100 + 1;
        int userGuess;
        int attempts = 0;

        // Display welcome message and instructions
        cout << "Welcome to the Number Guessing Game!\n";
        cout << "I have selected a number between 1 and 100.\n";
        cout << "Try to guess the number!\n";

        do {
            // Get user's guess
            cout << "Enter your guess (1-100): ";
            cin >> userGuess;

            // Check if the guess is correct and provide feedback
            if (userGuess < secretNumber) {
                cout << "Too low! Try again.\n";
            } else if (userGuess > secretNumber) {
                cout << "Too high! Try again.\n";
            } else {
                cout << "Congratulations! You guessed the number in " << attempts + 1 << " attempts.\n";
            }

            // Increment the attempts counter
            attempts++;

        } while (userGuess != secretNumber);

        // Ask the user if they want to play again
        cout << "Do you want to play again? (y/n): ";
        cin >> playAgain;

    } while (playAgain == 'y' || playAgain == 'Y');

    return 0;
}
```

## References
