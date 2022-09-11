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

## Arithmetic Operators

Arithmetic Operators are used to performing mathematical calculations.
All the operators are binary operators which mean they require 2
operands to perform operation. There are 5 types of Arithmetic
Operators.

1.  \+ Addition

2.  \- Subtraction

3.  \* Multiplication

4.  / Division

5.  \% Modulus

## Increment/Decrement Operators

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

### Increment Operator (++)

-   Increment operator is used to increment the value of a variable by
    one.

-   a++ is equivalent to a = a+1;

-   There are 2 types of Increment Operator:

    -   Pre-increment operator (++a)

    -   Post-increment operator (a++)

-   'rvalue' cannot be used with increment operator.

### Decrement Operator (--)

-   Decrement operator is used to decrement the value of a variable by
    one.

-   a-- is equivalent to a = a-1;

-   There are 2 types of decrement Operator:

    -   Pre-decrement operator (--a)

    -   Post-decrement operator (a--)

-   'rvalue' cannot be used with decrement operator.

## Relational Operators

-   Relational operators are used to comparing two quantities or values.

-   All the relational operators are binary operators.

-   All the relational operators will return either True or False.

1.  == Is equal to

2.  != Is not equal to

3.  \> Greater than

4.  \< Less than

5.  \>= Greater than or equal to

6.  \<= Less than or equal to

## Logical Operators

C provides three logical operators when we test more than one condition
to make decisions.

1.  && And operator: It performs logical conjunction of two expressions.
    (if both expressions evaluate to True, result is True. If either
    expression evaluates to False, the result is False)

2.  \|\| Or operator: It performs a logical disjunction on two
    expressions. (if either or both expressions evaluate to True, the
    result is True)

3.  ! Not operator: It performs logical negation on an expression.

## Bitwise Operators

C provides a special operator for bit operation between two variables.

1.  \<\< Binary Left Shift Operator

2.  \>\> Binary Right Shift Operator

3.  B̃inary Ones Complement Operator

4.  & Binary AND Operator

5.  B̂inary XOR Operator

6.  \| Binary OR Operator

## Assignment operators

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

## Conditional operators

C offers only one ternary (requires 3 operands) operator which is the
conditional operator (?: in combination) to construct conditional
expressions. Ex. result = (Expression1) ? Expression2 : Expression3 ;

1.  ? : Conditional Expression

## Special operators

C supports some special operators

1.  sizeof() Returns the size of a memory location.

2.  & Returns the address of a memory location.

3.  \* Pointer to a variable.

### Comma operator (,)

-   Comma operator can be used as a separator.\
    For example: int var1 = 0, var2 = 1;

-   Comma operator can be used as a \"operator\".\
    For example: int var1 = (0, 1, 2);\
    Comma operator returns the rightmost operand in the expression and
    it simply evaluates the rest of the operands and finally reject
    them.

-   Comma operator has the least precedence among all the operators
    available in C language.

## Token generation

-   Lexical analysis is the first phase in the compilation process.

-   Lexical analyzer (scanner) scans the whole source program and it
    finds the meaningful sequence of characters(lexemes) then it
    converts it into a token.

-   Token: lexemes mapped into token-name and attribute-value.\
    Example: int -\> \<keyword, int\>

-   Lexical analyzer always matches the longest character sequence.

## Operator precedence & associativity

Operator precedence determines the grouping of terms in an expression
and decides how an expression is evaluated. Certain operators have
higher precedence than others. For example, the multiplication operator
has a higher precedence than the addition operator.

### Operator Precedence

Operator precedence is used to evaluate the order of operators evaluated
in an expression. In C programming, every operator has a priority. When
there is more than one operator in the given expression, the operator
with higher precedence or priority is evaluated first and the operator
with the least priority is evaluated later.

### Operator Associativity

Operator associativity is used to evaluate the order of operators with
equal precedence in an expression. In the C programming language, when
an expression contains multiple operators with equal or same precedence,
we use associativity to determine the order of evaluation of operators.

Enter operator table here
