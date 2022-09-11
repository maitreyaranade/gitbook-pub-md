Date: 2022-09-11 Name: Maitreya Ranade

::: center
C++ Language\
:::

# C Programming

## Introduction

### History of Computing

Manual Entering code in binary Assembly language

C is a procedural programming language. It was initially developed by
Dennis Ritchie in the year 1972. It was mainly developed as a system
programming language to write an operating system. The main features of
the C language include:

-   Portability (Machine Specific)

-   Requires less lines of code than assembly language

-   Procedural programming

-   Middle level language

    -   Direct access to memory through Pointers

    -   Bit manipulation using bitwise Operators

    -   Writing assembly code within C code

-   Popular choice for system level apps

-   Wide variety of built in functions, standard libraries and header
    files.

High level vs Low level language Degree of abstraction High level: Less
efforts to users ex. COBOL, FORTRAN, C++, Pascal etc. Low level: More
efforts to users ex. Assembly Middle level language: ex. C

Preprocessor: replaces text (starting with #) with actual content before
compilation. Output of preprocessing is expanded source code.

Preprocessor directive: ex. #include\<stdio.h\> stdio.h: standard input
output file

-   header files: .h extensions

-   Contains declarations of functions like printf, scanf etc.

```{=html}
<!-- -->
```
-   Variables

-   Operators

-   Conditionals and Loops

-   Functions

-   Recursion

-   Pointers and arrays

-   Structure and union

## Variables

Variables are just names that point to a memory location. It is used to
store data. Its value can be changed, and it can be reused many times.
Variable is a way to represent memory location through symbol so that it
can be identified easily.

Declaration of variables: Announcing the propoerties of variable to the
compiler

Properties:

-   Size of the variable

-   Name of the variable

Data type: how much space a variable is going to occupy in memory.

Definition of variables: Allocating memory to a variable. Most of the
time declaration and definition will be done at the same time.

Initialization of variables: Initializing a variable means specifying an
initial value to assign to it (i.e., before it is used at all).\
Notice that a variable that is not initialized does not have a defined
value, hence it cannot be used until it is assigned such a value. If the
variable has been declared but not initialized, we can use an assignment
statement to assign it a value.

Variable name: composed of alphabets or combination of letters and
digits.

Variable naming conventions:

1.  Don't start variable name with digit.

2.  Beginning with underscore is valid but not recommended.

3.  C language is case sensitive.

4.  Special characters except underscore are not allowed in the variable
    name.

5.  Blanks or white spaces not allowed.

6.  Don't use keywords to name your variables.

7.  Don't use long names your variables.

8.  Redefinition of a variable is not allowed.

Scope of variables:

Scope of variables refers to the area of the program where the variables
can be accessed post declaration. In other words, a block or a region
where a variable is declared, defined and used and when a region ends,
variable is automatically destroyed.

In C, every variable defined in scope. You can define scope as the
section or region of a program where a variable has its existence;
moreover, that variable cannot be used or accessed beyond that region.

Scope of a variable: Local scope or Block scope A local scope or block
scope is collective program statements put in and declared within a
function or block (a specific region enclosed with curly braces) and
variables lying inside such blocks are termed as local variables.

Variable(s) that are declared within a block can be accessed within that
specific block and all other inner blocks of that block, but those
variables cannot be accessed outside the block.

::: center
![Scope of a variable](images/variableScope.png){#variableScope
width="\\textwidth"}
:::

Local Variable Variables that are declared within the function block and
can be used only within the function are called local variables.

Global variable Variables that are declared outside of all function
blocks and can be accessed inside all the functions are called global
variables.

### Data types

-   Exceeding the valid range of data type: Let us say that the max
    number of bytes in a particular data type is 'n'. Exceeding the
    range of the data type means that assigning a number with bits
    greater than 'n' bits. Hence, (MSB) bits beyond 'n' bits will be
    missed.

-   **Range** is nothing but upper and lower limits of some set of data.
    Binary: $2^{n} - 1$, where, n is number of buts. Unsigned range: o
    to 65535 2 bytes Signed range: -32768 to +32767\

-   **sizeof()** is a unary operator (not a function) that can get the
    size of a data type programmatically.\
    **Modifiers for integers (short, long, signed, unsigned)**\
    **long & short** are modifiers which are used to take either less or
    more memory.

-   Number systems

    -   Decimal number system: Human understandable number system. Also,
        called as base 10 number system. Range 0 to 9.

    -   Binary number system: Computer understandable number system.
        Also, called as base 2 number system. Range 0 to 1.

-   **Fixed point and Floating point representation** Fixed point and
    floating point are two ways of representing fractional numbers.

    -   In fixed point, there is a specific number of digits to
        represent the integer section and fraction section i.e. the
        decimal point has a fixed location.

    -   In floating point, there is no specific number of digits to
        represent integer section and fraction section i.e. the decimal
        point is floating. A number in floating point representation is
        as follows: $+/- Mantissa * 10^{exponent}$

::: center
![Fixed point and Floating point
representation](images/fixedFloating.png){#fixedFloating
width="\\textwidth"}
:::

#### integer

-   integer data type is used to represent integers.

-   Syntax: int variable_name; (by default variable is chosen as a
    signed integer)\
    Unsigned int declaration: unsigned int variable_name;\

-   Format specifier:

    -   int = \"%d\" (signed int)

    -   short int = \"%d\" (signed short int)

    -   long int = \"%ld\" (signed long int)

    -   unsigned int = \"%u\" (unsigned int)

    -   short unsigned int = \"%u\" (unsigned short int)

    -   long unsigned int = \"%lu\" (unsigned long int)

-   size: Integer can take either 2 or 4 bytes of memory. (vary as per
    system)

    -   int = 4

    -   short int = 2

    -   long int = 8

-   Range: Unsigned: 0 to 255 & Signed: -128 to +127

-   sizeof(short int) \<= sizeof(int) \<= sizeof(long int)

#### Character

-   Character data type is used to represent characters.

-   Representation: Characters are encoded using ASCII encoding scheme
    into 8 bit binary representation. There are 2 types of ASCII
    encoding schemes:

    -   Traditional ASCII: 7 bit representation MSB is always zero

    -   Extended ASCII: 8 bit representation of characters

-   Syntax: char variable_name = 'N';

-   Character data type can hold a single character and cannot hold a
    string.

-   Format specifier: \"%c\"

-   size: 1 byte

-   Range: Unsigned: 0 to 255 & Signed: -128 to +127

Signed characters: 2's complement representation Unsigned characters:

#### float

-   float data type is used to represent fractional numbers.

-   Representation: IEEE 754 Single Precision Floating Point

-   Syntax: float variable_name = 'fractional number';

-   float data type has a precision of upto 8 decimals(including decimal
    point and integer)

-   Format specifier: \"%f\"

-   size: 4 bytes (vary as per system)

#### double

-   double data type is used to represent fractional numbers.

-   Representation: IEEE 754 Double Precision Floating Point

-   Syntax: double variable_name = 'fractional number';

-   double data type has a precision of upto 16 decimals(including
    decimal point and integer)

-   Format specifier: \"%f\" or \"%lf\"

-   size: 8 bytes (vary as per system)

#### long double

-   long double data type is used to represent fractional numbers.

-   Representation: Extended Precision Floating Point

-   Syntax: long double variable_name = 'fractional number';

-   long double data type has a precision of upto 32 decimals(including
    decimal point and integer)

-   Format specifier: \"%Lf\"

-   size: 16 bytes (vary as per system)

## Variable Modifiers

### Auto

-   Auto stands for Automatic.

-   Syntax: auto int variable_name;

-   Variables declared inside a scope by default are automatic
    variables. Automatic variable is a variable which automatically gets
    destroyed after the completion of a function or a scope in which it
    is defined.

-   Advantage: This variable does not waste memory.

-   If auto variable is not initialized, it will be assigned a random
    value by default. Whereas, a global variable is initialized to 0 by
    default.

### Extern modifier

-   Extern is a short for External.

-   Syntax: (declaration) extern int variable_name; (no memory is
    allocated.)

-   Extern is used when a particular file needs to access a variable
    from another file.

-   When an extern variable is initialized, then memory for this
    variable is allocated and it will be considered defined.

### Register

-   Register keyword hints the compiler to store a variable in register
    memory.

-   Syntax: register data_type variable_name;

-   Access time reduces greatly for most frequently referred variables.

-   To put or to not put a variable in register is the choice of
    compiler.

-   Usually compiler do the necessary optimizations.

### Static

-   Static variables have a property of preserving their value even
    after they are out of their scope. Hence, static variables preserve
    their previous value in their previous scope and are not initialized
    again in the new scope.

-   Syntax: static = variable_value;

-   A static int variable remains in memory while the program is
    running. A normal or auto variable is destroyed when a function call
    where the variable was declared is over.

-   Static variables (like global variables) are initialized as 0 if not
    initialized explicitly.

-   Static variables are allocated memory in data segment, not stack
    segment.

-   Static global variables and functions are also possible in C/C++.
    The purpose of these is to limit scope of a variable or function to
    a file.

-   Static variables should not be declared inside structure.

## Constants

-   Constant is something that never changes. In other words, once
    defined cannot be modified later in the code.

-   #define is a preprocessor directive.

    -   Syntax: #define name value (name is also called macro)

    -   Avoid semicolon at the end in the syntax.

    -   Choosing capital letters for name is good practice.

    -   Preprocessor replaces Name with value.

    -   We can use macros like functions.

    -   First expansion then evaluation.

    -   There are current predefined / standard Macros ex. \_\_TIME\_\_
        & \_\_DATE\_\_.

-   Const keyword

    -   A variable defined with the const modifier are considered
        variables, and not macro definitions.

    -   syntax: const data_type variable_name

-   Const-s are handled by the compiler, where as #define-s are handled
    by the pre-processor.

-   The big advantage of const-s over #define is type checking.
    #define-s can't be type checked.

-   Since const-s are considered variables, we can use pointers on them.
    This means we can typecast, move addresses, and everything else
    you'd be able to do with a regular variable besides change the data
    itself, since the data assigned to that variable is constant.

## Memory Layout of C program

A typical memory representation of a C program consists of the following
sections.

1.  Text/Code segment

2.  Initialized data segment

3.  Uninitialized data segment (bss)

4.  Heap

5.  Stack

::: center
![Memory Layout of C program](images/memoryLayoutC.png){#memoryLayoutC
width="60%"}
:::

C program gets stored into not one but multiple sections of the memory.
A typical memory layout of a running process is as follows:

### Text/Code segment

-   A text segment, also known as a code segment or simply as text,
    contains machine code of the compiled program or executable
    instructions.

-   The text segment is often read-only, to prevent a program from
    accidentally modifying its instructions.

-   As a memory region, a text segment may be placed below the heap or
    stack in order to prevent heaps and stack overflows from overwriting
    it.

-   Usually, the text segment is sharable so that only a single copy
    needs to be in memory for frequently executed programs, such as text
    editors, the C compiler, the shells, and so on.

### Initialized Data Segment

-   Initialized data segment, usually called simply the Data Segment.

-   A data segment is a portion of the virtual address space of a
    program, which contains the global, extern, static (local and
    global), and const global variables that are initialized by the
    programmer.

-   Note that, the data segment is not read-only, since the values of
    the variables can be altered at run time.

-   This segment can be further classified into the read-only (for
    const-s) area and the read-write sections.

### Uninitialized Data Segment

-   Uninitialized data segment often called the \"bss\" segment, named
    after an ancient assembler operator that stood for \"block started
    by symbol\".

-   Uninitialized data segment contains all uninitialized global,
    static(local and global), and constant global variables.

-   Data in this segment is initialized by the kernel to arithmetic 0
    before the program starts executing.

-   This segment is also further classified into read-only (for const-s)
    area and read-write sections.

### Stack

The stack area traditionally adjoined the heap area and grew in the
opposite direction; when the stack pointer met the heap pointer, free
memory was exhausted. (With modern large address spaces and virtual
memory techniques they may be placed almost anywhere, but they still
typically grow in opposite directions.)

The stack area contains the program stack, a LIFO structure, typically
located in the higher parts of memory. On the standard PC x86 computer
architecture, it grows toward address zero; on some other architectures,
it grows in the opposite direction. A \"stack pointer\" register tracks
the top of the stack; it is adjusted each time a value is \"pushed\"
onto the stack. The set of values pushed for one function call is termed
a \"stack frame\"; A stack frame consists at minimum of a return
address.

Stack, where automatic variables are stored, along with information that
is saved each time a function is called. Each time a function is called,
the address of where to return to and certain information about the
caller's environment, such as some of the machine registers, are saved
on the stack. The newly called function then allocates room on the stack
for its automatic and temporary variables. This is how recursive
functions in C can work. Each time a recursive function calls itself, a
new stack frame is used, so one set of variables doesn't interfere with
the variables from another instance of the function.

### Heap

Heap is the segment where dynamic memory allocation usually takes place.

The heap area begins at the end of the BSS segment and grows to larger
addresses from there. The Heap area is managed by malloc, realloc, and
free, which may use the brk and sbrk system calls to adjust its size
(note that the use of brk/sbrk and a single \"heap area\" is not
required to fulfill the contract of malloc/realloc/free; they may also
be implemented using mmap to reserve potentially non-contiguous regions
of virtual memory into the process' virtual address space). The Heap
area is shared by all shared libraries and dynamically loaded modules in
a process.

## Operators

Operators are the foundation of any programming language. We can define
operators as symbols that help us to perform specific mathematical and
logical computations on operands. In other words, we can say that an
operator operates the operands.

Types of operators based on the operations they perform are as follows:

1.  Arithmetic Operators

2.  Increment/Decrement Operators

3.  Relational Operators

4.  Logical Operators

5.  Bitwise Operators

6.  Assignment Operators

7.  Misc Operators

### Arithmetic Operators

Arithmetic Operators are used to performing mathematical calculations.
All the operators are binary operators which mean they require 2
operands to perform operation. There are 5 types of Arithmetic
Operators.

1.  \+ Addition

2.  \- Subtraction

3.  \* Multiplication

4.  / Division

5.  \% Modulus

### Increment/Decrement Operators

Both the operators are unary operators. Both of them require only one
operand to perform operation.

-   lvalue(left value): is an object that has an identifiable location
    in memory (i.e. having an address) ex. a variable.

-   rvalue(right value): is an object that has no identifiable location
    in memory (i.e. having an address) ex. a function.

-   Pre increment/decrement operator means first increment/decrement
    then assign it to another variable.

-   Post increment/decrement operator means first assign it to another
    variable and then increment/decrement.

#### Increment Operator (++)

-   Increment operator is used to increment the value of a variable by
    one.

-   a++ is equivalent to a = a+1;

-   There are 2 types of Increment Operator:

    -   Pre-increment operator (++a)

    -   Post-increment operator (a++)

-   'rvalue' cannot be used with increment operator.

#### Decrement Operator (--)

-   Decrement operator is used to decrement the value of a variable by
    one.

-   a-- is equivalent to a = a-1;

-   There are 2 types of decrement Operator:

    -   Pre-decrement operator (--a)

    -   Post-decrement operator (a--)

-   'rvalue' cannot be used with decrement operator.

### Relational Operators

-   Relational operators are used to comparing two quantities or values.

-   All the relational operators are binary operators.

-   All the relational operators will return either True or False.

1.  == Is equal to

2.  != Is not equal to

3.  \> Greater than

4.  \< Less than

5.  \>= Greater than or equal to

6.  \<= Less than or equal to

### Logical Operators

C provides three logical operators when we test more than one condition
to make decisions.

1.  && And operator: It performs logical conjunction of two expressions.
    (if both expressions evaluate to True, result is True. If either
    expression evaluates to False, the result is False)

2.  \|\| Or operator: It performs a logical disjunction on two
    expressions. (if either or both expressions evaluate to True, the
    result is True)

3.  ! Not operator: It performs logical negation on an expression.

### Bitwise Operators

C provides a special operator for bit operation between two variables.

1.  \<\< Binary Left Shift Operator

2.  \>\> Binary Right Shift Operator

3.  B̃inary Ones Complement Operator

4.  & Binary AND Operator

5.  B̂inary XOR Operator

6.  \| Binary OR Operator

### Assignment operators

Assignment operators applied to assign the result of an expression to a
variable.

1.  = Assign

2.  += Increment then assign

3.  -= Decrement then assign

4.  \*= Multiply then assign

5.  /= Divide then assign

6.  %= Modulus then assign

7.  \<\<= Bitwise shift left then assign

8.  \>\>= Bitwise shift right then assign

9.  &= Bitwise AND then assign

10. \|= Bitwise OR then assign

11. =̂ Bitwise XOR then assign

### Conditional operators

C offers only one ternary (requires 3 operands) operator which is the
conditional operator (?: in combination) to construct conditional
expressions. Ex. result = (Expression1) ? Expression2 : Expression3 ;

1.  ? : Conditional Expression

### Special operators

C supports some special operators

1.  sizeof() Returns the size of a memory location.

2.  & Returns the address of a memory location.

3.  \* Pointer to a variable.

#### Comma operator (,)

-   Comma operator can be used as a separator.\
    For example: int var1 = 0, var2 = 1;

-   Comma operator can be used as a \"operator\".\
    For example: int var1 = (0, 1, 2);\
    Comma operator returns the rightmost operand in the expression and
    it simply evaluates the rest of the operands and finally reject
    them.

-   Comma operator has the least precedence among all the operators
    available in C language.

### Token generation

-   Lexical analysis is the first phase in the compilation process.

-   Lexical analyzer (scanner) scans the whole source program and it
    finds the meaningful sequence of characters(lexemes) then it
    converts it into a token.

-   Token: lexemes mapped into token-name and attribute-value.\
    Example: int -\> \<keyword, int\>

-   Lexical analyzer always matches the longest character sequence.

### Operator precedence & associativity

Operator precedence determines the grouping of terms in an expression
and decides how an expression is evaluated. Certain operators have
higher precedence than others. For example, the multiplication operator
has a higher precedence than the addition operator.

#### Operator Precedence

Operator precedence is used to evaluate the order of operators evaluated
in an expression. In C programming, every operator has a priority. When
there is more than one operator in the given expression, the operator
with higher precedence or priority is evaluated first and the operator
with the least priority is evaluated later.

#### Operator Associativity

Operator associativity is used to evaluate the order of operators with
equal precedence in an expression. In the C programming language, when
an expression contains multiple operators with equal or same precedence,
we use associativity to determine the order of evaluation of operators.

Add operator table here

## Conditionals

In c language, the statements are executed sequentially. Multiple times,
one requires a functionality which is used multiple times in an
execution. Programming languages provide various control structures that
allow for more complicated execution paths.

Conditionals or Decision making structures require that the programmer
specifies one or more conditions to be evaluated or tested by the
program, along with a statement or statements to be executed if the
condition is determined to be true, and optionally, other statements to
be executed if the condition is determined to be false. C programming
language assumes any non-zero and non-null values as true, and if it is
either zero or null, then it is assumed as false value.

General form of a typical decision making structure found in most of the
programming languages. C programming language provides the following
types of Conditionals:

### if

An if statement consists of a boolean expression followed by one or more
statements. Syntax:

``` {style="CStyle"}
if(boolean_expression) {
    /* statement(s) will execute if the boolean expression is true */
    }
```

If the Boolean expression evaluates to true, then the block of code
inside the 'if' statement will be executed. If the Boolean expression
evaluates to false, then the first set of code after the end of the 'if'
statement (after the closing curly brace) will be executed.

#### 

if-else An if statement can be followed by an optional else statement,
which executes when the Boolean expression is false. Syntax:

``` {style="CStyle"}
if(boolean_expression) {
        /* statement(s) will execute if the boolean expression is true */
    } else {
        /* statement(s) will execute if the boolean expression is false */
    }
```

If the Boolean expression evaluates to true, then the if block will be
executed, otherwise, the else block will be executed.

#### Nested if

It is always legal in C programming to nest if-else statements, which
means one can use one if or else-if statement inside another if or
else-if statement(s). Syntax:

``` {style="CStyle"}
if( boolean_expression 1) {    
       /* Executes when the boolean expression 1 is true */
       if(boolean_expression 2) {
          /* Executes when the boolean expression 2 is true */
       }
    }
```

You can nest else if-else in the similar way as you have nested if
statements.

### switch

A switch statement allows a variable to be tested for equality against a
list of values. Each value is called a case, and the variable being
switched on is checked for each switch case. This is also a great
replacement to long else if constructs. Syntax:

``` {style="CStyle"}
switch(expression) {
    
       case constant-expression  :
          statement(s);
          break; /* optional */
    	
       case constant-expression  :
          statement(s);
          break; /* optional */
      
       /* you can have any number of case statements */
       default : /* Optional */
       statement(s);
    }
```

Please note the following:

1.  The expression used in a switch statement must have an integral or
    enumerated type, or be of a class type in which the class has a
    single conversion function to an integral or enumerated type.

2.  You can have any number of case statements within a switch. Each
    case is followed by the value to be compared to and a colon. But
    duplicate case statements are not allowed.

3.  The constant-expression for a case must be the same data type as the
    variable in the switch, and it must be a constant or a literal.

4.  When the variable being switched on is equal to a case, the
    statements following that case will execute until a break statement
    is reached.

5.  When a break statement is reached, the switch terminates, and the
    flow of control jumps to the next line following the switch
    statement.

6.  Not every case needs to contain a break. If no break appears, the
    flow of control will fall through to subsequent cases until a break
    is reached.

7.  A switch statement can have an optional default case, which must
    appear at the end of the switch. The default case can be used for
    performing a task when none of the cases is true. No break is needed
    in the default case.

#### Nested switch

It is possible to have a switch as a part of the statement sequence of
an outer switch. Even if the case constants of the inner and outer
switch contain common values, no conflicts will arise. Syntax:

``` {style="CStyle"}
switch(ch1) {
    
       case 'A': 
          printf("This A is part of outer switch" );
    
          switch(ch2) {
             case 'A':
                printf("This A is part of inner switch" );
                break;
             case 'B': /* case code */
          }
    
          break;
       case 'B': /* case code */
    }
```

## Loops

A loop statement allows the programmer to execute a statement or group
of statements multiple times. C Programming languages provide various
control structures that allow for more complicated execution paths.

In general, loops are a programming element that repeat a portion of
code a set number of times until the desired process is complete.
Repetitive tasks are common in programming, and loops are essential to
save time and minimize errors. Loops make code more readable, manageable
and organized. C language provides the following types of loops to
handle looping requirements:

### while

A while loop in C programming repeatedly executes a target statement as
long as a given condition is true. It tests the condition before
executing the loop body. Syntax:

``` {style="CStyle"}
while(condition) {
      statement(s);
   }
```

Here, statement(s) may be a single statement or a block of statements.
The condition may be any expression, and true is any nonzero value. The
loop iterates while the condition is true. When the condition becomes
false, the program control passes to the line immediately following the
loop.

Here, the key point to note is that a while loop might not execute at
all. When the condition is tested and the result is false, the loop body
will be skipped and the first statement after the while loop will be
executed.

### for

A for loop is a repetition control structure that allows you to
efficiently write a loop that needs to execute a specific number of
times. Syntax:

``` {style="CStyle"}
for ( initialization; condition; increment/decrement) {
      statement(s);
   }
```

Kindly note:

1.  The init step is executed first, and only once. This step allows you
    to declare and initialize any loop control variables. You are not
    required to put a statement here, as long as a semicolon appears.

2.  Next, the condition is evaluated. If it is true, the body of the
    loop is executed. If it is false, the body of the loop does not
    execute and the flow of control jumps to the next statement just
    after the 'for' loop.

3.  After the body of the 'for' loop executes, the flow of control jumps
    back up to the increment statement. This statement allows you to
    update any loop control variables. This statement can be left blank,
    as long as a semicolon appears after the condition.

4.  The condition is now evaluated again. If it is true, the loop
    executes and the process repeats itself (body of loop, then
    increment step, and then again condition). After the condition
    becomes false, the 'for' loop terminates.

### do-while

Unlike for and while loops, which test the loop condition at the top of
the loop, the do-while loop in C programming checks its condition at the
bottom of the loop. A do-while loop is similar to a while loop, except
the fact that it is guaranteed to execute at least one time. Syntax:

``` {style="CStyle"}
do {
      statement(s);
   } while( condition );
```

Notice that the conditional expression appears at the end of the loop,
so the statement(s) in the loop executes once before the condition is
tested.

If the condition is true, the flow of control jumps back up to do, and
the statement(s) in the loop executes again. This process repeats until
the given condition becomes false.

### Nested loops

C programming allows to use one loop inside another loop. A final note
on loop nesting is that you can put any type of loop inside any other
type of loop. For example, a 'for' loop can be inside a 'while' loop or
vice versa.

### Loop Control Statements

Loop control statements change execution from its normal sequence. When
execution leaves a scope, all automatic objects that were created in
that scope are destroyed. C supports the following control statements:

#### break

When a break statement is encountered inside a loop, the loop is
immediately terminated and the program control resumes at the next
statement following the loop.\
It can also be used to terminate a case in the switch statement. If you
are using nested loops, the break statement will stop the execution of
the innermost loop and start executing the next line of code after the
block. Syntax:

``` {style="CStyle"}
break;
```

#### continue

Instead of forcing termination, the continue statement forces the next
iteration of the loop to take place, skipping any code in between.

For the for loop, continue statement causes the conditional test and
increment portions of the loop to execute. For the while and do\...while
loops, continue statement causes the program control to pass to the
conditional tests. Syntax:

``` {style="CStyle"}
break;
```

#### goto

A goto statement in C programming provides an unconditional jump from
the 'goto' to a labeled statement in the same function.

**NOTE:** Use of goto statement is highly discouraged in any programming
language because it makes difficult to trace the control flow of a
program, making the program hard to understand and hard to modify. Any
program that uses a goto can be rewritten to avoid them. Syntax:

``` {style="CStyle"}
goto label;
      /* statement(s) exempted from execution */
   label: statement;
```

Here label can be any plain text except C keyword and it can be set
anywhere in the C program above or below to goto statement.

### The Infinite Loop

An infinite loop is a looping construct that does not terminate the loop
and executes the loop forever. It is also called an indefinite loop or
an endless loop. It either produces a continuous output or no output.\
A loop becomes an infinite loop if a condition never becomes false. We
can create an infinite loop through various loop structures like the
following:

1.  for loop

2.  while loop

3.  do-while loop

4.  go to statement

This is how an infinite loop can be generated from the aforementioned
structures.

``` {style="CStyle"}
// using for loop
   for( ; ; ) {
      statement(s)
   }

   // using while loop
   while(1)  {  
      statement(s)
   }  

   // using do-while loop
   do  
   {  
      statement(s)
   }while(1); 
   
   // using go to statement
   label;  
   statement(s)
   goto label;  
```

**NOTE:** An infinite loop can be terminated by pressing Ctrl + C keys.

## Functions & Pointers

### What is a Function

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

##### 

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

#### printf() and scanf() functions

printf() and scanf() functions are inbuilt library functions in C
programming language which are available in C library by default. These
functions are declared and related macros are defined in \"stdio.h\"
which is a header file in C language.

#### printf

-   printf() function is used to print the (\"character, string, float,
    integer, octal and hexadecimal values\") onto the output screen.

-   syntax: printf(\"%d\", var)

-   We use printf() function with %d format specifier to display the
    value of an integer variable. Similarly, %c is used to display
    character, %f for float variable, %s for string variable, %lf for
    double and %x for hexadecimal variable.

-   To generate a newline, we use \"\\n\" in C printf() statement.

#### scanf

-   scanf stands for Scan Formatted string

-   scanf() function is used to read character, string, numeric data
    from an input device like keyboard.

-   syntax: scanf(\"%d\", &var)

-   The format specifier %d is used in scanf() statement so that, the
    value entered is received as an integer and %s for string.

-   Ampersand is used before the variable name in scanf() statement to
    store the user input into that particular variable name as &
    Variable_name.

#### Note

1.  printf() is used to display the output and scanf() is used to read
    the inputs.

2.  printf() and scanf() functions are declared in \"stdio.h\" header
    file in C library.

3.  All syntax in C language including printf() and scanf() functions
    are case sensitive.

4.  All characters in printf() and scanf() functions must be in lower
    case as C is a case sensitive language.

### Why Use Functions

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

### Passing Values between Functions

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

### Scope Rule of Functions

Kindly refer to the Variables section.

### Calling Convention

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

### Function Declaration and Prototypes

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

### Call by Value and Call by Reference

There are two methods to pass the data into the function in C language,

1.  Call by value

2.  Call by reference

#### Call by value

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

#### Call by reference

In call by reference, the address of the variable is passed into the
function call as the actual parameter. As the variables are stored in
the memory, so instead of passing the value of a variable, can we not
pass the location number (or address) of the variable to a function?
This feature of C functions needs at least an elementary knowledge of a
concept called \"pointers\".

### An Introduction to Pointers

The textbook definition of a pointer is *The pointer in C language is a
variable which stores the address of another variable.* This variable
can be of type int, char, array, function, or any other pointer. The
size of the pointer depends on the architecture.

#### Pointer Notation

Consider the declaration,**int i = 3;**\
This declaration tells the C compiler to:

1.  Reserve space in memory to hold the integer value.

2.  Associate the name i with this memory location.

3.  Store the value 3 at this location.

We may represent i's location in memory by the following memory map.

::: center
![Variable memory map](images/pointer.png){#pointer width="\\textwidth"}
:::

We see that the computer has selected memory location 65524 as the place
to store the value 3. **i's address in memory is a number.**

##### Operator &

\"&\" is used in C as an \"address of\" operator. The expression \"&i\"
returns the address of the variable i, which in this case happens to be
65524. We have been using the \"&\" operator all the time in the scanf()
statement.

##### Operator \*

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

##### Pointer declaration

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

## C/C++ Preprocessors

As the name suggests Preprocessors are programs that process our source
code before compilation. There are a number of steps involved between
writing a program and executing a program in C / C++.

::: center
![Preprocessor in C](images/Cpreprocessor.png){#Cpreprocessor
width="60%"}
:::

The source code file is processed by preprocessors and an expanded
source code file is generated named program. This expanded file is
compiled by the compiler and an object code file is generated named
program .obj. Finally, the linker links this object code file to the
object code of the library functions to generate the executable file
program.exe.

Preprocessor programs provide preprocessors directives which tell the
compiler to preprocess the source code before compiling. All of these
preprocessor directives begin with a '#' (hash) symbol. The '#' symbol
indicates that, whatever statement starts with #, is going to the
preprocessor program, and preprocessor program will execute this
statement. Examples of some preprocessor directives are: #include,
#define, #ifndef etc. Remember that \# symbol only provides a path that
it will go to the preprocessor, and command such as include is processed
by preprocessor program. For example, include will include extra code to
your program. We can place these preprocessor directives anywhere in our
program.

There are 4 main types of preprocessor directives:

1.  Macros

2.  File Inclusion

3.  Conditional Compilation

4.  Other directives

Macros: Macros are a piece of code in a program which is given some
name. Whenever this name is encountered by the compiler the compiler
replaces the name with the actual piece of code. The '#define' directive
is used to define a macro.

::: highlight
Note: There is no semi-colon(';') at the end of macro definition. Macro
definitions do not need a semi-colon to end.
:::

File Inclusion: This type of preprocessor directive tells the compiler
to include a file in the source code program. There are two types of
files which can be included by the user in the program: Header File or
Standard files: These files contains definition of pre-defined functions
like printf(), scanf() etc. These files must be included for working
with these functions. Different function are declared in different
header files. For example standard I/O functions are in 'iostream' file
whereas functions which perform string operations are in 'string' file.

user defined files: When a program becomes very large, it is good
practice to divide it into smaller files and include whenever needed.
These types of files are user defined files. These files can be included
as:

Conditional Compilation: Conditional Compilation directives are type of
directives which helps to compile a specific portion of the program or
to skip compilation of some specific part of the program based on some
conditions. This can be done with the help of two preprocessing commands
'ifdef' and 'endif'.

If the macro with name as 'macroname' is defined then the block of
statements will execute normally but if it is not defined, the compiler
will simply skip this block of statements.

Other directives: Apart from the above directives there are two more
directives which are not commonly used. These are: #undef Directive: The
#undef directive is used to undefine an existing macro. This directive
works as:

Using this statement will undefine the existing macro LIMIT. After this
statement every "#ifdef LIMIT" statement will evaluate to false.

#pragma Directive: This directive is a special purpose directive and is
used to turn on or off some features. This type of directives are
compiler-specific, i.e., they vary from compiler to compiler. Some of
the #pragma directives are discussed below: #pragma startup and #pragma
exit: These directives helps us to specify the functions that are needed
to run before program startup( before the control passes to main()) and
just before program exit (just before the control returns from main()).
Note: Below program will not work with GCC compilers. Look at the below
program:

#pragma warn Directive: This directive is used to hide the warning
message which are displayed during compilation. We can hide the warnings
as shown below: #pragma warn -rvl: This directive hides those warning
which are raised when a function which is supposed to return a value
does not returns a value. #pragma warn -par: This directive hides those
warning which are raised when a function does not uses the parameters
passed to it. #pragma warn -rch: This directive hides those warning
which are raised when a code is unreachable. For example: any code
written after the return statement in a function is unreachable.

##### Pragma Directive in C/C++

This directive is a special purpose directive and is used to turn on or
off some features. This type of directives are compiler-specific i.e.,
they vary from compiler to compiler. Some of the pragma directives are
discussed below:

#pragma startup and #pragma exit: These directives helps us to specify
the functions that are needed to run before program startup( before the
control passes to main()) and just before program exit (just before the
control returns from main()). Note: Below program will not work with GCC
compilers. Look at the below program:

## References

-   [Neso Academy (Youtube Channel) (C Programming & Data Structures
    playlist)](https://youtube.com/playlist?list=PLBlnK6fEyqRhX6r2uhhlubuF5QextdCSM)

-   Let us C by Yashwant Kanetkar

-   [Tutorials
    Point](https://www.tutorialspoint.com/cprogramming/index.htm)

-   [Geeks for
    geeks](https://www.geeksforgeeks.org/c-programming-language/)

-   [The C book](https://publications.gbdirect.co.uk/c_book/)
