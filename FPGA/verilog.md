## Verilog

Operator Precedence: The order of the table tells what operation is made
first, the first ones has the highest priority. The () can be used to
override default.

### Features of Verilog

-   Case sensitive

-   All keywords are lowercase

-   Semicolon is the statement terminator

-   //: single line comment

-   /\* \*/: multiline comment

### Verilog Code structure

Sample code to explain verilog code structure:

``` {style="verilog-style"}
// timescale directive tells the simulator the base units and precision of the simulation 
        `timescale 1 ns / 10 ps 
        module name (input and outputs); 
        // parameter declarations 
        parameter parameter_name = parameter value; 
        // Input output declarations 
        input in1; 
        input in2; // single bit inputs 
        output [msb:lsb] out; // a bus output 
        // internal signal register type declaration - register types (only assigned within always statements). reg register
        variable 1; 
        reg [msb:lsb] register variable 2; 
        // internal signal. net type declaration - (only assigned outside always statements) wire net variable 1; 
        // hierarchy - instantiating another module 
        reference name instance name ( 
        .pin1 (net1), 
        .pin2 (net2), 
        . 
        .pinn (netn) 
        ); 
        // synchronous procedures 
        always @ (posedge clock) 
        begin 
        . 
        end 
        // combinatinal procedures 
        always @ (signal1 or signal2 or signal3) 
        begin 
        . 
        end 
        assign net variable = combinational logic; 
        endmodule 
```

Types of elements in Verilog are Wires and Registers.

-   **Wires** make connections between elements. They implement nets.
    Otherwise known as nodes in the circuit. Since wires are simply
    nets. They are driven by signals. They may not always have a value.
    So, they may have a high impedance or High-Z state. Which is neither
    a zero or one. But, equivalent to a floating node.

-   **Registers** can also make connections between elements in the
    code. But, registers can be a assign values. And they hold those
    values until the next assignment. And finally registers can drive
    wires.

Just a quick warning! The name register is misleading. Because Verilog
registers do not necessary produce Flip flops in a FPGA or ASIC
implementation. The synthesis tool will decide if the behavior really
requires and actual register.

### Net data types

-   wire: represents a node or connection

-   tri: represents a tri-state node

-   supply0: constant logic 0

-   supply1: constant logic 1

### Variable data types

-   reg: unsigned variable of any bit size (reg signed : signed
    implementation)

-   integer: signed 32-bit variable

-   real,time,realtime: non-synthesizable

### Two methods to define port connections

-   By ordered list: port connections defined by the order of the port
    list in the lower-level module.

-   By name: port connections defined by name, order of the port
    connections does not matter.

-   Mixed is not possible.

Parameter is value assigned to a symbolic name. localparam is same as
parameter but cannot be overwritten.

### Operators

Verilog operators operate on several data types to produce an output.
Not all Verilog operators are synthesible (can produce gates). Some
operators are similar to those in the C language. Remember, you are
making gates, not an algorithm (in most cases).


  **Character**                      **Operation**                  **Type of operator**
  ---------------------------------- ------------------------------ ----------------------
  \+                                 Add                            Arithmatic
  \-                                 Subtract                       Arithmatic
  /                                  Divide                         Arithmatic
  \*                                 Multiply                       Arithmatic
  \%                                 Modulus                        Arithmatic
  $\sim$                             Invert                         bitwise
  &                                  And                            bitwise
  \|                                 Or                             bitwise
  $\wedge$                           Xor                            bitwise
  $\wedge$$\sim$ or $\sim$$\wedge$   Xnor                           bitwise
  &                                  And all bits                   reduction
  $\sim$ &                           Nand all bits                  reduction
  \|                                 Or all bits                    reduction
  $\sim$ \|                          Nor all bits                   reduction
  $\wedge$                           Xor all bits                   reduction
  $\wedge$ or $\sim$$\wedge$         Xnor all bits                  reduction
  \>                                 Greater than                   Relational
  \<                                 Smaller than                   Relational
  \>=                                Greater than or equal          Relational
  \<=                                Smaller than or equal          Relational
  ==                                 Equality                       Relational
  !=                                 Inequality                     Relational
  ===                                Case equality                  Relational
  !===                               Case inequality                Relational
  !                                  Not true                       Logical
  &&                                 Both expressions true          Logical
  \|\|                               One or both expressions true   Logical
  \>\>                               Shift right                    shift
  \<\<                               Shift left                     shift
  ?                                  Conditions testing             Misc
  {}                                 Concatenate                    Misc
  {{}}                               Replicate                      Misc


Operator Precedence: The order of the table tells what operation is made
first, the first ones has the highest priority. The () can be used to
override default.


![Operator
Precedence](images/OperatorPrecedence.png)


### Assignments

Assignment statements are categorized as follows:

Continuous assignments

:   Model the behavior of combinational logic by using expressions and
    operators. Always active: LHS is updated upon RHS changes LHS must
    be a net data type. RHS can be a bet, register or function calls.
    Delay values can be assigned to model gate delays.

Procedural assignments

:   Procedural assignments are made inside procedural blocks such as:\
    i. initial: Initializes behavioral statements for simulation.
    Initial block starts at 0, executes only once during simulation, and
    then does not execute again.\
    ii. always: Descibe the circuit functionality using behavioral
    statements. Block executes concurrently starting at time 0 and
    continuously in a looping fashion.

    Each always and initial block represents a separate process.
    Processes run in parallel and start at simulation time 0. Statements
    inside a process execute sequentially. always and inital blocks
    cannot be nested.

    Two types of procedural assignents:

    -   Blocking assignments: executed in the order they are specified
        in a sequential block

    -   Non blocking assignments: Allow scheduling of assignments
        without blocking execution of the statements that follow in a
        sequential block.

### RTL processes

There are two types of RTL processes:

-   Combinatorial Process: sensitive to all inputs used in the
    combinatorial logic. ex: always @(a,b,sel)

-   Clocked proess: sensitive to a clock or/and control signal. ex:
    always @(posedge clk, posedge rst)

### Behavioral statements

Must be inside a procedural block (initial or always)

if-else

:   conditions are evaluated in order from top to bottom, Prioritization

case

:   conditions are evaulated at once, No prioritization

Loop

:   used for repetitive operations.

    -   forever: infinite loop, non synthesizable

    -   repeat: executes a fixed number of times

    -   while: repeates until condition is achieved, non synthesizable

    -   for: executes initial assignment at the start of the loop and
        then executes loop body if expression is true.

### Subprograms

Defined within a module. Uses: replacing repititive code, enhancing
readability.

Functions

:   return a value based on its inputs, produces combinational logic.
    Always execute in zero time. Cannot pause their execution. Cannot
    contain delay, event, or timing control statements. Must have at
    least one input argument. Arguments may not be outputs, or inouts.
    Always return a single value. Ex: assign multOut = mult(ina, inb)

Tasks

:   Like procedures in other languages, can be combinatorial or
    registered. May execute in non-zero simulation time. May contain
    delay, event, or timing control statements. May have zero or more
    input, output, or inout arguments. Ex: stmOut(nxt, first, sel,
    filter)

    
    ![Verilog Functions and
    Tasks](images/VerilogFuncTasks.png)
    
