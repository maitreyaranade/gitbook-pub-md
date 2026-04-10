
## FPGA generic design flow

FPGA generic design flow is shown in the .


![FPGA generic design flow](images/GenFlow.png)


### Design Entry

Creating design Schematic / HDL Code

### Design Implementation

Partitioning Placing Routing

### Design Verification

Simulation for checking functionality Debugging on the hardware: Logic
Analyser

FPGA development process as shown in the is usually divided in two
parts: implementation and verification.

-   **Implementation** is the process of moving forward from your
    abstract design all the way to the final application. This is done
    by a tool chain of programs that perform a number of steps just like
    a compiler does.

-   **Verification** which is the necessary process of testing the
    design in every step of the implementation. And this is, as you may
    imagine, an iterative process.


![FPGA development process](images/FPGADevelop.png)


These are the steps involved in the implementation process. The first
step is to write the source code which is a description of the hardware
under development. There are several levels of abstraction to write this
code. For example, your code can specify the connections in your system
or the behavior of your system. This code is written in a hardware
description language. The two most popular of which are VHDL and
Verilog. Once the code is written, it goes through logic synthesis. A
process very similar to software compiling. In fact, this whole process
is sometimes called compiling. Logic synthesis consists in converting
the source code into a net list that is a logic representation of the
connections in the design under development. By this stage, not all HDL
code is synthesizable. There are limitations in the FPGA's architecture
that require your code to comply with some rules. A special level of
abstraction known as the register transfer level or RTL is regarded as
synthesizable most of the time. So it's very common to refer to the
source code as RTL code. Once your design is understood by the tool
chain, you get to specify the constraints of the final operational
system. These are the requirements that you want the system to meet. The
most important of these are timing constraints. You have to specify how
fast you need your system to operate. When you inform the tool chain
about your timing requirements, it can use these hints to choose a
combination of connections that will produce the best system possible.
Other aspects specified as user constraints are pin assignments, the
area you want your design to occupy inside the chip, and the logic level
voltages in the pins. Next the design goes through a process called
place and route. This is where the net lists are translated into devices
and connections, and these in turn are assigned to specific parts of the
FPGA in what is known as a floor plan. Cells are assigned to logic
elements, and the interconnects are routed. Finally you get to generate
the programming file. The output of this stage is a binary file
sometimes called a bit stream. The target may be an FPGA or some other
memory. In fact, more often than not, FPGAs implement their internal
configuration memory as volatile RAM. So there's usually an on board
non-volatile memory with a boot up procedure that loads its content into
the FPGAs configuration RAM. This whole process is prone to errors and
bugs. So that's why the verification process is so important. There's at
least one way to verify and validate your design at each step of the
implementation. At the source code stage, you get to perform a
behavioral simulation which reveals how the system behaves logically.
After synthesis, a functional simulation can be performed which uses the
newly produced gate level model. Once the timing constraints have been
considered by the tool chain, a timing analysis can be performed to
predict if there's any risk that your system will not meet these
requirements, and the final application hardware can be put to the test
with the help of in-circuit verification tools often provided by the
FPGA vendor.


![Xilinx Vivado Workflow](images/FPGADesignFlow.png)


The individual blocks Xilinx Vivado Workflow are explained below:

## RTL Design

You can specify RTL source files to create a project and use these
sources for RTL code development, analysis, synthesis and
implementation. Xilinx supplies a library of recommended RTL and
constraint templates to ensure RTL and XDC are formed optimally for use
with the Vivado Design Suite. Vivado synthesis and implementation
support multiple source file types, including Verilog, VHDL,
SystemVerilog, and XDC.

## IP Design and System-Level Design Integration

The Vivado Design Suite provides an environment to configure, implement,
verify, and integrate IP as a standalone module or within the context of
the system-level design. IP can include logic, embedded processors,
digital signal processing (DSP) modules, or C-based DSP algorithm
designs. Custom IP is packaged following IP-XACT protocol and then made
available through the Vivado IP catalog. The IP catalog provides quick
access to the IP for configuration, instantiation, and validation of IP.
Xilinx IP utilizes the AXI4 interconnect standard to enable faster
system-level integration. Existing IP can be used in the design either
in RTL or netlist format.

## IP Subsystem Design

The Vivado IP Integrator environment enables you to stitch together
various IP into IP subsystems using the AMBA AXI4 interconnect protocol.
You can interactively configure and connect IP using a block design
style interface and easily connect entire interfaces by drawing
DRC-correct connections similar to a schematic. Connecting the IP using
standard interfaces saves time over traditional RTL-based connectivity.
Connection automation is provided as well as a set of DRCs to ensure
proper IP configuration and connectivity. These IP block designs are
then validated, packaged, and treated as a single design source. Block
designs can be used in a design project or shared among other projects.
The IP Integrator environment is the main interface for embedded design
and the Xilinx evaluation board interface.

## I/O and Clock Planning

The Vivado IDE provides an I/O pin planning environment that enables I/O
port assignment either onto specific device package pins or onto
internal die pads, and provides tables to let you design and analyze
package and I/O-related data. Memory interfaces can be assigned
interactively into specific I/O banks for optimal data flow. You can
analyze the device and design-related I/O data using the views and
tables available in the Vivado pin planner. The tool also provides I/O
DRC and simultaneous switching noise (SSN) analysis commands to validate
your I/O assignments.

## Xilinx Platform Board Support

In the Vivado Design Suite, you can select an existing Xilinx evaluation
platform board as a target for your design. In the platform board flow,
all of the IP interfaces implemented on the target board are exposed to
enable quick selection and configuration of the IP used in your design.
The resulting IP configuration parameters and physical board
constraints, such as I/O standard and package pin constraints, are
automatically assigned and proliferated throughout the flow. Connection
automation enables quick connections to the selected IP.

### Board Files

## Synthesis

Vivado synthesis performs a global, or top-down synthesis of the overall
RTL design. However, by default, the Vivado Design Suite uses an
out-of-context (OOC), or bottom-up design flow to synthesize IP cores
from the Xilinx IP Catalog and block designs from the Vivado IP
integrator. You can also choose to synthesize specific modules of a
hierarchical RTL design as OOC modules. This OOC flow lets you
synthesize, implement, and analyze design modules of a hierarchical
design, IP cores, or block designs, out of the context of, or
independent from the top-level design. The OOC synthesized netlist is
stored and used during top-level implementation to preserve results and
reduce runtime. The OOC flow is an efficient technique for supporting
hierarchical team design, synthesizing and implementing IP and IP
subsystems, and managing modules of large complex designs.

The Vivado Design Suite also supports the use of third-party synthesized
netlists, including EDIF or structural Verilog. However, IP cores from
the Vivado IP Catalog must be synthesized using Vivado synthesis, and
are not supported for synthesis with a third-party synthesis tool.

Synthesis derives an optimized list of physical components and their
interconnections called a netlist from the model of a digital system
described in an HDL. Synthesis produces a database describing the
elements and structure of a circuit. It specifies how to fabricate a
phyical integrated circuit that implements in silicon the functionality
described by design entry.

## Design Analysis and Simulation

The Vivado Design Suite lets you analyze, verify, and modify the design
at each stage of the design process. You can run design rule and design
methodology checks, logic simulation, timing and power analysis to
improve circuit performance. This analysis can be run after RTL
elaboration, synthesis, and implementation.

The Vivado simulator enables you to run behavioral and structural logic
simulation of the design at different stages of the design flow. The
simulator supports Verilog and VHDL mixed-mode simulation, and results
can be displayed in a waveform viewer integrated in the Vivado IDE. You
can also use third-party simulators that can be integrated into and
launched from the Vivado IDE.

### Simulation

Logic debugging on PC before implementation of hardware. Allows line by
line debug. Allows use of external files to simulate circuit. Testbench
is another wrapper which tests the module you want to test (DUT: Device
under test).

Functions only in the simulation(non synthesizable):

-   \$monitor

-   \$display

-   \$stop

-   \$finish

-   \$error

clock generation:

*always begin\
clk \<= 1; #5;\
clk \<= 0; #5;\
end;*

## Placement and Routing

When the synthesized netlist is available, Vivado implementation
provides all the features necessary to optimize, place and route the
netlist onto the available device resources of the target part. Vivado
implementation works to satisfy the logical, physical, and timing
constraints of the design. For challenging designs the Vivado IDE also
provides advanced floorplanning capabilities to help drive improved
implementation results. These include the ability to constrain specific
logic into a particular area, or manually placing specific design
elements and fixing them for subsequent implementation runs.

## Hardware Debug and Validation

After implementation, the device can be programmed and then analyzed
with the Vivado logic analyzer, or within the standalone Vivado Lab
Edition environment. Debug signals can be identified in the RTL design,
or inserted after synthesis and are processed throughout the flow. Debug
cores can be configured and inserted either in RTL, in the synthesized
netlist, or in the implemented design using incremental implementation
techniques. Existing debug probes can be also modified, or internal
signals routed to a package pin for external probing using the ECO flow.

## Generate Bitstream

## Program FPGA

## FAQs
