# Gate-Level Modeling in Verilog

## 1. Overview of Gate-Level Modeling

Gate-level modeling describes digital circuits using logic gates such as AND, OR, and NOT. It operates at a lower level of abstraction than RTL and provides a direct correspondence between circuit diagrams and Verilog code.

This modeling style is intuitive for designers familiar with digital logic because each Verilog construct maps closely to physical hardware components. While switch-level modeling is even lower, it is rarely used due to complexity.

---

## 2. Gate Primitives in Verilog

Verilog provides predefined gate primitives that can be instantiated directly without defining modules.

### Categories of Gates

#### And/Or Type Gates
- These gates have one output and one or more inputs.
- The first terminal in the instantiation is always the output, followed by inputs.
- Output updates whenever any input changes.

Supported gates include:
- `and`, `or`, `xor`
- `nand`, `nor`, `xnor`

These gates can accept multiple inputs, and their outputs are computed by applying logic iteratively across all inputs.

![Logic Gates](images/LogicGates.png)

#### Buf/Not Type Gates
- These gates have one input and one or more outputs.
- The last terminal represents the input, while preceding terminals are outputs.

Supported gates include:
- `buf`, which passes the input unchanged.
- `not`, which inverts the input.

#### Controlled Gates (Bufif/Notif)
- These gates include an additional control signal.
- They drive the output only when the control signal is active.
- When inactive, the output is high impedance (`z`).

Supported gates include:
- `bufif1`, `bufif0`
- `notif1`, `notif0`

These gates are useful in designs where multiple drivers share a common signal line.

---

## 3. Gate Instantiation

- Gate primitives are instantiated similarly to modules.
- Instance names are optional for primitives, allowing concise descriptions.
- Multiple inputs or outputs can be specified directly in the instantiation.

Example concepts:
- Gates can be used to directly translate logic diagrams into Verilog.
- No separate module definition is required for primitive gates.

```verilog
wire OUT, IN1, IN2;

// basic gate instantiations.
and a1(OUT, IN1, IN2);
nand na1(OUT, IN1, IN2);
or or1(OUT, IN1, IN2);
nor nor1(OUT, IN1, IN2);
xor x1(OUT, IN1, IN2);
xnor nx1(OUT, IN1, IN2);
buf b1(OUT1, IN);
not n1(OUT1, IN);
bufif1 b1 (out, in, ctrl);
bufif0 b0 (out, in, ctrl);
notif1 n1 (out, in, ctrl);
notif0 n0 (out, in, ctrl);

// More than two inputs; 3 input nand gate
nand na1_3inp(OUT, IN1, IN2, IN3);
buf b1_2out(OUT1, OUT2, IN);

// gate instantiation without instance name
and (OUT, IN1, IN2); // legal gate instantiation
not (OUT1, IN); // legal gate instantiation
```

---

## 4. Arrays of Gate Instances

Verilog allows creation of arrays of gate instances to simplify repetitive designs.

```verilog
wire [3:0] OUT, IN1, IN2;

// basic gate instantiations.
nand n_gate[3:0](OUT, IN1, IN2);

// This is equivalent to the following 4 instantiations
nand n_gate0(OUT[0], IN1[0], IN2[0]);
nand n_gate1(OUT[1], IN1[1], IN2[1]);
nand n_gate2(OUT[2], IN1[2], IN2[2]);
nand n_gate3(OUT[3], IN1[3], IN2[3]);
```

- This is useful when performing identical operations across vectors.
- Each instance operates on corresponding bits of input and output vectors.

This approach significantly reduces code duplication and improves readability.

---

## 5. Gate Delays

Real hardware exhibits propagation delays, which can be modeled in Verilog.

### Types of Delays

#### Rise Delay
- Represents the time taken for output to transition to logic 1.

#### Fall Delay
- Represents the time taken for output to transition to logic 0.

#### Turn-Off Delay
- Represents the time taken for output to transition to high impedance (`z`).

If the output transitions to an unknown value (`x`), the minimum of the specified delays is used.

---

## 6. Delay Specification

Verilog allows different levels of delay specification:

- A single delay value applies to all transitions.
- Two delay values specify rise and fall delays.
- Three delay values specify rise, fall, and turn-off delays explicitly.
- If no delay is specified, the default is zero.

This flexibility allows designers to model timing behavior with varying levels of detail.

---

## 7. Min, Typical, and Max Delays

Each delay type (rise, fall, turn-off) can include three values:

- Minimum delay represents the best-case scenario.
- Typical delay represents nominal behavior.
- Maximum delay represents worst-case conditions.

### Usage
- One of these values is selected during simulation.
- Selection is typically controlled via simulator options.

This feature allows designers to analyze circuit behavior under different process variations without modifying the design.
```verilog
// Delay of delay_time for all transitions
and #(delay_time) a1(out, i1, i2);

// Rise and Fall Delay Specification.
and #(rise_val, fall_val) a2(out, i1, i2);

// Rise, Fall, and Turn-off Delay Specification
and #(rise_val, fall_val, turnoff_val) a3(out, i1, i2);

// Three delays - min max & typical
// if +mindelays, rise= 2 fall= 3 turn-off = 4
// if +typdelays, rise= 3 fall= 4 turn-off = 5
// if +maxdelays, rise= 4 fall= 5 turn-off = 6
and #(2:3:4, 3:4:5, 4:5:6) a3(out, i1,i2);


```
---

## 8. Timing Behavior and Simulation

- Gate delays affect the timing of signal transitions in simulation.
- Outputs do not change immediately but follow specified delays.
- Intermediate signals also exhibit delays, impacting overall circuit timing.

Example insight:
- A change in input propagates through gates sequentially, each adding its delay.
- This results in observable timing differences between signals in waveforms.

---