


Zynq Documentation\


# Zynq ultrascale+ MPsoc Architecture Overview

## Introduction to UltraScale Architecture

The Xilinx UltraScale architecture is the first ASIC-class architecture
to enable multi-hundred gigabit-per-second levels of system performance
with smart processing, while efficiently routing and processing data
on-chip. UltraScale architecture-based devices address a vast spectrum
of high-bandwidth, high-utilization system requirements by using
industry-leading technical innovations, including next-generation
routing, ASIC-like clocking, 3D-on-3D ICs, multiprocessor SoC (MPSoC)
technologies, and new power reduction features. The devices share many
building blocks, providing scalability across process nodes and product
families to leverage system-level investment across platforms.

Virtex UltraScale+ devices provide the highest performance and
integration capabilities in a FinFET node, including both the highest
serial I/O and signal processing bandwidth, as well as the highest
on-chip memory density. As the industry's most capable FPGA family, the
Virtex UltraScale+ devices are ideal for applications including 1+Tb/s
networking and data center and fully integrated radar/early-warning
systems.

Virtex UltraScale devices provide the greatest performance and
integration at 20 nm, including serial I/O bandwidth and logic capacity.
As the industry's only high-end FPGA at the 20 nm process node, this
family is ideal for applications including 400G networking, large scale
ASIC prototyping, and emulation.

Kintex UltraScale+ devices provide the best price/performance/watt
balance in a FinFET node, delivering the most cost-effective solution
for high-end capabilities, including transceiver and memory interface
line rates as well as 100G connectivity cores. Our newest mid-range
family is ideal for both packet processing and DSP-intensive functions
and is well suited for applications including wireless MIMO technology,
Nx100G networking, and data center.

Kintex UltraScale devices provide the best price/performance/watt at 20
nm and include the highest signal processing bandwidth in a mid-range
device, next-generation cost-effectiveness. The family is ideal for
packet processing in 100G networking and data centers applications as
well as DSP-intensive processing needed in next-generation medical
imaging, 8k4k video, and heterogeneous wireless infrastructure.

Artix UltraScale+ devices provide high serial bandwidth and signal
compute density in a cost-optimized device for critical networking
applications, vision and video processing, and secured connectivity.
Coupled with the innovative InFO packaging, which provides excellent
thermal and power distribution, Artix UltraScale+ devices are perfectly
suited to applications requiring high compute density in a small
footprint.

Zynq UltraScale+ devices provide 64-bit processor scalability while
combining real-time control with soft and hard engines for graphics,
video, waveform, and packet processing. Integrating an Arm-based system
for advanced analytics and on-chip programmable logic for task
acceleration creates unlimited possibilities for applications including
5G Wireless, next generation ADAS, and industrial Internet-of-Things.

# Zynq ultrascale+ MPsoc Configurable logic blocks

# Zynq ultrascale+ MPsoc Clocking Resources

## Clocking Resource Abbreviations

-   CMT: clock management tile

-   CR: clock region

-   CLB: Configurable logic blocks

-   HCS: Horizontal Clock Spine

-   GT: gigabit transceiver

-   SYSMON: System Monitor

-   MMCM: mixed-mode clock manager

-   PLL: phase-locked loop

## Clocking Architecture Overview

The UltraScale architecture clocking resources manage complex and simple
clocking requirements with dedicated global clocks distributed on clock
routing and clock distribution resources. The clock management tiles
(CMTs) provide clock frequency synthesis, deskew, and jitter filtering
functionality.

-   The device is subdivided into columns and rows of segmented clock
    regions (CRs) which are arranged in tiles. A CR contains
    configurable logic blocks (CLBs), DSP slices, block RAMs,
    interconnect, and associated clocking. The height of a CR is 60
    CLBs, 24 DSP slices, and 12 block RAMs with a Horizontal Clock Spine
    (HCS) at its center. The HCS contains the horizontal routing and
    distribution resources, leaf clock buffers, clock network
    interconnections, and the root of the clock network. Clock buffers
    drive directly into the HCS. There are 52 I/Os per bank and four
    gigabit transceivers (GTs) that are pitch matched to the CRs. A core
    column contains configuration, System Monitor (SYSMON), and PCIe
    blocks to complete a basic device.

-   Adjacent to the input/output block columns are the physical layer
    (PHY) blocks with CMTs, global clock buffers, global clock
    multiplexing structures, and I/O logic management functions. The
    clocking drives vertical and horizontal connectivity through
    separate clock routing and clock distribution resources via HCS into
    the CRs and I/Os.

-   Horizontal clock routing and distribution tracks drive horizontally
    into the CRs. Vertical routing and distribution tracks drive
    vertically adjacent CRs. The tracks are segmentable at the CR
    boundaries in both the horizontal and vertical directions. This
    allows for the creation of device-wide global clocks or local clocks
    of variable size.

-   The distribution tracks drive the clocking of synchronous elements
    across the device. Distribution tracks are driven by routing tracks
    or directly by the clocking structures in the PHY.

-   I/Os are directly driven from the PHY clocking and/or an adjacent
    PHY via routing tracks.

-   A CMT contains one mixed-mode clock manager (MMCM) and two
    phase-locked loops (PLLs).

## Clocking Resources

### Overview

UltraScale architecture-based devices have several clock routing
resources to support various clocking schemes and requirements,
including high fanout, short propagation delay, and extremely low skew.
To best utilize the clock routing resources, the designer must
understand how to get user clocks from the PCB to the UltraScale
devices, decide which clock routing resources are optimal, and then
access those clock routing resources by utilizing the appropriate I/O
and clock buffers.

### Clock Routing Resources Overview

Each I/O bank contains global clock input pins to bring user clocks onto
the device clock management and routing resources. The global clock
inputs bring user clocks onto:

-   Clock buffers in the PHY adjacent to the same bank

-   CMTs in the PHY adjacent to the same bank

### Clock Buffers

Each device has three global clock buffers: BUFGCTRL, BUFGCE, and
BUFGCE_DIV. In addition, there is a local BUFCE_LEAF clock buffer for
driving leaf clocks from horizontal distribution to various blocks in
the device. BUFGCTRL has derivative software representations of types
BUFGMUX, BUFGMUX1, BUFGMUX_CTRL, and BUFGCE_1. BUFGCE is for glitchless
clock gating and has software derivative BUFG (BUFGCE with clock enable
tied High). The global clock buffers drive routing and distribution
tracks into the device logic via HCS rows. There are 24 routing and 24
distribution tracks in each HCS row. There is also a BUFG_GT that
generates divided clocks for GT clocking. The clock buffers:

-   Can be used as a clock enable circuit to enable or disable clocks
    either globally, locally, or within a CR for fine-grained power
    control.

-   Can be used as a glitch-free multiplexer to:

    -   select between two clock sources.

    -   switch away from a failed clock source.

-   Are often driven by a CMT to:

    -   eliminate the clock distribution delay.

    -   adjust clock delay relative to another clock.

### Global Clock Inputs

External global user clocks must be brought into the UltraScale device
on differential clock pin pairs called global clock (GC) inputs. There
are four GC pin pairs in each bank that have direct access to the global
clock buffers, MMCMs, and PLLs that are in the CMT adjacent to the same
I/O bank.

GC inputs provide dedicated, high-speed access to the internal global
and regional clock resources. GC inputs use dedicated routing and must
be used for clock inputs where the timing of various clocking features
is imperative. General-purpose I/O with local interconnects should not
be used for clock signals.

Each I/O bank is located in a single clock region and includes 52 I/O
pins. Of the 52 I/O pins in each I/O bank in every I/O column, there are
four global clock input pin pairs (a total of eight pins). Each global
clock input:

-   Can be connected to a differential or single-ended clock on the PCB.

-   Can be configured for any I/O standard, including differential I/O
    standards.

-   Has a P-side (master), and an N-side (slave).

Single-ended clock inputs must be assigned to the P (master) side of the
GC input pin pair. If a single-ended clock is connected to the P-side of
a differential clock pin pair, the N-side cannot be used as another
single-ended clock pin---it can only be used as a user I/O.

GC inputs can be used as regular I/O if not used as clocks. When used as
regular I/O, global clock input pins can be configured as any
single-ended or differential I/O standard. GC inputs can connect to the
PHY adjacent to the banks they reside in.

### Byte Clock Inputs

Byte-lane clock (DBC and QBC) input pin pairs are dedicated clock inputs
directly driving source synchronous clocks to the bit slices in the I/O
banks. In memory applications, these are also known as DQS. When not
used for I/O byte clocking these pin have other functions such as
general purpose I/Os.

### Clock Buffers and Clock Routing

Global clocks are a dedicated network of interconnects specifically
designed to reach all clock inputs to the various resources in a device.
These networks are designed to have low skew and low duty cycle
distortion, low power, and improved jitter tolerance. They are also
designed to support very high-frequency signals.\
Understanding the signal path for a global clock expands the
understanding of the various global clocking resources. The global
clocking resources and network consist of these paths and components.

-   Clock Structure

-   Clock Buffers

-   BUFGCTRL: Clock Buffer Primitives

-   BUFGCE Clock Buffers

-   BUFG Clock Buffer

-   BUFCE_LEAF Clock Buffer

### Clock Structure

The basic device architecture is composed of blocks of Clock Regions
(CRs). CRs are organized into tiles and thus build columns and rows.
Each CR contains slices (CLBs), DSPs, and 36K block RAM blocks.

The mix of slice, DSP, and block RAM columns in each CR can be
different, but are always identical when stacked in the vertical
direction, thus building columns of those resources for the entire
device. I/O and GT columns are then inserted with columns of CRs. In
addition, there is a single column that contains the configuration
logic, SYSMON, and PCIe blocks. An HCS runs horizontally through the
device in the center of each row of CRs, I/Os, and GTs. The HCS contains
the horizontal routing and distribution tracks as well as leaf clock
buffers and clock network interconnects between horizontal/vertical
routing and distribution. Vertical tracks of routing and distribution
connect all CRs in a column, while vertical routing spans an entire I/O
column. There are 24 horizontal routing and 24 distribution tracks , and
24 vertical routing and 24 distribution tracks . The purpose of the
clock routing resources is to route a clock from the global clock
buffers to a central point from where it is connected to the loads via
the distribution resources. This central point of the clock network is
called a clock root in the UltraScale architecture. The root can be in
any CR in a device from where it is routed to the loads via the clock
distribution resources. This architecture optimized clock skew. Routing
and distribution resources can either connect to adjacent CRs or
disconnect (isolated) at the border of the CR as needed. This concept
extends to SSI devices as well.


![Horizontal Clocking](images/HorizClock.png){#HorizClock width="70%"}



![Vertical Clocking](images/VertClock.png){#VertClock width="70%"}


The clocks can be distributed from their sources in one of two ways:

-   The clocks can go onto routing tracks that take the clocks to a
    central point in a CR without going to any loads. The clocks can
    then drive the distribution tracks unidirectionally from which the
    clock networks fan out. In this way, the clock buffers can drive to
    a specific point in the CRs from which the clock buffers travel
    vertically and then horizontally on the distribution tracks to drive
    the clocking points. The clocking points are driven via leaf clocks
    with clock enable (CE) in that CR and adjacent CRs, if needed.
    Distribution tracks cannot drive routing tracks. This distribution
    scheme is used to move the root for all the loads to be at a
    specific location for improved, localized skew. Furthermore, both
    routing and distribution tracks can drive into horizontally or
    vertically adjacent CRs in a segmented fashion. Routing tracks can
    drive both routing and distribution tracks in the adjacent CRs while
    the distribution tracks can drive other horizontal distribution
    tracks in adjacent CRs. The CR boundary segmentation allows
    construction of either truly global, device-wide clock networks or
    more local clock networks of variable sizes by reusing clocking
    tracks.

-   Alternatively, clock buffers can drive straight onto the
    distribution tracks and distribute the clock in that manner. This
    reduces the clock insertion delay.


![Clock Distribution](images/clockDistr.png){#clockDistr width="70%"}


### Clock Buffers

The PHY global clocking contains several sets of BUFGCTRLs, BUFGCEs, and
BUFGCE_DIVs. Each set can be driven by four GC pins from the adjacent
bank, MMCMs, PLLs in the same PHY, and interconnect. The clock buffers
then drive the routing and distribution resources across the entire
device. Each PHY contains 24 BUFGCEs, 8 BUFGCTRLs, and 4 BUFGCE_DIVs but
only 24 of them can be used at the same time.

#### BUFGCTRL

The BUFGCTRL Clock Buffer Primitives are designed to switch between two
clock inputs without the possibility of a glitch.


![BUFGCTRL Clock Buffer Primitive](images/BUFGCTRL.png){#BUFGCTRL
width="70%"}


All other global clock buffer primitives are derived from certain
configurations of BUFGCTRL. Pins of the types of BUFGCTRL Clock Buffers:

-   BUFGCTRL I0, I1 O CE0, CE1, IGNORE0, IGNORE1, S0, S1

-   BUFGCE_1 I O CE

-   BUFGMUX I0, I1 O S

-   BUFGMUX_1 I0, I1 O S

-   BUFGMUX_CTRL I0, I1 O S

BUFGCTRL has four select lines, S0, S1, CE0, and CE1. It also has two
additional control lines, IGNORE0 and IGNORE1. These six control lines
are used to control the inputs I0 and I1.

When the presently selected clock transitions from High to Low after S0
and S1 change, the output is kept Low until the other (to-be-selected)
clock transitions from High to Low. Then, the new clock starts driving
the output.

##### BUFGCE_1

BUFGCE_1 is a clock buffer with one clock input, one clock output, and a
clock enable line. This primitive is based on BUFGCTRL with some pins
connected to logic High or Low.

The switching condition for BUFGCE_1 is similar to BUFGCTRL with
INIT_OUT set to 1. If the CE input is Low prior to the incoming falling
clock edge, the following clock pulse does not pass through the clock
buffer, and the output stays High. Any level change of CE during the
incoming clock Low pulse has no effect until the clock transitions High.
The output stays High when the clock is disabled. However, when the
clock is being disabled, it completes the clock Low pulse.

##### BUFGMUX and BUFGMUX_1

BUFGMUX is a clock buffer with two clock inputs, one clock output, and a
select line (made by shorting CE0 & CE1 lines). This primitive is based
on BUFGCTRL with some pins connected to logic High or Low.

##### BUFGMUX_CTRL

BUFGMUX_CTRL is a clock buffer with two clock inputs, one clock output,
and a select line (made by shorting S0 & S1 lines). This primitive is
based on BUFGCTRL with some pins connected to logic High or Low.
BUFGMUX_CTRL uses the S pins as select pins. S can switch anytime
without causing a glitch. The setup/hold time on S is for determining
whether the output passes an extra pulse of the previously selected
clock before switching to the new clock. If S changes prior to the setup
time TBCCCK_S and before I0 transitions from High to Low, the output
does not pass an extra pulse of I0. If S changes following the hold time
for S, the output passes an extra pulse. If S violates the setup/hold
requirements, the output might pass the extra pulse but it will not
glitch. In any case, the output changes to the new clock within three
clock cycles of the slower clock.

#### BUFGCE

BUFGCE is a clock buffer with one clock input, one clock output, and a
clock enable line. This buffer provides glitch-less clock gating. BUFGCE
can directly drive the routing resources and is a clock buffer with a
single gated input. Its output becomes 0 when CE goes Low (inactive).
When CE goes High, the input is transferred to the output.

BUFGCE Pins:

-   CE: (Input) Clock enable

-   I: (Input) Clock buffer

-   O: (Output) Clock buffer

#### BUFG

BUFG is a clock buffer with one clock input and one clock output. This
primitive is based on BUFGCE with the CE pin connected to High.

#### BUFCE_LEAF

BUFCE_LEAF is a clock buffer with CE for leaf driving off horizontal HCS
row. This buffer is an interconnect leaf clock buffer driving the
clocking point of the various blocks with a single gated input. Its O
output is 0 when CE is Low (inactive). When CE is High, the I input is
transferred to the O output.

#### BUFGCE_DIV

BUFGCE_DIV is a clock buffer with one clock input (I), one clock output
(O), one clear input (CLR) and a clock enable (CE) input. BUFGCE_DIV can
directly drive the routing and distribution resources and is a clock
buffer with a single gated input and a reset.

Its output is 0 when CLR is High (active). When CE is High, the input is
transferred to the output. CE is synchronous to the clock for
glitch-free operation. CLR is an asynchronous reset assertion and
synchronous reset deassertion to this buffer.

BUFGCE_DIV Pins:

-   CE: (Input) Clock enable

-   I: (Input) Clock buffer

-   O: (Output) Clock buffer

-   R: (Input) Reset

#### BUFG_GT and BUFG_GT_SYNC

The BUFG_GTs are driven by the gigabit transceivers (GTs) and the
ADC/DAC blocks in the RFSoC devices. BUFG_GTs provide the only means for
those blocks to drive the clock routing resources. Only GTs, ADCs, and
DACs can drive BUFG_GTs. BUFG_GT is a clock buffer with one clock input
(I), one clock output (O), one clear input (CLR) with CLR mask input
(CLRMASK), a clock enable (CE) input with a CE mask input (CEMASK) and a
3-bit divide (DIV\[2:0\]) input.

BUFG_GT_SYNC is the synchronizer circuit for the BUFG_GTs. The
BUFG_GT_SYNC primitive is automatically inserted by the Vivado tools, if
not present in the design. This buffer can directly drive the routing
and distribution resources and is a clock buffer with a single gated
input and a reset.

When CE is deasserted (Low) the output stops at its current state, High
or Low. When CE is High, the I input is transferred to the O output.
Both edges of CE and the deassertion of CLR are automatically
synchronized to the clock for glitch-free operation. The Vivado tools do
not support timing for the CE pin, therefore, a deterministic latency
cannot be achieved. CLR is an asynchronous reset assertion and
synchronous reset deassertion to the BUFG_GTs.

#### BUFG_PS

The BUFG_PS is a simple clock buffer with one clock input (I), one clock
output (O). This clock buffer is a resource for the Zynq UltraScale+
MPSoC processor system (PS) and provides access to the programmable
logic (PL) clock routing resources for clocks from the processor into
the PL. Up to 18 PS clocks can drive the BUFG_PS. This clock buffer
resides next to the PS.

## Clock Management Tile (CMT)

### Overview

In UltraScale architecture-based devices, each device has a CMT as part
of the PHY next to each of the I/O banks. The clock management tile
(CMT) includes a mixed-mode clock manager (MMCM) and two phase-locked
loops (PLLs).

The MMCM is the primary block for frequency synthesis for a wide range
of frequencies, and serves as a jitter filter for either external or
internal clocks, and deskew clocks among a wide range of other
functions.

The main purpose of the PLL is to generate clocking for the I/Os. But it
also contains a limited subset of the MMCM functions that can be used
for general clocking purposes. The clock input connectivity allows
multiple resources to provide the reference clock(s) to the MMCM.

MMCMs have infinite fine phase shift capability in either direction and
can be used in dynamic phase shift mode. The resolution of the fine
phase shift depends on the voltage-controlled oscillator (VCO)
frequency.

### MMCMs

The MMCMs serve as frequency synthesizers for a wide range of
frequencies, and as jitter filters for either external or internal
clocks, and deskew clocks. Input multiplexers select the reference and
feedback clocks from either the global clock I/Os or the clock routing
or distribution resources. Each clock input has a programmable counter
divider (D). The phase-frequency detector (PFD) compares both phase and
frequency of the rising edges of both the input (reference) clock and
the feedback clock. If a minimum High/Low pulse is maintained, the duty
cycle is ancillary. The PFD is used to generate a signal proportional to
the phase and frequency between the two clocks. This the VCO. The PFD
produces an up or down signal to the charge pump and loop filter to
determine whether the VCO should operate at a higher or lower frequency.


![MMCM Block Diagram](images/MMCM.png){#MMCM width="\\textwidth"}


#### MMCM Primitives

The UltraScale device MMCM primitives, MMCME3_BASE and MMCME3_ADV. The
UltraScale+ devices have the same primitives with an E4 instead of an
E3.

### PLLs

There are two PLLs per CMT that provide clocking to the PHY logic and
I/Os. In addition, they can be used as frequency synthesizers for a wide
range of frequencies, serve as jitter filters, and provide basic phase
shift capabilities and duty cycle programming. The PLLs differ from the
MMCM in number of outputs, cannot deskew clock nets, and do not have
advanced phase shift capabilities, Multipliers and input dividers have a
smaller value range and do not have many of the other advanced features
of the MMCM.

#### PLL Primitives

The UltraScale device contain PLL primitives PLLE3_BASE and PLLE3_ADV.
For UltraScale+ devices have the same primitives with an E4 instead of
an E3.

### Dynamic Reconfiguration Port

### VHDL and Verilog Templates and the Clocking Wizard

### Clocking Guidelines

## Question & Answers

 itemize


# Zynq ultrascale+ MPsoc Memory Resources
