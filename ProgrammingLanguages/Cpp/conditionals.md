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

## if

An if statement consists of a boolean expression followed by one or more
statements. Syntax:

```c
if(boolean_expression) {
    /* statement(s) will execute if the boolean expression is true */
    }
```

If the Boolean expression evaluates to true, then the block of code
inside the 'if' statement will be executed. If the Boolean expression
evaluates to false, then the first set of code after the end of the 'if'
statement (after the closing curly brace) will be executed.

### 

if-else An if statement can be followed by an optional else statement,
which executes when the Boolean expression is false. Syntax:

```c
if(boolean_expression) {
        /* statement(s) will execute if the boolean expression is true */
    } else {
        /* statement(s) will execute if the boolean expression is false */
    }
```

If the Boolean expression evaluates to true, then the if block will be
executed, otherwise, the else block will be executed.

### Nested if

It is always legal in C programming to nest if-else statements, which
means one can use one if or else-if statement inside another if or
else-if statement(s). Syntax:

```c
if( boolean_expression 1) {    
       /* Executes when the boolean expression 1 is true */
       if(boolean_expression 2) {
          /* Executes when the boolean expression 2 is true */
       }
    }
```

You can nest else if-else in the similar way as you have nested if
statements.

## switch

A switch statement allows a variable to be tested for equality against a
list of values. Each value is called a case, and the variable being
switched on is checked for each switch case. This is also a great
replacement to long else if constructs. Syntax:

```c
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

### Nested switch

It is possible to have a switch as a part of the statement sequence of
an outer switch. Even if the case constants of the inner and outer
switch contain common values, no conflicts will arise. Syntax:

```c
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
