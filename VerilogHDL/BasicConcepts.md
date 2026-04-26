- [Verilog Basic Concepts](#verilog-basic-concepts)
  - [1. Overview](#1-overview)
  - [2. Lexical Conventions](#2-lexical-conventions)
    - [General Rules](#general-rules)
    - [Whitespace](#whitespace)
    - [Comments](#comments)
    - [Operators](#operators)
    - [Number Representation](#number-representation)
      - [Sized Numbers](#sized-numbers)
      - [Unsized Numbers](#unsized-numbers)
      - [Special Values](#special-values)
      - [Additional Rules](#additional-rules)
    - [Strings](#strings)
    - [Identifiers and Keywords](#identifiers-and-keywords)
    - [Escaped Identifiers](#escaped-identifiers)
  - [3. Data Types in Verilog](#3-data-types-in-verilog)
    - [Value Set](#value-set)
  - [4. Nets](#4-nets)
  - [5. Registers](#5-registers)
  - [6. Vectors](#6-vectors)
    - [Vector Operations](#vector-operations)
  - [7. Integer, Real, and Time Data Types](#7-integer-real-and-time-data-types)
    - [Integer](#integer)
    - [Real](#real)
    - [Time](#time)
  - [8. Arrays](#8-arrays)
  - [9. Memories](#9-memories)
  - [10. Parameters and Constants](#10-parameters-and-constants)
    - [Local Parameters](#local-parameters)
  - [11. Strings in Registers](#11-strings-in-registers)
  - [12. System Tasks](#12-system-tasks)
    - [Displaying Information](#displaying-information)
    - [Monitoring Signals](#monitoring-signals)
    - [Simulation Control](#simulation-control)
  - [13. Compiler Directives](#13-compiler-directives)
    - [`define`](#define)
    - [`include`](#include)


---

# Verilog Basic Concepts

## 1. Overview

This chapter establishes the foundational constructs and conventions used in Verilog HDL. These concepts are essential for understanding how Verilog models real hardware behavior, including data representation, simulation, and coding structure.

---

## 2. Lexical Conventions

Verilog syntax is similar to the C programming language and consists of tokens such as identifiers, keywords, numbers, operators, and strings.

### General Rules
- Verilog is a case-sensitive language.
- Keywords are always written in lowercase.
- Code is interpreted as a stream of tokens.

### Whitespace
- Spaces, tabs, and newlines are ignored except when separating tokens.
- Whitespace inside strings is preserved.

### Comments
- Single-line comments start with `//`.
- Multi-line comments are enclosed within `/* */`.
- Nested multi-line comments are not allowed.

### Operators
- Unary operators act on a single operand.
- Binary operators operate between two operands.
- Ternary operators use the conditional format `?:`.

### Number Representation
- Numbers can be specified as sized or unsized.

#### Sized Numbers
- Format: `<size>'<base><value>`
- Supported bases: binary (b), decimal (d), hexadecimal (h), octal (o)
- Eg. 4'b1111; 12'habc;

#### Unsized Numbers
- Default to decimal and at least 32 bits.
- Eg. 'b1111; 'hc3; // Both of these are 32 bit numbers

#### Special Values
- `x` represents unknown values.
- `z` represents high impedance (floating state).
- `?` can be used as an alternative to `z` in specific contexts.

#### Additional Rules
- Negative numbers use a minus sign before the size. Eg. -6'd3;
- Underscores improve readability and are ignored. Eg. 8'b1110_0111;
- Automatic bit extension applies based on the most significant bit.

### Strings
- Strings are enclosed in double quotes.
- They must be contained on a single line.
- Each character occupies one byte (ASCII).

### Identifiers and Keywords
- Identifiers name variables, modules, and signals.
- They consist of letters, digits, underscores, and `$`.
- They must not start with a digit or `$`.

### Escaped Identifiers
- Begin with `\` and end with whitespace.
- Allow use of special characters in names.

---

## 3. Data Types in Verilog

Verilog data types closely model hardware behavior and signal representation.

### Value Set
Verilog supports four logic values:
- `0` represents logic low.
- `1` represents logic high.
- `x` represents unknown.
- `z` represents high impedance.

Signal strengths are also defined to resolve conflicts between multiple drivers.

---

## 4. Nets

- Nets represent physical connections between hardware elements.
- They continuously reflect the value driven by connected devices.
- The most commonly used net type is `wire`.
- Default value of a net is `z` if undriven.

Key characteristics:
- Nets do not store values.
- They must be driven by some source.

---

## 5. Registers

- Registers represent storage elements in Verilog.
- They retain their value until explicitly changed.
- Declared using the `reg` keyword.

Important distinctions:
- A Verilog register is not necessarily a physical flip-flop.
- Registers do not require a clock to update values.
- Default value of a register is `x`.

Registers can also be declared as signed for arithmetic operations.

---

## 6. Vectors

- Vectors represent multi-bit nets or registers.
- Declared using range notation such as `[msb:lsb]`.

Key concepts:
- Default is scalar (1-bit) if no range is specified.
- Bit ordering determines significance, with the left index as MSB.

### Vector Operations
- Individual bits and ranges can be accessed using indexing.
- Part-select allows selection of subsets of bits.
- Variable part-select enables dynamic access using expressions.

---

## 7. Integer, Real, and Time Data Types

### Integer
- Used for general-purpose computations.
- Typically at least 32 bits and signed.

### Real
- Used for floating-point values.
- Supports decimal and scientific notation.
- Values are rounded when assigned to integers.

### Time
- Used to store simulation time.
- Typically at least 64 bits.
- Retrieved using the system function `$time`.

---

## 8. Arrays

- Arrays allow storage of multiple elements of the same type.
- Can be one-dimensional or multi-dimensional.

Key characteristics:
- Each element can be a scalar or vector.
- Accessed using index notation.
- Arrays differ from vectors, which represent a single multi-bit value.

---

## 9. Memories

- Memories are modeled as one-dimensional arrays of registers.
- Used to represent RAM, ROM, and register files.

Key points:
- Each element represents a word.
- Each word can be multiple bits wide.
- Access is performed using a single index.

---

## 10. Parameters and Constants

- Parameters define constants within a module.
- Declared using the `parameter` keyword.

Key advantages:
- Enable configurable and reusable designs.
- Can be overridden during module instantiation.

### Local Parameters
- Declared using `localparam`.
- Cannot be modified externally.
- Useful for defining fixed internal constants such as state encodings.

---

## 11. Strings in Registers

- Strings can be stored in register variables.
- Each character occupies 8 bits.
- If the register is wider than the string, unused bits are zero-filled.
- If narrower, the string is truncated.

Special characters such as newline and tab are supported using escape sequences.

---

## 12. System Tasks

System tasks are built-in functions used for simulation control and debugging. They are identified by a `$` prefix.

### Displaying Information
- `$display` prints values, variables, or expressions.
- Supports formatted output similar to C's `printf`.
- Automatically appends a newline.

### Monitoring Signals
- `$monitor` continuously tracks specified signals.
- Outputs values whenever any monitored signal changes.
- Only one active monitor is allowed at a time.

### Simulation Control
- `$stop` pauses simulation for debugging.
- `$finish` terminates simulation execution.

---

## 13. Compiler Directives

Compiler directives control preprocessing behavior and are identified by a backtick (`).

### `define`
- Used to create macros or constants.
- Improves readability and maintainability.

### `include`
- Used to include contents of another file.
- Commonly used for header files and shared definitions.

---