# Tasks and Functions in Verilog

## 1. Overview

Tasks and functions are used to modularize and reuse commonly used behavioral code in Verilog designs.

- They help reduce code duplication and improve readability and maintainability.
- Both are defined within a module and are part of the design hierarchy.
- They are invoked from `initial`, `always`, or other tasks/functions.
- They contain only behavioral statements and cannot include `always` or `initial` blocks.

---

## 2. Tasks vs Functions

### Functional Distinction

- A **function** is used for combinational logic that:
  - Executes in zero simulation time.
  - Returns exactly one value.
  - Has only input arguments.

- A **task** is used for more general procedures that:
  - May include delays, events, or timing control.
  - Can return multiple values via output/inout arguments.
  - Can have zero or more arguments.

### Summary of Differences

| Feature | Function | Task |
|--------|--------|------|
| Execution time | Zero time | May consume time |
| Timing control | Not allowed | Allowed |
| Return value | Single value | No direct return, multiple outputs allowed |
| Arguments | Only inputs | Input, output, inout |
| Invocation capability | Can call functions only | Can call both tasks and functions |

---

## 3. Tasks

### 3.1 When to Use Tasks

- The logic includes delays or timing control.
- Multiple outputs are required.
- There are no input arguments.

### 3.2 Task Declaration and Invocation

Tasks are declared using `task` and `endtask`.

* Arguments are passed in positional order.
* Output values are returned when the task completes.
* Tasks can call other tasks and functions.

Example:
```verilog
task bitwise_op;
  input [7:0] a, b;
  output [7:0] out;
  begin
    out = a & b;
  end
endtask
```

Invocation:

```verilog
bitwise_op(A, B, OUT);
```

### 3.3 Task with Timing Control

Tasks can include delays, making them suitable for sequential behavior.

Example:

```verilog
task delayed_and;
  input a, b;
  output out;
  begin
    #10 out = a & b;
  end
endtask
```

### 3.4 Automatic (Re-entrant) Tasks

* By default, tasks are **static**, meaning variables are shared across calls.
* This can cause incorrect behavior if tasks are invoked concurrently.
* Each call gets its own independent variable space.
* Recommended when tasks may be called concurrently.

To solve this, use `automatic`:

```verilog
task automatic compute;
```

---

## 4. Functions

### 4.1 When to Use Functions

A function must satisfy all of the following:

* No delay or timing control.
* At least one input argument.
* Returns exactly one value.
* No output or inout arguments.
* No nonblocking assignments.

### 4.2 Function Declaration and Return Mechanism

Functions use an implicit variable (same name as function) to return values.
* Return value is assigned to the function name.
* Default return width is 1 bit unless specified.

Example:

```verilog
function parity;
  input [7:0] data;
  begin
    parity = ^data;
  end
endfunction
```

Invocation:

```verilog
p = parity(data);
```

### 4.3 Function with Explicit Width

Example:

```verilog
function [31:0] shift;
  input [31:0] data;
  input dir;
  begin
    shift = (dir) ? (data >> 1) : (data << 1);
  end
endfunction
```

### 4.4 Automatic (Recursive) Functions

* Functions can be declared `automatic` for recursion or concurrent calls.

* Each call gets independent storage.
* Enables recursion and safe concurrent usage.

Example:

```verilog
function automatic integer factorial;
  input integer n;
  begin
    if (n <= 1)
      factorial = 1;
    else
      factorial = n * factorial(n-1);
  end
endfunction
```

---

## 5. Constant Functions

* Used to compute values at compile/elaboration time.
* Commonly used for parameter calculations.

Example:

```verilog
function integer clog2;
  input integer depth;
  begin
    for(clog2 = 0; depth > 0; clog2 = clog2 + 1)
      depth = depth >> 1;
  end
endfunction
```

Usage:

```verilog
input [clog2(256)-1:0] addr;
```

---

## 6. Signed Functions

* Functions can return signed values using `signed`.
* Enables signed arithmetic comparisons and operations.

Example:

```verilog
function signed [31:0] compute;
```

---

## 7. Best Practices

* Use **functions** for combinational logic and calculations.
* Use **tasks** for:
  * Sequential behavior
  * Delays and timing control
  * Multiple outputs
* Avoid using static tasks when concurrent execution is possible; prefer `automatic`.
* Keep functions simple and side-effect free.
* Ensure correct argument ordering during task invocation.
* Use functions for reusable logic like parity, encoding, or arithmetic operations.

---