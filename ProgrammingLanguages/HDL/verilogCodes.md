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