## What is a Function
A function is a self-contained block of statements that takes an input,
perform a coherent task/computation and produces an output. Every C
program can be thought of as a collection of these functions.

## Need for a Function
Why should anyone write separate functions at all:
1.  **Readability** Writing functions avoids rewriting the same code
    over and over.
2.  **Abstraction** If you are using the function in your program then
    you don't have to worry about how it works inside!
3.  **Reusability** Once the function is defined, it can be reused over
    and over again.
4.  **Modularity** Using functions it becomes easier to write programs
    and keep track of what they are doing. If the operation of a program
    can be divided into separate activities, and each activity placed in
    a different function, then each could be written and checked more or
    less independently. Separating the code into modular functions also
    makes the program easier to design and understand.

## Defining a Function
A function can also be referred as a method or a sub-routine or a
procedure, etc.
The general form of a function definition in C programming language is
as follows:
```c
return_type function_name ( parameter list ) {
        body of the function
     }
```
A function definition in C programming consists of a function header and
a function body. Here are all the parts of a function:
1.  Return Type: A function may return a value. The return type is the
    data type of the value the function returns. Some functions perform
    the desired operations without returning a value.
2.  Function Name: This is the actual name of the function. The function
    name and the parameter list together constitute the function
    signature.
3.  Parameters: When a function is invoked, a value is passed to the
    parameter. This value is referred to as actual parameter or
    argument. The parameter list refers to the type, order, and number
    of the parameters of a function. Parameters are optional.
4.  Function Body: The function body contains a collection of statements
    that define what the function does.

## Function declaration
Function declaration is also called as function prototype represents
declaring the properties of a function to the compiler. A function
declaration tells the compiler about a function's name, return type, and
parameters. Syntax of a function declaration is:
```c
return_type function_name( parameter list );
```

## Calling a Function
After creating a C function, to use it has to be called to perform the
defined task. To call a function, the required parameters along with the
function name need to be passed, and the returned value has to be stored
if the function has one. Syntax for calling a function is,
```c
return_value = function_name ( parameter list );
```

The function which receives the control from a function call is referred
as the called function.\
The function which transfers the control with a function call is
referred as the calling function.

When a program (calling function) calls a function, the program control
is transferred to the called function. A called function performs a
defined task and upon reaching the end of functionality, it returns the
program control back to the calling function.

## Function Arguments
-   If a function is to use arguments, it must declare variables that
    accept the values of the arguments.
-   The variables declared in the function prototype or definition are
    known as **Formal arguments**
-   The values that are passed to the called function from the main
    function are known as **Actual arguments**.
-   The actual arguments and formal arguments must match in number,
    type, and order.
-   **Formal parameters** behave like other local variables inside the
    function and are created upon entry into the function and destroyed
    upon exit.
-   There are two methods of declaring the formal arguments:
    1.  Kernighan and Ritchie (or just K & R) method:\
        function (x, y, z)\
        int x, y, z ;
    2.  ANSI method: (Commonly used)\
        function (int x, int y, int z)
While calling a function, there are two ways in which arguments can be
passed to a function:
1.  Call by value
2.  Call by reference

### Call by value
In call by value method, the value of the actual parameters is copied
into the formal parameters. In other words, the value of the variable is
used in the function call.
-   We can not modify the value of the actual parameter by the formal
    parameter.
-   Different memory is allocated for actual and formal parameters since
    the value of the actual parameter is copied into the formal
    parameter.
-   The actual parameter is the argument which is used in the function
    call whereas formal parameter is the argument which is used in the
    function definition.

### Call by reference
In call by reference, the address of the variable is passed into the
function call as the actual parameter. As the variables are stored in
the memory, so instead of passing the value of a variable, can we not
pass the location number (or address) of the variable to a function?
This feature of C functions needs at least an elementary knowledge of a
concept called \"pointers\".

## Summary and additional concepts
1.  C program is a collection of one or more functions.
2.  Any C program contains at least one function.
3.  If a program contains only one function, it must be main().
4.  If a C program contains more than one function, then one (and only
    one) of these functions must be main(), because program execution
    always begins with main().
5.  There is no limit on the number of functions that might be present
    in a C program.
6.  A function can be called any number of times.
7.  Each function in a program is called in the sequence specified by
    the function calls in main().
8.  The order in which the functions are defined in a program and the
    order in which they get called need not necessarily be same.
9.  After each function has done its thing, control returns to main().
    When main() runs out of function calls, the program ends.
10. A function gets called when the function name is followed by a
    semicolon.
11. In C language, arguments of a function are passed from right to
    left.
12. A function can be called from other function, but a function cannot
    be defined in another function.
13. A function can call itself. Such a process is called \"recursion\".
14. The **return** statement is necessary for returning value to the
    calling function, if any. It serves two purposes:
    1.  On executing the return statement, it immediately transfers the
        control back to the calling program.
    2.  It returns the value present in the parentheses after return, to
        the calling program. In the above program the value of sum of
        three numbers is being returned.
15. There is no restriction on the number of return statements that may
    be present in a function. Also, the return statement need not always
    be present at the end of the called function.
16. Whenever the control returns from a function some value is
    definitely returned. If a meaningful value is returned then it
    should be accepted in the calling program by equating the called
    function to some variable.
17. If we want that a called function should not return any value, in
    that case, we must mention so by using the keyword void.
18. A function can return only one value at a time.
19. If the value of a formal argument is changed in the called function,
    the corresponding change does not take place in the calling
    function.

## Types of functions
There are two primary types of functions:
1.  Library functions printf(), scanf() etc.
2.  User-defined functions function_name_1(), function_name_2() etc.
As the name suggests, library functions are nothing but commonly
required functions grouped together and stored in what is called a
Library. This library of functions is present on the disk and is written
for us by people who write compilers for us. Almost always a compiler
comes with a library of standard functions. The procedure of calling
both types of functions is exactly same.

### printf() and scanf() functions
printf() and scanf() functions are inbuilt library functions in C
programming language which are available in C library by default. These
functions are declared and related macros are defined in \"stdio.h\"
which is a header file in C language.

### printf
-   printf() function is used to print the (\"character, string, float,
    integer, octal and hexadecimal values\") onto the output screen.
-   syntax: printf(\"%d\", var)
-   We use printf() function with %d format specifier to display the
    value of an integer variable. Similarly, %c is used to display
    character, %f for float variable, %s for string variable, %lf for
    double and %x for hexadecimal variable.
-   To generate a newline, we use \"\\n\" in C printf() statement.

### scanf
-   scanf stands for Scan Formatted string
-   scanf() function is used to read character, string, numeric data
    from an input device like keyboard.
-   syntax: scanf(\"%d\", &var)
-   The format specifier %d is used in scanf() statement so that, the
    value entered is received as an integer and %s for string.
-   Ampersand is used before the variable name in scanf() statement to
    store the user input into that particular variable name as &
    Variable_name.

### Points to note
1.  printf() is used to display the output and scanf() is used to read
    the inputs.
2.  printf() and scanf() functions are declared in \"stdio.h\" header
    file in C library.
3.  All syntax in C language including printf() and scanf() functions
    are case sensitive.
4.  All characters in printf() and scanf() functions must be in lower
    case as C is a case sensitive language.

## Static and dynamic scoping
