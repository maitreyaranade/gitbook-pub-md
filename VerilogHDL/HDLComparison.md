# Hardware Description Language

---

# Table of Contents

## [HDL Basics](basics.md)
## [Verilog](verilog.md)
## [SystemVerilog](systemverilog.md)
## [VHDL](vhdl.md)
## [Verilog Codes](verilogCodes.md)

---

# Verilog vs VHDL

| VHDL                                     | Verilog                                 |
|------------------------------------------|-----------------------------------------|
| Strongly typed                           | Weakly typed                            |
| Easier to understand                     | Less code to write                      |
| More natural in use                      | More of a hardware modeling language    |
| Wordy                                    | Concise                                 |
| Non-C-like syntax                        | Similarities to the C language          |
| Variables must be described by data type | A lower level of programming constructs |
| Widely used for FPGAs and military       | A better grasp on hardware modeling     |
| More difficult to learn                  | Simpler to learn                        |
| Complex data tyepes                      | Simpler data tyepes                     |


---

# Verilog vs SystemVerilog

System Verilog and verilog both Both are IEEE standards, Verilog is IEEE
1364 -2005 (Latest Version)and System verilog is IEEE 1800 - 2017( Latest version). Verilog is a Hardware Description Language , whereas System verilog is a combination of Hardware Description Language (HDL) and Hardware Verification Language (HVL). So, System verilog can be considered as an extension or a superset of Verilog.

- **History** Verilog, is the popular Hardware Description Language invented in early 1980's. Whereas, System Verilog started initially with a name, as Superlog in 2002 and was standardized in 2005 with its own name.\ System verilog for RTL design is an extension of verilog (2005) and has all of its features.System verilog for verification uses Object-oriented programming techniques.

- **Data types** Verilog has majorly two datatypes -- Reg and Wire which are 4 valued logic 0,1,x,z. Whereas, System verilog has logic(inclusive of Wire & Reg), int, shortint, longint, logic, bit, real, realtime, reg, chandle, user defined data type, etc. which are both combination of 4 and 2 valued logic.

- **Memory** Verilog does not allow packed array concept and the lifetime of memories will be static. Whereas, System verilog allows packed array declaration and the lifetime of memories can be dynamic.

- **Procedural Block** Verilog has a general purpose always block to model different types of hardware structures. Whereas, System verilog uses three different procedural blocks namely, always_comb , always_ff and always_latch intended to model specific type of hardware description.

- **Construction** Verilog design is based on hierarchy of modules, where modules encapsulate the design hierarchy, and communicate with other modules through ports. Whereas , System verilog uses Class based design.

- **Interface** Verilog ports (larger designs) for describing a module's connectivity with other module is difficult. Whereas, System verilog uses interface to reduce the redundancy of port declarations between modules.

- **Random** Verilog uses inbuit system functions like $random and $urandom, whereas System Verilog uses a method called Randomize().

- **Constraints** Verilog does not support any control over the variable to be randomized, whereas System verilog uses constraints to have a control of what is being randomized.

- **TB Environment** Verilog does not support for having reusable testbenches and so for complex designs verification will be a milestone whereas, System verilog supports for having reusable testbenches.

- **Synchronisation** SystemVerilog uses interface construct which has used for bunching of all the signals along with clocking block which is used for synchronisation unlike Verilog in which instantiation with the DUT becomes tedious because of large number of signals.

---

# VHDL


# Introduction
VHDL is a Department of Defense–mandated hardware description language. (The V in VHDL stands for the first letter in VHSIC, an acronym for very high-speed integrated circuit.)
- VHDL can model the behavior and structure of digital system at multiple abstraction levels.
- VHDL is strongly typed and very deterministic.
