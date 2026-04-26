# Verilog Codes




D-Latch

```verilog
always @ (enable, D)
  if (enable) Q <= D;
``` 

D flip-flop without reset

```verilog
always @ (posedge Clk)
  Q <= D;
``` 

D flip-flop with asynchronous reset

```verilog
always @ ( posedge Clk, negedge rst)
  if (!rst) Q <= 1'b0; 
  else Q <= D;
``` 

T flip-flop from D flip-flop and gates

```verilog
assign DT = Q ^ T ; // Continuous assignment
DFF (Q, DT, Clk, rst); // Instantiate the D flip-flop
```
JK flip-flop from D flip-flop and gates 

```verilog
assign JK = (J & ~Q) | (~K & Q);
DFF JK1 (Q, JK, Clk, rst); // Instantiate D flip-flop
```

Functional description of JK flip-flop 

```verilog
assign Q_b = ~ Q ;
always @ ( posedge Clk)
case ({J,K})
2'b00: Q <= Q;
2'b01: Q <= 1'b0;
2'b10: Q <= 1'b1;
2'b11: Q <= !Q;
endcase
```



# Verilog Code structure

Sample code to explain verilog code structure:

```verilog
`timescale 1 ns / 10 ps
// timescale directive tells the simulator the base units and precision of the simulation 

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
  ....
  .pinn (netn) 
); 

// synchronous procedures 
always @ (posedge clock) 
begin 
....
end 

// combinatinal procedures 
always @ (signal1 or signal2 or signal3) 
begin 
....
end 

assign net variable = combinational logic; 

endmodule 
```
---