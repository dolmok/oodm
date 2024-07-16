# OODM Programming Language

OODM, pronounced "ooh-dee-em," is a programming language crafted to provide the ease of writing interpreted code with the performance benefits of compilation.  With OODM, you can effortlessly write simple and readable code capable of handling complex tasks efficiently.

The OODM compiler is developed in C++.  For those who prefer not to deal with the complexities of compiled languages, OODM includes a utility program that seamlessly compiles and runs your code in one step.

## Hello World 

Here is a simple example to get you started with OODM:

```
print("Hello, World!")
```

## Basic Syntax

OODM was created by combining the readability of Python with the structured approach of Java.  Here we will have a quick overview of its basic syntax.

### Comments

1. **Single-line comments**: Use `# ...` for single-line comments.
2. **Multi-line comments**: Use `### ... ###` for multi-line comments.

Below is an example:

```
# This is a single-line comment.

###
This is a
multi-line comment.
###
```

### Data Types

There are a lot of data types in OODM.  You can also create new data types using classes.

1. `int`: Data type for 32-bit integers.
2. `long`: Data type for 64-bit integers.
3. `uint`: Data type for unsigned 32-bit integers.
4. `ulong`: Data type for unsigned 64-bit integers.
5. `byte`: Data type for 8-bit integers.
6. `short`: Data type for 16-bit integers.
7. `ubyte`: Data type for unsigned 8-bit integers.
8. `ushort`: Data type for unsigned 16-bit integers.
9. `bool`: Data type for storing booleans.
10. `String`: Data type for storing UTF-8 strings.
11. `Array`: Data type for array-based lists.
12. `Function`: Data type for storing functions.
13. `Class`: Data type for storing classes.

### Variables

Variables are dynamically typed.  However, you can also explicitly set the data type of the variables.

```
x = 10
name = "John Doe"
isReady: bool = true
list: Array of int = [1, 2, 3, 4, 5]
```

> **Note**: While you can store any type in a variable, constantly changing the type of a variable is a bad practice, since it drastically lowers the performance. Consider using multiple variables instead.

### Functions

You can define functions using the `function` keyword.

```
greet = function(name) {
    print("Hello, " + name)
}
add = function(a, b) => a + b
```

### Classes and Objects

You can define classes using the `class` keyword.  Functions defined within the class will be treated as member functions.  The special method `constructor` is called when an instance of the class is initialized.  Accessing class members is straightforward using the dot notation, `.member_name`.

```
Person = class {
    name, age

    constructor = function(name, age) {
        .name = name
        .age = age
    }

    display = function() {
        print("Name: " + .name + ", Age: " + .age)
    }
}
```

### Control Flow

#### If-Else Statement

You can use `if` and `else` to branch on some conditions.  Since the braces (`{}`) cannot be omitted, you should use `elif` instead of `else if`.

```
x = 10
if x > 0 {
    print("Positive")
}
elif x == 0 {
    print("Zero")
}
else {
    print("Negative")
}
```

#### Looping

There are two ways to loop in OODM, a `while` or an `until` loop and a `for` loop.

A `while` or an `until` loop is straightforward, looping while/until some condition is met.

```
x = 0

# Loop while x is less than 10
while x < 10 {
    x += 1  # Increment x by one
}

# Loop until x is less than -10
until x < -10 {
    x -= 1  # Decrement x by one
}
```

Using a `for` loop, you can loop over a list, generator, or any other kinds of iterators.

```
primes = [2, 3, 5, 7, 11]

for prime in primes {
    print(prime)  # 2, 3, 5, 7, 11
}

for i in (0...10) {
    print(i)  # 0, 1, 2, 3, 4, 5, 6, 7, 8, 9
}
```

You can use `break` to exit the nearest enclosing loop prematurely.

```
for i in (0...10) {
    if i == 5 {
        break
    }
    print(i)  # 0, 1, 2, 3, 4
}
```

Use `continue` to skip the rest of the code inside the loop for the current iteration and proceed to the next iteration.

```
for i in (0...10) {
    if i == 5 {
        continue
    }
    print(i)  # 0, 1, 2, 3, 4, 6, 7, 8, 9;  Notice the missing 5.
}
```

After each loop you can place a `then` statement, which gets executed when the loop completed normally without encountering a `break` statement.

```
for _ in (0...5) {  # Loop for 5 times
    x = parsePrimitive of int(readInput())  # Input a number from the user
    if x < 0 {
        break  # Break if the number is negative
    }
}
then {
    # This statement will only be executed when the user do not enter any negative number
    print("The loop was completed normally.")
}
```
