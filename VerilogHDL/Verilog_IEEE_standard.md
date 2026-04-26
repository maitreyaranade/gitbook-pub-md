# IEEE 1364-2005 Verilog HDL

## 1. Overview of IEEE 1364-2005

IEEE 1364-2005 is the final major standalone Verilog HDL language standard before Verilog was incorporated into SystemVerilog (IEEE 1800). It formalized syntax, semantics, simulation behavior, RTL modeling rules, and interoperability used across ASIC and FPGA flows.

### Why It Matters

- It became the reference language for classic Verilog RTL design and simulation.
- Most legacy ASIC/FPGA codebases still contain IEEE 1364 style Verilog.
- Understanding it is essential for maintaining existing RTL and gate-level netlists.
- Many synthesis coding guidelines still originate from this standard.

### Evolution

| Standard | Importance |
|---|---|
| IEEE 1364-1995 | First major Verilog IEEE standard |
| IEEE 1364-2001 | Major usability improvements |
| IEEE 1364-2005 | Clarifications, cleanup, final mature Verilog |
| IEEE 1800 | SystemVerilog superseded Verilog |

---

## 2. Core Design Philosophy

Verilog models hardware using concurrent processes, event-driven simulation, and multiple abstraction levels.

### Supported Modeling Levels

- Behavioral modeling
- Register Transfer Level (RTL)
- Dataflow modeling
- Gate-level modeling
- Switch-level modeling

### Key Principle

Verilog statements may look software-like, but semantics model hardware concurrency.

Example:

```verilog
assign y = a & b;
assign z = c | d;
```

Both statements represent hardware operating simultaneously.

---

## 3. Basic Source Structure

A Verilog design is built from modules.

```verilog
module adder(input a, b, output y);
assign y = a ^ b;
endmodule
```

### Module Contains

* Port declarations
* Parameters
* Net/register declarations
* Continuous assignments
* Procedural blocks
* Tasks/functions
* Submodule instances

### Notes

* Modules may instantiate other modules.
* Hierarchical design is fundamental.

---

## 4. Lexical Rules

## 4.1 Case Sensitivity

Verilog is case-sensitive.

```verilog
clk != Clk != CLK
```

## 4.2 Comments

```verilog
// single line
/* multi-line */
```

## 4.3 Identifiers

May contain:

* letters
* digits
* `_`
* `$`

Cannot start with digit.

## 4.4 Escaped Identifiers

Used for special names.

```verilog
\my-signal-name 
```

(terminated by whitespace)

---

## 5. Data Values and Logic System

Verilog uses a four-state logic system.

| Value | Meaning        |
| ----- | -------------- |
| 0     | Logic zero     |
| 1     | Logic one      |
| x     | Unknown        |
| z     | High impedance |

### Why Important

Real hardware may have:

* uninitialized signals
* bus contention
* floating tri-state lines

---

## 6. Net Types

Nets model driven connections.

### Common Net Types

* `wire`
* `tri`
* `wand`
* `wor`
* `supply0`
* `supply1`

### Key Rule

Nets do not store values. They reflect driven values.

```verilog
wire y;
assign y = a & b;
```

---

## 7. Variable Types

Variables store procedural values.

### Common Types

* `reg`
* `integer`
* `time`
* `real`
* `realtime`

### Important Clarification

`reg` does **not** automatically mean hardware register. It means procedural assignment variable.

```verilog
reg y;
always @(*) y = a & b;
```

This can synthesize to combinational logic.

---

## 8. Scalars, Vectors, Arrays, Memories

## Scalars

Single bit.

```verilog
reg a;
```

## Vectors

Multi-bit packed signals.

```verilog
reg [7:0] data;
```

## Memories

Array of words.

```verilog
reg [7:0] mem [0:255];
```

256 entries of 8 bits each.

---

## 9. Numbers and Literals

Format:

```text
<size>'<base><value>
```

Examples:

```verilog
8'b10100101
16'h00FF
4'd9
```

### Bases

* `b` binary
* `o` octal
* `d` decimal
* `h` hexadecimal

### Supports x/z digits

```verilog
4'b10xz
```

---

## 10. Operators

## Arithmetic

`+ - * / %`

## Relational

`< <= > >=`

## Equality

`== !=`

## Case Equality

`=== !==`

Includes x/z matching.

## Logical

`! && ||`

## Bitwise

`~ & | ^ ^~`

## Reduction

Unary reduction across vector.

```verilog
&data
|data
^data
```

## Shift

`<< >> <<< >>>`

## Conditional

```verilog
sel ? a : b
```

Used to infer mux logic.

---

## 11. Continuous Assignments

Used for combinational net driving.

```verilog
assign y = (a & b) | c;
```

### Characteristics

* Reevaluates whenever RHS changes.
* LHS usually net type.

---

## 12. Procedural Blocks

Two main procedural processes:

## 12.1 `initial`

Runs once at simulation start.

```verilog
initial begin
  reset = 1;
end
```

Mostly simulation/testbench usage.

## 12.2 `always`

Runs forever.

```verilog
always #5 clk = ~clk;
```

Used in RTL and testbench.

---

## 13. Event Controls and Sensitivity Lists

Used to trigger procedural execution.

## Level Sensitive

```verilog
always @(a or b or sel)
```

## Edge Sensitive

```verilog
always @(posedge clk)
always @(negedge rst_n)
```

## Recommended Combinational Form

```verilog
always @(*)
```

Automatically infers dependencies.

---

## 14. Blocking vs Nonblocking Assignments

## Blocking `=`

Sequential execution within block.

```verilog
a = b;
c = a;
```

`c` gets updated `a`.

## Nonblocking `<=`

Scheduled parallel update.

```verilog
a <= b;
c <= a;
```

`c` gets old `a`.

### Professional Rule

* Use blocking for combinational logic.
* Use nonblocking for sequential clocked logic.

---

## 15. Conditional Statements

## If / Else

```verilog
if(en) y = a;
else y = b;
```

## Case

```verilog
case(sel)
2'b00: y = a;
2'b01: y = b;
default: y = 0;
endcase
```

### Variants

* `case`
* `casex`
* `casez`

Use cautiously because wildcards may hide bugs.

---

## 16. Loops

Supported procedural loops:

* `for`
* `while`
* `repeat`
* `forever`

Example:

```verilog
for(i=0;i<8;i=i+1)
 sum[i] = a[i] ^ b[i];
```

---

## 17. Tasks and Functions

## Functions

* Return one value
* No timing control

```verilog
function parity;
input [7:0] d;
begin
 parity = ^d;
end
endfunction
```

## Tasks

* May have multiple outputs
* Can include delays/events

```verilog
task load_data;
input [7:0] d;
begin
 data = d;
end
endtask
```

---

## 18. Parameters

Used for reusable configurable modules.

```verilog
parameter WIDTH = 8;
reg [WIDTH-1:0] data;
```

### Override at Instantiation

```verilog
fifo #(16) u1 (...);
```

---

## 19. Generate Constructs (1364-2005 Important RTL Feature)

Used for elaboration-time hardware replication.

## Generate For

```verilog
genvar i;
generate
for(i=0;i<8;i=i+1)
 begin
 end
endgenerate
```

## Generate If / Case

Conditional structural generation.

Useful for scalable parameterized RTL.

---

## 20. Timing and Delay Modeling

Delay syntax:

```verilog
#5 a = b;
assign #3 y = a & b;
```

### Delay Types

* Rise
* Fall
* Turn-off

Used mainly in simulation/gate-level models.

---

## 21. User Defined Primitives (UDP)

Allows truth-table based primitive creation.

Example uses:

* Custom latch
* Special logic primitive

Less common in modern RTL but present in standard.

---

## 22. Gate-Level Primitive Instances

Built-in primitives:

* `and`
* `or`
* `nand`
* `nor`
* `xor`
* `buf`
* `not`
* transistor primitives

Example:

```verilog
and g1(y,a,b);
```

---

## 23. Specify Blocks

Used for path delays and timing checks.

```verilog
specify
(a *> y) = 3;
endspecify
```

Used in standard-cell simulation models.

---

## 24. System Tasks and Functions

Common examples:

## Display / Monitor

```verilog
$display(...)
$monitor(...)
$strobe(...)
```

## Simulation Control

```verilog
$finish
$stop
$time
```

## File I/O

```verilog
$fopen
$fdisplay
$fclose
```

## Memory Load

```verilog
$readmemb
$readmemh
```

## Waveforms

```verilog
$dumpfile
$dumpvars
```

---

## 25. Scheduling Semantics (Very Important)

Verilog simulator uses event queues.

Typical regions:

* Active
* Inactive
* NBA (nonblocking assignment)
* Monitor/Postponed

### Why Important

Explains race conditions and why blocking/nonblocking behave differently.

---

## 26. Strength Modeling

Signals may have drive strengths:

* strong
* weak
* pull
* supply

Used for tri-state buses and switch-level models.

Less common in synthesizable RTL.

---

## 27. Compilation Units and Directives

Preprocessor directives:

* `` `define ``
* `` `include ``
* `` `ifdef ``
* `` `timescale ``

Example:

```verilog
`timescale 1ns/1ps
```

---

## 28. Synthesizable Subset (Industry Practice)

Although standard allows many features, practical synthesis usually uses:

* Modules
* Parameters
* `wire`, `reg`
* `assign`
* `always`
* `if/case`
* loops with static bounds
* tasks/functions (restricted)
* generate blocks

Usually avoided in synthesis:

* delays
* force/release
* specify
* UDPs
* event-based testbench-only code

---

## 29. Common RTL Templates

## Combinational Logic

```verilog
always @(*) begin
  case(sel)
    2'b00: y = a;
    default: y = b;
  endcase
end
```

## Sequential Logic

```verilog
always @(posedge clk or negedge rst_n)
begin
 if(!rst_n) q <= 0;
 else q <= d;
end
```

---

## 30. Common Pitfalls

## Latch Inference

Missing assignment path in combinational block.

## Race Conditions

Multiple blocks updating same signal improperly.

## Mixing Blocking/NBA Incorrectly

Can create simulation mismatch.

## Width Mismatch

Silent truncation or extension.

## Casex Misuse

May mask unknown states.

---

## 31. What 1364-2005 Improved

Compared with earlier versions:

* Better clarification of ambiguous semantics
* Mature generate constructs
* Improved syntax consistency
* Better interoperability with toolchains
* Final cleanup before SystemVerilog transition

---

## 32. Relationship to SystemVerilog

SystemVerilog (IEEE 1800) extends Verilog with:

* `logic`
* `always_comb`
* `always_ff`
* interfaces
* classes
* assertions
* randomization
* packages

But classic Verilog 1364 remains foundational.

---

## 33. Professional Revision Takeaways

* IEEE 1364-2005 is the mature classic Verilog standard.
* Modules are the core design unit.
* Four-state logic (`0,1,x,z`) is fundamental.
* Use `assign` for combinational nets.
* Use blocking for combinational procedural logic.
* Use nonblocking for clocked sequential logic.
* Parameters and generate enable scalable RTL.
* Many standard features are simulation-only, not synthesis-friendly.
* Understanding scheduling semantics is critical for debug.
* Most modern RTL still reflects IEEE 1364 coding principles.

---

## 34. Interview Focus Areas

Know these thoroughly:

* Blocking vs nonblocking
* Wire vs reg
* Case vs casex vs casez
* Sensitivity lists
* Latch inference
* FSM coding style
* Generate loops
* Signed vs unsigned behavior
* Race conditions
* Simulation vs synthesis mismatch

```
```
