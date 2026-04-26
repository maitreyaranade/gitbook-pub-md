A loop statement allows the programmer to execute a statement or group
of statements multiple times. C Programming languages provide various
control structures that allow for more complicated execution paths.

In general, loops are a programming element that repeat a portion of
code a set number of times until the desired process is complete.
Repetitive tasks are common in programming, and loops are essential to
save time and minimize errors. Loops make code more readable, manageable
and organized. C language provides the following types of loops to
handle looping requirements:

## while

A while loop in C programming repeatedly executes a target statement as
long as a given condition is true. It tests the condition before
executing the loop body. Syntax:

```c
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

## for

A for loop is a repetition control structure that allows you to
efficiently write a loop that needs to execute a specific number of
times. Syntax:

```c
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

## do-while

Unlike for and while loops, which test the loop condition at the top of
the loop, the do-while loop in C programming checks its condition at the
bottom of the loop. A do-while loop is similar to a while loop, except
the fact that it is guaranteed to execute at least one time. Syntax:

```c
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

## Nested loops

C programming allows to use one loop inside another loop. A final note
on loop nesting is that you can put any type of loop inside any other
type of loop. For example, a 'for' loop can be inside a 'while' loop or
vice versa.

## Loop Control Statements

Loop control statements change execution from its normal sequence. When
execution leaves a scope, all automatic objects that were created in
that scope are destroyed. C supports the following control statements:

### break

When a break statement is encountered inside a loop, the loop is
immediately terminated and the program control resumes at the next
statement following the loop.

It can also be used to terminate a case in the switch statement. If you
are using nested loops, the break statement will stop the execution of
the innermost loop and start executing the next line of code after the
block. Syntax:

```c
break;
```

### continue

Instead of forcing termination, the continue statement forces the next
iteration of the loop to take place, skipping any code in between.

For the for loop, continue statement causes the conditional test and
increment portions of the loop to execute. For the while and do\...while
loops, continue statement causes the program control to pass to the
conditional tests. Syntax:

```c
break;
```

### goto

A goto statement in C programming provides an unconditional jump from
the 'goto' to a labeled statement in the same function.

**NOTE:** Use of goto statement is highly discouraged in any programming
language because it makes difficult to trace the control flow of a
program, making the program hard to understand and hard to modify. Any
program that uses a goto can be rewritten to avoid them. Syntax:

```c
goto label;
      /* statement(s) exempted from execution */
   label: statement;
```

Here label can be any plain text except C keyword and it can be set
anywhere in the C program above or below to goto statement.

## The Infinite Loop

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

```c
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
