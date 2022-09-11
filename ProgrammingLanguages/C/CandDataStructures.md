Date: 2022-09-11 Name: Maitreya Ranade

::: center
C Language and Data Structures\
:::

# C Programming

## Introduction

### History of Computing

Multiple devices have been used to aid computation for thousands of
years like abacus, astronomical calenders, differential analyser, etc.
Charles Babbage, an English mechanical engineer, (considered the
\"father of the computer\") originated the concept of a programmable
computer in the early 19th century.

A computer is a machine that can be programmed to carry out sequences of
arithmetic or logical operations automatically. Modern computers can
perform generic sets of operations known as programs. The principle of
the modern computer was proposed by Alan Turing in 1936. The fundamental
concept of Turing's design was the stored program, where all the
instructions for computing were stored in a memory. The next great
advance in computing power came with the advent of the transistors,
semiconductors, and integrated circuits.

Machine code was the language of early programs, written in the
instruction set of the particular machine, often in binary notation.
Assembly languages were soon developed that let the programmer specify
instruction in a text format, with abbreviations for each operation code
and meaningful names for specifying addresses.

With further development in software as well as hardware, Compiler
languages were formulated. High-level languages made the process of
developing a program simpler and more understandable, and less bound to
the underlying hardware. These compiled languages allowed the programmer
to write programs in terms that are syntactically richer, and more
capable of abstracting the code, making it easy to target for varying
machine instruction sets via compilation declarations and heuristics.
Compilers harnessed the power of computers to make programming easier by
allowing programmers to specify calculations by entering a formula using
infix notation.

#### Introduction to C language

C is a procedural programming language. It was initially developed at
the AT & T's Bell Laboratories of USA by Dennis Ritchie in the year
1972. It was mainly developed as a system programming language to write
an operating system. The main features of the C language include:

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

### Elements of C Language

Communicating with a computer involves speaking the language the
computer understands. However, there is a close analogy between learning
English and C language. Learning English comprises of learning the
alphabets, then learn to combine those to form words, which in turn are
combined to form sentences and then sentences are combined to form
paragraphs.

Similarly, instead of straight-away learning how to write programs, we
must first know what alphabets, numbers and special symbols are used in
C, then how using them constants, variables and keywords are
constructed, and finally how are these combined to form an instruction.
A group of instructions would be combined later on to form a program.

#### The C Character Set

A character denotes any alphabet, digit or special symbol used to
represent information. shows the valid alphabets, numbers and special
symbols allowed in C.

::: center
![C Character Set](images/CCharSet.png){#CCharSet width="\\textwidth"}
:::

#### Constants, Variables and Keywords

The alphabets, numbers and special symbols when properly combined form
constants, variables and keywords. Following sections explain
'constants' and 'variables' in detail.

#### C Instructions

Constants, Variables and Keywords are combined to form an instruction to
perform a certain functionality. There are basically three types of
instructions in C:

1.  Type Declaration Instruction

2.  Arithmetic Instruction

3.  Control Instruction

The purpose of each of these instructions is given below:

Type declaration instruction

:   To declare the type of variables used in a C program.

Arithmetic instruction

:   To perform arithmetic operations between constants and variables.

Control instruction

:   To control the sequence of execution of various statements in a C
    program.

These instructions are decoded in the following sections.

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

## C Preprocessor

The C preprocessor is a program that processes the source program before
it is passed to the compiler. There are several steps involved from the
stage of writing a C program to the stage of getting it executed. shows
these different steps along with the files created during each stage.
The input and output to each of these processors is shown in .

::: center
![Different stages of a C
program](images/CCodingSteps.PNG){#CCodingSteps width="45%"}
:::

::: center
![Input and Output to each stage of a C
program](images/CCodingStepsIO.PNG){#CCodingStepsIO width="80%"}
:::

Note that if the source code is stored in a file PR1.C then the expanded
source code gets stored in a file PR1.I. When this expanded source code
is compiled, the object code gets stored in PR1.OBJ. When this object
code is linked with the object code of library functions the resultant
executable code gets stored in PR1.EXE.

The preprocessor offers several features called preprocessor directives.
Each of these preprocessor directives begin with a \# symbol. The
directives can be placed anywhere in a program but are most often placed
at the beginning of a program, before the first function definition.
Preprocessor replaces preprocessor directives (starting with #) with
actual content before compilation.

There are 4 main types of preprocessor directives:

1.  Macro expansion

2.  File Inclusion

3.  Conditional Compilation

4.  Miscellaneous directives

### Macro expansion

Macros are a piece of code in a program which is given some name.
Whenever this name is encountered by the compiler the compiler replaces
the name with the actual piece of code. The '#define' directive is used
to define a macro.

-   Note: There is no semi-colon(';') at the end of macro definition.
    Macro definitions do not need a semi-colon to end.

-   In C programming it is customary to use capital letters for macro
    template.

-   Macros can have arguments.

-   In a macro call the preprocessor replaces the macro template with
    its macro expansion, unlike in a function call the control is passed
    to a function along with certain arguments, some calculations are
    performed in the function and a useful value is returned back from
    the function.

-   Usually macros make the program run faster but increase the program
    size, whereas functions make the program smaller and compact.

### File Inclusion

File Inclusion preprocessor directive tells the compiler to include a
file in the source code program. There are two ways of writing #include
statement:

``` {style="CStyle"}
#include "filename" // This command looks for the file in the current directory as well as the specified list of directories as mentioned in the include search path that might have been set up.
    
    #include <filename> // This command would look for the file in the specified list of directories only.
```

There are two types of files which can be included by the user in the
program:

1.  Header File or Standard files: These files contains definition of
    pre-defined functions like printf(), scanf() etc. These files must
    be included for working with these functions. Different function are
    declared in different header files. standard I/O functions are in
    'iostream' file whereas functions which perform string operations
    are in 'string' file.

2.  user defined files: When a program becomes very large, it is good
    practice to divide it into smaller files and include whenever
    needed. These types of files are user defined files.

### Conditional Compilation

Conditional Compilation directives are type of directives which helps to
compile a specific portion of the program or to skip compilation of some
specific part of the program based on some conditions. This can be done
with the help of two preprocessing commands 'ifdef' and 'endif'.

``` {style="CStyle"}
#ifdef macroname
        statement 1 ;
        statement 2 ;
        statement 3 ;
    #endif
```

If the macro with name as 'macroname' is defined then the block of
statements will execute normally but if it is not defined, the compiler
will simply skip this block of statements. Usecases of Conditional
Compilation directives are:

1.  To comment out or include part(s) of a code with a single definition
    of a macro.

2.  A more sophisticated use of #ifdef has to do with making the
    programs portable, i.e. to make them work on two totally different
    computers.

3.  #ifndef is used to avoid multiple definitions , declaration, and or
    inclusions.

#### #if and #elif Directives

The #if directive can be used to test whether an expression evaluates to
a nonzero value or not. If the result of the expression is nonzero, then
subsequent lines upto a #else, #elif or #endif are compiled, otherwise
they are skipped.

### Miscellaneous directives

Apart from the above directives there are two more directives which are
not commonly used. These are:

#### #undef Directive

The #undef directive is used to undefine an existing macro. Using this
statement will undefine the existing macro. After this statement every
#ifdef statement will evaluate to false.

#### #pragma Directive

This directive is a special purpose directive and is used to turn on or
off some features. This type of directives are compiler-specific, they
vary from compiler to compiler. Some of the #pragma directives are
discussed below:

##### #pragma startup and #pragma exit

These directives helps us to specify the functions that are needed to
run before program startup (before the control passes to main()) and
just before program exit (just before the control returns from main()).

##### #pragma warn Directive

This directive is used to hide the warning message which are displayed
during compilation.

-   #pragma warn -rvl: This directive hides those warning which are
    raised when a function which is supposed to return a value does not
    returns a value.

-   #pragma warn -par: This directive hides those warning which are
    raised when a function does not uses the parameters passed to it.

-   #pragma warn -rch: This directive hides those warning which are
    raised when a code is unreachable. any code written after the return
    statement in a function is unreachable.

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

#### if loop with multiple conditions

An if statement can check multiple conditions in order to execute
statements when the Boolean expression is true. Syntax:

``` {style="CStyle"}
if(boolean_expression_1 && boolean_expression_2 || (! boolean_expression_3) ) {
        /* statement(s) will execute if the boolean expression is true */
    } 
```

C allows usage of three logical operators, namely, &&, \|\| and !. These
are to be read as 'AND' 'OR' and 'NOT' respectively. Don't use the
single symbol \| and & as they are bitwise operators. The first two
operators, && and \|\|, allow two or more conditions to be combined in
an if statement. The ! operator is a NOT operator which returns 1 if a
boolean expression is not true.

#### if-else

An if statement can be followed by an optional else statement, which
executes when the Boolean expression is false. Syntax:

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
statement following the loop.

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
an endless loop. It either produces a continuous output or no output.

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

## Functions

### What is a Function

A function is a self-contained block of statements that takes an input,
perform a coherent task/computation and produces an output. Every C
program can be thought of as a collection of these functions.

### Need for a Function

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

### Defining a Function

A function can also be referred as a method or a sub-routine or a
procedure, etc.

The general form of a function definition in C programming language is
as follows:

``` {style="CStyle"}
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

### Function declaration

Function declaration is also called as function prototype represents
declaring the properties of a function to the compiler. A function
declaration tells the compiler about a function's name, return type, and
parameters. Syntax of a function declaration is:

``` {style="CStyle"}
return_type function_name( parameter list );
```

### Calling a Function

After creating a C function, to use it has to be called to perform the
defined task. To call a function, the required parameters along with the
function name need to be passed, and the returned value has to be stored
if the function has one. Syntax for calling a function is,

``` {style="CStyle"}
return_value = function_name ( parameter list );
```

::: highlight
The function which receives the control from a function call is referred
as the called function.\
The function which transfers the control with a function call is
referred as the calling function.
:::

When a program (calling function) calls a function, the program control
is transferred to the called function. A called function performs a
defined task and upon reaching the end of functionality, it returns the
program control back to the calling function.

### Function Arguments

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

### Summary and additional concepts

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

### Types of functions

There are two primary types of functions:

1.  Library functions printf(), scanf() etc.

2.  User-defined functions function_name_1(), function_name_2() etc.

As the name suggests, library functions are nothing but commonly
required functions grouped together and stored in what is called a
Library. This library of functions is present on the disk and is written
for us by people who write compilers for us. Almost always a compiler
comes with a library of standard functions. The procedure of calling
both types of functions is exactly same.

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

#### Points to note

1.  printf() is used to display the output and scanf() is used to read
    the inputs.

2.  printf() and scanf() functions are declared in \"stdio.h\" header
    file in C library.

3.  All syntax in C language including printf() and scanf() functions
    are case sensitive.

4.  All characters in printf() and scanf() functions must be in lower
    case as C is a case sensitive language.

### Static and dynamic scoping

## Pointers

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

## Arrays

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

## Structure

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

## File Input Output

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

## References

-   [Neso Academy (Youtube Channel) (C Programming & Data Structures
    playlist)](https://youtube.com/playlist?list=PLBlnK6fEyqRhX6r2uhhlubuF5QextdCSM)

-   Let us C by Yashwant Kanetkar

-   [Tutorials
    Point](https://www.tutorialspoint.com/cprogramming/index.htm)

-   [Geeks for
    geeks](https://www.geeksforgeeks.org/c-programming-language/)

-   [The C book](https://publications.gbdirect.co.uk/c_book/)
