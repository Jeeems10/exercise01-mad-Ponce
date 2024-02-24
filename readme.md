# MAD - Exercise 01
## Tasks
* Watch the Kotlin Crashcourse Video in Moodle or complete the tutorials **[Introduction to programming in Kotlin](https://developer.android.com/courses/pathways/android-basics-compose-unit-1-pathway-1)** and **[Kotlin fundamentals](https://developer.android.com/courses/pathways/android-basics-compose-unit-2-pathway-1
)**.
* Answer the questions inside this Readme.md file and push it to your repository.
* Submit your coding solution of the Number Guessing Game inside the repository.
* Submit the link to your repository in Moodle.

## Questions
### Describe how Kotlin handles null safety. What are nullable types and non-null types in Kotlin? (0,5 points)

<span style="color:blue">Provide your answer here! </span>
<br> One of the main characteristics of Kotlin is its approach to null safety, which aims to lower the possibility of the feared NullPointerException that afflicts a lot of Java programs. By differentiating between nullable and non-null types

**Non-Null Types**
<br>Types in Kotlin are never null by default. This implies that Kotlin assumes a variable cannot contain a null value if it is declared as a variable of a particular type. You cannot give null to a variable that is declared as String, for instance. If this is attempted, a compile-time error will occur. By using this design decision, the possibility of running into a NullPointerException when accessing variables is practically eliminated.

![image](https://github.com/Jeeems10/exercise01-mad-Ponce/assets/114492119/6b0d1e3f-88d4-4627-838f-dd4976dadaf8)

**Nullable Types**
<br> A question mark (?) is appended to the type name to indicate that the type is expressly marked as nullable, allowing a variable to have a null value. String?, for example, is a nullable string type; its variables can store null or a string value.

![image](https://github.com/Jeeems10/exercise01-mad-Ponce/assets/114492119/71ac7099-ab12-4c62-ba25-d75abf01cef2)

> Note: you can also use code snippets to illustrate your answer. 

```kotlin 
// example code snippet
val a: String = "value" // non-null type
```

### What are lambda expressions and higher order functions in Kotlin? Why would you store a function inside a variable? (0,5 points)

<span style="color:blue">Provide your answer here!</span>

**Lamda Expressions**
<br>In essence, a lambda expression is a brief code block that accepts parameters and outputs a value. Curly braces {} are used to define lambda expressions. The expressions and return value of the lambda are located on the right side of the arrow ->, while parameters are taken on the left. For producing short function literals that may be saved in variables, returned as values, or supplied as arguments, lambdas are a highly helpful tool.

![image](https://github.com/Jeeems10/exercise01-mad-Ponce/assets/114492119/81b6f55d-bdf0-427c-9834-accc56e766c1)

**Higher-Order Functions**
<br>Functions that have the ability to return functions or take functions as parameters are known as higher-order functions. This is one of Kotlin's most useful features; it makes code more abstract and succinct, especially when working with operations that can be applied to a variety of data types or behavior types.

![image](https://github.com/Jeeems10/exercise01-mad-Ponce/assets/114492119/4d21f544-b2da-42f1-920c-76d9f0fe4246)

![image](https://github.com/Jeeems10/exercise01-mad-Ponce/assets/114492119/05fc09ee-b12d-4f8d-b2a3-8b256469a98c)

![image](https://github.com/Jeeems10/exercise01-mad-Ponce/assets/114492119/e1a4a561-53a7-425f-a732-f2360ab8e78d)

**Storing Functions in Variables**
<br>There are various reasons why storing a function in a variable can be highly helpful.
- Reusability: A function can be defined once and used again in several circumstances.
- Higher-Order Functions: This feature enables the building of extremely abstract and generic code that may operate on any sort of data by allowing functions to be sent as parameters to other functions.
- Deferred Execution: Depending on the logic of the application, storing a function enables you to execute it later, repeatedly, or conditionally.

![image](https://github.com/Jeeems10/exercise01-mad-Ponce/assets/114492119/dae1c964-a948-444e-8b86-a9f7ff4c30bc)

![image](https://github.com/Jeeems10/exercise01-mad-Ponce/assets/114492119/15dace9b-fec0-4d6c-8c60-8b6deb488acd)

### Provide a solution for the following number guessing game inside `App.kt`. (3 points)

## Number Guessing Game in Kotlin
The game is a simple number guessing game. The task is to generate a random, max 9-digit, number. The number must **not contain repeating digits**. Valid digits are 1-9.
Ask the user to guess the max 9-digit number. The game is finished when the user guesses the correct digits in the correct order.
In each round, the user gets feedback about the number of correct digits and the number of correct digits in the correct position.
The output should be in the format "n:m", where "n" is the number of digits guessed correctly regardless of their position, 
and "m" is the number of digits guessed correctly at their correct position. Here are some examples:

This example shows the game flow with 4-digits to guess (the default argument)

Generated number: 8576
-	User input: 1234, Output: 0:0
-	User input: 5678, Output: 4:1
-	User input: 5555, Output: 1:1
-	User input: 3586, Output: 3:2
-	User input: 8576, Output: 4:4 -> user wins

Take a look into the provided code structure in `src/main/kotlin/App.kt`. Implement the following methods (lambda expressions):
- _playNumberGame(digitsToGuess: Int = 4)_ (1 point): The main game loop that handles user input and game state. Make use of _generateRandomNonRepeatingNumber_ and _checkUserInputAgainstGeneratedNumber_ here. This function also utilizes a default argument 
- _generateRandomNonRepeatingNumber_ (1 point): A lambda expression that generates a random number with non-repeating digits of a specified length.
- _checkUserInputAgainstGeneratedNumber_ (1 point): A lambda expression that compares the user's input against the generated number and provides feedback.

``CompareResult.kt`` This class is a data structure which helps with bundling the result of the comparison of the user input and the generated number. Look at the toSting() and use it in your output.

Run the project with `./gradlew run` and test your implementation with the provided tests in `src/test/kotlin/AppTest.kt` with `./gradlew test`.

# Project Structure
The project is structured into two main Kotlin files:

**App.kt**: Contains the main game logic and functions.

**AppTest.kt**: Contains unit tests for the various functions in App.kt.

