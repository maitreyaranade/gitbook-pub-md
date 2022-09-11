## What is a Function

A function is a self-contained block of statements that perform a
coherent task of some kind. Every C program can be thought of as a
collection of these functions.

Example of a function:

``` {style="CStyle"}
main()
{
message();
printf("\nCry, and you stop the monotony!");
}

message()
{
printf("\nSmile, and the world smiles with you...");
}
```

And here's the output:

``` {style="CStyle"}
Smile, and the world smiles with you...
Cry, and you stop the monotony!
```

Here, main() itself is a function and through it we are calling the
function message(). What do we mean when we say that main() \"calls\"
the function message()? We mean that the control passes to the function
message(). The activity of main() is temporarily suspended. It falls
asleep while the message() function wakes up and goes to work. When the
message() function runs out of statements to execute, the control
returns to main(), which comes to life again and begins executing its
code at the exact point where it left off. Thus, main() becomes the
\"calling\" function, whereas message() becomes the \"called\" function.

#### 

Calling multiple functions:

``` {style="CStyle"}
main()
{
printf("\nI am in main");
italy();
brazil();
argentina();
}

italy()
{
printf("\nI am in italy");
}

brazil()
{
printf("\nI am in brazil");
}

argentina()
{
printf("\nI am in argentina");
}
```

The output of the above program when executed would be as under:

``` {style="CStyle"}
I am in main
I am in italy
I am in brazil
I am in argentina
```

Summary:

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

9.  After each function has done its thing, control returns to
    main().When main() runs out of function calls, the program ends.

10. A function gets called when the function name is followed by a
    semicolon. Syntax for calling a function is,

    ``` {style="CStyle"}
    main()
        {
        argentina();
        }
    ```

11. A function is defined when function name is followed by a pair of
    braces in which one or more statements may be present. Syntax for
    defining a function is,

    ``` {style="CStyle"}
    argentina()
        {
        statement 1 ;
        statement 2 ;
        statement 3 ;
        }
    ```

12. A function can be called from other function, but a function cannot
    be defined in another function.

13. A function can call itself. Such a process is called \"recursion\".

14. There are basically two types of functions:

    1.  Library functions Ex. printf(), scanf() etc.

    2.  User-defined functions Ex. argentina(), brazil() etc.

    As the name suggests, library functions are nothing but commonly
    required functions grouped together and stored in what is called a
    Library. This library of functions is present on the disk and is
    written for us by people who write compilers for us. Almost always a
    compiler comes with a library of standard functions. The procedure
    of calling both types of functions is exactly same.

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

### Note

1.  printf() is used to display the output and scanf() is used to read
    the inputs.

2.  printf() and scanf() functions are declared in \"stdio.h\" header
    file in C library.

3.  All syntax in C language including printf() and scanf() functions
    are case sensitive.

4.  All characters in printf() and scanf() functions must be in lower
    case as C is a case sensitive language.

## Why Use Functions

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

## Passing Values between Functions

The 'calling' function has to communicate certain information to the
'called' function. The mechanism used to convey information to the
function is the 'argument'. The arguments are sometimes also called
'parameters'.

Consider the following program. In this program, in main()we receive the
values of a, b and c through the keyboard and then output the sum of a,
b and c. However, the calculation of sum is done in a different function
called calsum(). If sum is to be calculated in calsum()and values of a,
b and c are received in main(), then we must pass on these values to
calsum(), and once calsum()calculates the sum we must return it from
calsum()back to main().

``` {style="CStyle"}
/* Sending and receiving values between functions */
main()
{
    int a, b, c, sum ;
    printf("\nEnter any three numbers ");
    scanf("%d %d %d", &a, &b, &c);
    sum = calsum(a, b, c);
    printf("\nSum = %d", sum);
}

calsum(x, y, z)
int x, y, z ;
{
    int d ;
    d = x + y + z ;
    return(d);
}
```

And here is the output:

``` {style="CStyle"}
Enter any three numbers 10 20 30
Sum = 60
```

There are a number of things to note about this program:

1.  In this program, from the function main() the values of a, b and c
    are passed on to the function calsum(), by making a call to the
    function calsum().

2.  In the calsum() function these values get collected in three
    variables x, y and z.

3.  The variables a, b and c are called 'actual arguments', whereas the
    variables x, y and z are called 'formal arguments'.

4.  Any number of arguments can be passed to a function being called.
    However, the type, order and number of the actual and formal
    arguments must always be same.

5.  There are two methods of declaring the formal arguments.

    1.  Kernighan and Ritchie (or just K & R) method: (used in this
        program):\
        calsum(x, y, z)\
        int x, y, z ;

    2.  ANSI method: (Commonly used)\
        calsum(int x, int y, int z)

6.  The **return** statement is necessary for returning value to the
    calling function, if any. It serves two purposes:

    1.  On executing the return statement, it immediately transfers the
        control back to the calling program.

    2.  It returns the value present in the parentheses after return, to
        the calling program. In the above program the value of sum of
        three numbers is being returned.

7.  There is no restriction on the number of return statements that may
    be present in a function. Also, the return statement need not always
    be present at the end of the called function.

8.  Whenever the control returns from a function some value is
    definitely returned. If a meaningful value is returned then it
    should be accepted in the calling program by equating the called
    function to some variable.

9.  If we want that a called function should not return any value, in
    that case, we must mention so by using the keyword void.

10. A function can return only one value at a time.

11. If the value of a formal argument is changed in the called function,
    the corresponding change does not take place in the calling
    function.

## Scope Rule of Functions

Kindly refer to the Variables section.

## Calling Convention

Calling convention indicates the order in which arguments are passed to
a function when a function call is encountered. There are two
possibilities here:

1.  Arguments might be passed from left to right.

2.  Arguments might be passed from right to left. (Followed by C)

The order of passing arguments becomes an important consideration. For
example:

``` {style="CStyle"}
int a = 1;
printf("%d %d %d", a, ++a, a++);
```

It appears that this printf() would output 1 2 3. This however is not
the case. Surprisingly, it outputs 3 3 1. As C's calling convention is
from right to left, i.e. firstly 1 is passed through the expression a++
and then a is incremented to 2. Then result of ++a is passed. That is, a
is incremented to 3 and then passed. Finally, latest value of a, i.e. 3,
is passed. Thus in right to left order 1, 3, 3 get passed. Once printf()
collects them it prints them in the order in which we have asked it to
get them printed (and not the order in which they were passed). Thus 3 3
1 gets printed.

## Function Declaration and Prototypes

Any C function by default returns an **int** value. More specifically,
whenever a call is made to a function, the compiler assumes that this
function would return a value of the type **int**. If we desire that a
function should return a value other than an **int**, then it is
necessary to explicitly mention so in the calling function as well as in
the called function. What it means is square() is a function that
receives a float and returns a float. For example,\
float square (float);\
This statement is often called the prototype declaration of the square()
function.

## Call by Value and Call by Reference

There are two methods to pass the data into the function in C language,

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

## An Introduction to Pointers

The textbook definition of a pointer is *The pointer in C language is a
variable which stores the address of another variable.* This variable
can be of type int, char, array, function, or any other pointer. The
size of the pointer depends on the architecture.

### Pointer Notation

Consider the declaration,**int i = 3;**\
This declaration tells the C compiler to:

1.  Reserve space in memory to hold the integer value.

2.  Associate the name i with this memory location.

3.  Store the value 3 at this location.

We may represent i's location in memory by the following memory map.


![Variable memory map](images/pointer.png)


We see that the computer has selected memory location 65524 as the place
to store the value 3. **i's address in memory is a number.**

#### Operator &

\"&\" is used in C as an \"address of\" operator. The expression \"&i\"
returns the address of the variable i, which in this case happens to be
65524. We have been using the \"&\" operator all the time in the scanf()
statement.

#### Operator \*

Pointer operator \"\*\" is called as the \"value at address\" operator.
It gives the value stored at a particular address. The \"value at
address\" operator is also called \"indirection\" operator

Note that printing the value of \"\*(&i)\" is same as printing the value
of i.

The expression &i gives the address of the variable i. This address can
be collected in a variable, by saying, j = &i ;

But remember that j is not an ordinary variable like any other integer
variable. It is a variable that contains the address of other variable
(i in this case). Since j is a variable the compiler must provide it
space in the memory.

#### Pointer declaration

int \*j;\
This declaration tells the compiler that j will be used to store the
address of an integer value. In other words, j points to an integer.

Here is a program that demonstrates the relationships we have been
discussing.

``` {style="CStyle"}
main( )
{
    int i = 3 ;
    int *j ;

    j = &i ;
    printf ( "\nAddress of i = %u", &i ) ;
    printf ( "\nAddress of i = %u", j ) ;
    printf ( "\nAddress of j = %u", &j ) ;
    printf ( "\nValue of j = %u", j ) ;
    printf ( "\nValue of i = %d", i ) ;
    printf ( "\nValue of i = %d", *( &i ) ) ;
    printf ( "\nValue of i = %d", *j ) ;
}
```

The output of the above program would be:

``` {style="CStyle"}
Address of i = 65524
    Address of i = 65524
    Address of j = 65522
    Value of j = 65524
    Value of i = 3
    Value of i = 3
    Value of i = 3
```

***Note: Remember that, addresses (location numbers) are always going to
be whole numbers, therefore pointers always contain whole numbers.***
