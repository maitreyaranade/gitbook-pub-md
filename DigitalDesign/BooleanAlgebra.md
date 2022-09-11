# Boolean algebra

THe most Common postulates used to formulate various algebraic
structures are:

1.  Closure: A set S is closed with respect to a binary operator if, for
    every pair of elements of S, the binary operator specifies a rule
    for obtaining a unique & element of S.

2.  Associative law: $$(x*y)*z = x*(y*z)$$ for all $x,y,z \varepsilon S$

3.  Commutative law: $$x*y = y*x$$ for all $x,y\varepsilon S$

4.  Identity element: if there exists an element $e \varepsilon S$ with
    $$e*x = x*e = x$$ for every $x \varepsilon S$

5.  Inverse: A set S having the identity element e - is said to have an
    inverse when , $$x*y=e$$

6.  Distributive law: $$x*(y.z) = (x*y).(x*z)$$

# Basic theorems & Properties of boolean algebra

## Duality

If the operators and the elements are interchanged, every algebraic
expression deducible from the postulates of boolean algebra remains
unchanged.

## Basic theorems

\- Insert table 2.1

## Operator Precedence

1.  Parentheses

2.  NOT

3.  AND

4.  OR

# Boolean functions

A boolean function is described by an algebraic expression consisting of
binary variables, the constants (0 & 1) and the logic operation symbols.
$$eg. F_1 = x + y'z$$

A boolean a n function expresses the logical relationship between binary
variables & is evaluated by determining the binary value of the
expression for all possible values of the variables.

## Truth table

is a boolean function can be represented in a truth table. Truth table
enlists all the possible combinations $2^n$ of the variables (n), and
the corresponding output value of boolean function.\
A boolean function can be transformed into a circuit diagram composing
logic gates from algebraic expression which is also known as schematic.

# Canonical & standard forms

revisit Insest logic gates one pager Fig. 205

# Integrated Circuits

An integrated circuit (IC) is fabricated on a die of a silicon
semiconductor crystal, called a chip, containing the electronic
components for constructing digital gates.

## Levels of Integration

Digital ICs are categorized according to the complexity of their
circuits.

-   SSI (Small Scale Integration): Number of gates are less than 10.

-   MSI (Medium Scale integration): Number of gates are between 10 to
    1000 Gates.

-   LSI (Large Scale Integration): Number of gates are in thousands ex.
    Processors, memory chips & programmable logic devices.

-   VLSI (Very Large Scale Integrations): Number of gates are in
    millions ex. complex microcomputer chips.

# Computer Aided Design of VLSI circuits

Integrated circuits having sub-micron geometric features are
manufactured optically by projecting light onto silicon wafers. The
design of digital systems with VLSI circuits containing millions of
gates is an enormous task. Only with the help of CAD tools, this task is
made possible considering system complexity.\
EDA (Electronic Design Automation) automates multiple steps of design
phases of ICs. Typical design flow,

1.  Design entry: Schematic / HDL based model

2.  phyical realisation

    1.  ASIC

    2.  FPGA

    3.  PLD

    4.  Full Custom IC

3.  Hardware fabrication with CAD & EDA (Schematic entry)
