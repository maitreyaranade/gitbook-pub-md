The C preprocessor is a program that processes the source program before
it is passed to the compiler. There are several steps involved from the
stage of writing a C program to the stage of getting it executed. shows
these different steps along with the files created during each stage.
The input and output to each of these processors is shown in .


![Different stages of a C
program](images/CCodingSteps.PNG)



![Input and Output to each stage of a C
program](images/CCodingStepsIO.PNG)


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

## Macro expansion

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

## File Inclusion

File Inclusion preprocessor directive tells the compiler to include a
file in the source code program. There are two ways of writing #include
statement:

```c
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

## Conditional Compilation

Conditional Compilation directives are type of directives which helps to
compile a specific portion of the program or to skip compilation of some
specific part of the program based on some conditions. This can be done
with the help of two preprocessing commands 'ifdef' and 'endif'.

```c
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

### #if and #elif Directives

The #if directive can be used to test whether an expression evaluates to
a nonzero value or not. If the result of the expression is nonzero, then
subsequent lines upto a #else, #elif or #endif are compiled, otherwise
they are skipped.

## Miscellaneous directives

Apart from the above directives there are two more directives which are
not commonly used. These are:

### #undef Directive

The #undef directive is used to undefine an existing macro. Using this
statement will undefine the existing macro. After this statement every
#ifdef statement will evaluate to false.

### #pragma Directive

This directive is a special purpose directive and is used to turn on or
off some features. This type of directives are compiler-specific, they
vary from compiler to compiler. Some of the #pragma directives are
discussed below:

#### #pragma startup and #pragma exit

These directives helps us to specify the functions that are needed to
run before program startup (before the control passes to main()) and
just before program exit (just before the control returns from main()).

#### #pragma warn Directive

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
