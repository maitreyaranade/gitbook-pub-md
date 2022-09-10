# Introduction

Logic circuits for digital systems maybe combinational or sequential. A
logic circuit is combinational if it's outputs are at any time are a
function of only the present inputs. Combinational circuits employ
boolean functions whereas, sequential circuits employ storage element in
addition to logic gates.\

## Sequential circuits

Their outputs are a function of the inputs and the state of the storage
elements. Hence, the outputs of a sequential circuit depend at any time
on not only the present values of inputs but also on past inputs.\
A combinational circuit consists of an interconnection of logic gates.
Combinational logic gates process the input signals to produce the value
of the output signal.\
Block diagram import fig. 4.1\
A combinational circuit can be specified with a truth table that lists
the output.

# Analysis of combinational circuits

The logic diagram of a combinational circuit has logic gates with no
feedback paths or memory elements. Analysis of a combinational circuit
determines its functionality that is the logic function that the circuit
implements.

Steps involved in the Analysis of combinational circuits method 1

1.  Make sure that the circuit is combinational & not Sequential
    (without memory element & feedback loops).

2.  Obtain the output boolean functions or the truth table. Use
    hierarchy and input, output to add intermediate primary logic gates
    to determine the boolean functions.

3.  Derive truth table: Assign a value to the output base of on every
    input combination.

Steps involved in the Analysis of combinational circuits method 2:

1.  Develop HDL model of the circuit.

2.  Write a test-bench (logic simulation)

3.  Step 1 still requires method 1

# Design procedure

Steps involved in the Design procedure of combinational circuits:

1.  Gather specifications of the circuit.

2.  Determine number of inputs & outputs.

3.  Derive truth table.

4.  Obtain simplified boolean functions.

5.  Draw the logic diagram & verify correctness of the design. Manually
    or by simulation.)

# Binary adder Subtractor

A binary adder performs an addition of 2 bits. Extra bit needed for the
addition which is the higher significant bit of the addition is called a
\"Carry\". The result of addition apart from the carry is called
\"Sum\".

## Half Adder

Half Adder is a combinational circuit which adds 2 1 bit digits.
Previous carry is not used in the Half Adder.\
$$S = x'y + xy'$$ or $$S = x \bigoplus y$$ $$C = xy$$ where, x & y =
inputs,\
S& C = sum & carry

## Full adder

A full adder is a combinational circuits that forms the arithmatic sum
of 3 bits (2 significant bits & carry). x, y are the inputs for the
addition whereas, z is the carry from the previous lower significant
position. $$S = x'y'z + x'yz' + xy'z' + xyz$$ $$C = xy + xz + yz$$ or
$$S = (x \bigoplus y) \bigoplus z$$
$$C = (x \bigoplus y) \bigoplus z + xy$$

where, x, y, z = inputs,\
S& C = sum & carry\
Insert HA full adder diagrams

full adder with 2 half adders and an OR gate

## Binary Adder

Binary adder is a digital circuit that produces the arithmatic sum of 2
binary members. Binary adder is implemented with full adder connected in
cascade. Addition of n-bit numbers require chain of n-full adders.\
Add diagram (4.9) Ripple Carry adder\
For an n-bit adder, there are 2n gate levels for the carry to ripple
from input to output.\
add figure (4.10) Carry lookahead scheme\
Carry & Sum is calculated individually. $C_0$ = input carry\
$C_1$ = $G_0$ + $P_0*C_0$ $P_i$= $A_i \bigoplus B_i$\
$C_2$ = $G_1$ + $P_1*C_1$ $G_i$= $A_i*B_i$\
$C_2$ = $G_2$ + $P_2*C_2$ $S_i$= $P_i \bigoplus C_i$\
$C_{i+1}$ = $G_i$ + $P_i*C_i$\
$G_i$ = Carry Generate\
$P_i$ = Parry Propogate

with this circuit, the speed of operation is gained at the expense of
additional hardware complexity. With this sums have equal propogation
delay.\
figure (4.11) & fig. 4.12\
$S_0$= $C_0 \bigoplus P_0$\
$S_1$= $C_1 \bigoplus P_1$\
$S_2$= $C_2 \bigoplus P_2$\
$S_3$= $C_3 \bigoplus P_3$

## Binary Subtractor

Subtraction of unsigned binary numbers can be done with
compliments.$C_0$ is set to 1. With this, Full adder 0, adds A with 1's
is compliment of B and ($C_0 = 1$), which is,
$$A + 2's complement of (B)$$

## Adder Subtractor

Addition and subtraction operations can be combined into one circuit
with one common binary adder. Add figure (4.13) Four bit adder
subtractor (with overflow deletion). Mode input M controls operation.

M = 1 for Subtraction\
M = 0 for addition\
V = output for detecting overflow.

For unsigned numbers,\
Sum = A - B if A $\geqslant$ B\
Sum = 2's complement (B-A), if (A \< B) 

For signed numbers,\
Sum= A - B, provided there is no overflow

## Overflow

Overflow occurs if 2 'n'-bit numbers are added with 'n+1'-bit result for
signed, unsigned, decimal or binary numbers.\
Overflow is a problem in digital computers because the number of bits
that hold the number is finite. '(n+1)'-bit result cannot be
accommodated by a 'n'-bit word. Detection of an overflow is critical and
is detected with a Flipflop.\
Overflow cannot occur after an addition of one positive and one negative
number. An overflow occurs only if both numbers to be added are either
both positive or both negative.\
\
An overflow condition can be detected by observing the carry into the
sign bit position & the carry out of the sign bit position. If these 2
carries not equal, an overflow has occurred. An XOR gate can be
implemented for the detection.

# Binary Multiplier

Multiplication in binary form is the same as multiplication in decimal
form. The multiplicand is multiplied by each bit of the multiplier,
starting from the least significant bit. Each such multiplication forms
a partial product. Successive partial products are shifted one position
to the left. The final product is obtained from the sum of partial
products.\
Insert Fig 4.15\
similarly 'n'-bit adders can be implemented for in bit multiplicand
instead of Half Adder for 'n'-bit multiplication. For product terms,
same AND gate can be used.

# Magnitude Comparator

Magnitude Comparator is a combinational circuit that compares a numbers
to determine their relative magnitudes. For eg. we consider 2 4-bit
binary numbers $A = A_3A_2A_1A_0$ & $B = B_3B_2B_1B_0$.

## Test for equality

(A = B )iff $a_0 = b_0, a_1 = b_1, .... , a_n = b_n$ for an n-bit
number.\
$x_i = A_i$ XNOR $B_i$ for all 'n'-bits.\
Variable $x_i$ becomes 1 only if both the digits are same.

## Test for comparison

We more from MSB to LSB for the inspection.\
$x_i = A_i$ XNOR $B_i$ for all 'n'-bits.\
if $x_i = 1$ i++ until $x_i = 0$\
if $x_i = 0$

-   (A \> B) if $A_i = 1$, $B_i = 0$

-   (A \< B) if $A_i = 0$, $B_i = 1$

Figure 4:17 four bit magnitude comparator

## Boolean functions for Magnitude Comparator

$$(A > B) = A_3B_3' + x_3A_2B_2' + x_3x_2A_1B_1'+ x_3x_2x_1A_0B_0'$$
$$(A < B) = A_3'B_3 + x_3A_2'B_2 + x_3x_2A_1'B_1+ x_3x_2x_1A_0'B_0$$
$$(A = B) = x_3x_2x_1x_0$$

# Decoders

converts binary A Decoder is a combinational circuit that information
from 'n' input lines to a maximum of an unique output lines. The
decoders that convert n-line inputs to m-line outputs are called n to m
line decoders where $m \leqslant 2^n$.\
Ex. **3 to 8 line decoder** 3 inputs are decoded into 8 outputs. The
input variables represent a binary number & the outputs represent the
eight digits of an octal number.\
Typical Application: binary to octal conversion.\
Insert truth table, logic diagram.

## Decoder Applications

### Decoder Demultiplexer

A decoder with enable input can function as a demultiplexer. Enable line
being the input and other lines as select lines.

### Nested Decoders

Decoder with enable inputs can be connected together to form a larger
decoder circuits. Insert ex. (4.8 practice example)

### combinational Logic

Any combinational circuit with 'n' inputs and 'm' outputs can be
implemented with an 'n' to '$2^n$' line decoder and 'm' OR gates. For
example: Implementation of a full adder with a decoder.

# Encoder

An encoder generates the binary code corresponding to each input value.
Encoder has $2^n$ (or fewer) input lines and 'n' output lines.

## Priority encoder

Priority encoder is an encoder that handles inputs with certain
predefined priority, to generate output accordingly. For ex. Insert
Table 4.8 truth table. High Priority for higher subscript number & V =
valid bit indicator

# Multiplexer

A multiplexer is a combinational circuit that selects binary information
from one of many input lines and directs it to a single output line
based on select lines. If there are 'n'select lines, the input lines
should be '$2^n$'. For ex. 2:1 Mux Insert figure 4.24

MUXs can be combined with common select lines to provide multiple bit
selection logic. Ex. Quadrapule 2:1 line Mux Insert figure

Boolean expression can be implemented with MUX.

## Three state gate (Tristate gate) (Tristate buffer)

MUX can be constructed with Three State Gates (digital circuits that
exhibit 3 States).\
3 states include :

1.  Logic 1

2.  Logic 0

3.  High impedance state

### High impedence state

-   Logic behaves like an open circuit.

-   The circuit has no logic significance.

-   The circuit connected to the output of the 3 state gate is not
    affected by the inputs to the gate.

Tristate gates may perform any conventional logic. However, the most
commonly used tristate gate is the buffer gate. Ex. Implementation of
2:1 Mux with tristate gates.\
Insert Fig 4.30\
4.12 Revisit revision VHDL Verilog
