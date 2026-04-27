# Zynq UltraScale+ MPSoC Clocking Resources

> Reference basis: AMD/Xilinx UltraScale Architecture Clocking Resources (UG572), adapted for Zynq UltraScale+ MPSoC context.

---

# 1. Overview

Zynq UltraScale+ MPSoC devices use the UltraScale clocking architecture, which provides dedicated low-skew, high-performance clock networks for programmable logic (PL), processor-system-to-PL clock transfer, I/O interfaces, transceivers, and timing-critical logic.

The architecture is designed to support:

- Global high-fanout clocks.
- Regional or localized clocks.
- Frequency synthesis.
- Clock gating.
- Clock multiplexing.
- Jitter filtering.
- Phase alignment.
- Low insertion delay.
- Scalable clock distribution across large devices.

Clocking is implemented using dedicated hardware resources rather than ordinary routing, which improves timing quality and predictability.

---

# 2. Important Abbreviations

| Term | Meaning |
|---|---|
| CMT | Clock Management Tile |
| CR | Clock Region |
| CLB | Configurable Logic Block |
| HCS | Horizontal Clock Spine |
| MMCM | Mixed-Mode Clock Manager |
| PLL | Phase-Locked Loop |
| GT | Gigabit Transceiver |
| PHY | Physical Interface Clocking/I/O Area |
| SYSMON | System Monitor |

---

# 3. Clocking Architecture Summary

The device is divided into rows and columns of clock regions. Each region contains logic resources and dedicated clock connectivity.

A clock region typically contains:

- CLBs
- DSP slices
- Block RAM
- Interconnect
- Associated clock resources

At the center of each clock row is the Horizontal Clock Spine (HCS), which acts as the major clock backbone for that row.

The HCS contains:

- Horizontal clock routing tracks
- Horizontal clock distribution tracks
- Leaf clock buffers
- Interconnect points between vertical and horizontal clock networks
- Clock root connectivity

This structure enables clocks to be distributed efficiently across small areas or the full device.

---

# 4. Clock Regions and Segmented Distribution

Clock routing is segmented at clock region boundaries. This is a major UltraScale feature.

### Practical Meaning

A clock can be distributed as:

- Device-wide global clock.
- Local clock spanning a few adjacent regions.
- Mid-size domain covering selected areas.

### Benefit

Designers can reduce:

- Power consumption
- Unnecessary fanout
- Clock skew in localized logic
- Congestion

---

# 5. Horizontal and Vertical Clock Networks

Two major dedicated paths are used.

## Horizontal Paths

Drive clocks across rows through HCS resources.

## Vertical Paths

Drive clocks between adjacent clock regions in columns.

### Typical Use

- Horizontal distribution for row-based logic spread.
- Vertical distribution for stacked modules or memory columns.

Both can be combined to create complete networks.

---

# 6. Clock Roots

A clock root is the central distribution point from which a clock fans out to loads.

Instead of always launching from one corner of the device, UltraScale architecture allows clock roots to be positioned closer to the logic using that clock.

### Benefits

- Lower skew
- Lower insertion delay
- Better timing closure
- More efficient regional clocking

---

# 7. Clock Management Tile (CMT)

Each relevant PHY area contains a Clock Management Tile.

Each CMT includes:

- 1 MMCM
- 2 PLLs

These blocks are the primary programmable clock-generation resources.

### Used For

- Frequency multiplication
- Frequency division
- Duty-cycle shaping
- Jitter cleanup
- Phase shift
- Clock deskew
- Clock generation for interfaces

---

# 8. Global Clock Inputs (GC Pins)

External clocks should enter the device using dedicated GC input pins.

Each I/O bank provides dedicated global clock pin pairs with direct access to:

- Global buffers
- MMCMs
- PLLs
- Dedicated clock routing resources

### Why GC Pins Matter

General-purpose I/O pins are not preferred for clocks because normal routing introduces:

- More skew
- More jitter
- Poor timing predictability

### Best Practice

Use GC pins for oscillators, reference clocks, interface clocks, and timing-critical external clocks.

---

# 9. Differential Clock Inputs

GC inputs are available as differential pairs.

Each pair has:

- P side (master)
- N side (slave)

Single-ended clocks should use the P side.

### Professional Note

Differential clocks are preferred for board-level noise immunity and signal integrity.

---

# 10. Byte Clock Inputs (DBC / QBC)

Dedicated byte-lane clocks are used for source-synchronous interfaces, especially memory interfaces.

Typical usage includes:

- DQS clocks
- Byte-lane capture clocks
- DDR-style interfaces

When unused for byte clocking, these pins may support alternate functions.

---

# 11. Global Clock Buffers Overview

Clock buffers connect clock sources to the internal dedicated clock network.

Main buffer types:

- BUFGCTRL
- BUFGCE
- BUFG
- BUFGCE_DIV
- BUFCE_LEAF
- BUFG_GT
- BUFG_PS

These are essential resources for robust clock tree implementation.

---

# 12. BUFGCTRL

BUFGCTRL is the most flexible global clock buffer.

### Main Features

- Two clock inputs
- One output
- Glitch-free switching between clock sources
- Clock selection logic
- Clock enable control

### Typical Uses

- Primary/backup oscillator switching
- Dynamic source selection
- Safe clock muxing

### Example Use Case

A design may switch from an external oscillator to an MMCM-generated clock without producing glitches.

---

# 13. BUFGCE

BUFGCE is a global clock buffer with clock enable.

### Main Purpose

Glitchless clock gating.

### Behavior

- CE High enables clock.
- CE Low disables output cleanly.

### Common Uses

- Power saving
- Subsystem clock shutdown
- Controlled startup sequencing

---

# 14. BUFG

BUFG is the simpler always-enabled version of BUFGCE.

### Use Case

Use when a clock should always propagate globally.

---

# 15. BUFGCE_DIV

This buffer supports division plus enable/reset control.

### Features

- Input clock
- Divided output clock
- Clock enable
- Reset/Clear

### Typical Uses

- Creating slower derived clocks
- Dividing fabric or interface clocks
- Clock domain generation without consuming MMCM outputs

---

# 16. BUFCE_LEAF

Leaf-level clock buffer used near clock loads.

### Purpose

Drives final local clock points from HCS distribution resources.

### Benefit

Improves local distribution efficiency and supports local enable behavior.

---

# 17. BUFG_GT and BUFG_GT_SYNC

Used for clocks originating from gigabit transceivers or RFSoC converter blocks.

### Typical Uses

- Recovered serial clocks
- GT transmit clocks
- High-speed interface domains

Synchronization logic may be automatically inserted by Vivado.

---

# 18. BUFG_PS

Special clock buffer for Zynq UltraScale+ MPSoC processor system clocks entering programmable logic.

### Importance in Zynq MPSoC

Allows processor-generated clocks to drive PL clock networks.

### Common Uses

- AXI clock domains
- Peripheral clocks
- Processor-sourced fabric clocks

---

# 19. MMCM Overview

The MMCM is the most capable clock management block.

### Main Functions

- Frequency synthesis
- Fractional or integer clock generation (tool/device dependent options)
- Phase shifting
- Jitter filtering
- Duty cycle correction
- Clock deskew
- Multiple output clocks

### Example

Input 100 MHz oscillator can generate:

- 200 MHz CPU fabric clock
- 50 MHz peripheral clock
- 125 MHz Ethernet clock

from one MMCM depending on valid constraints.

---

# 20. MMCM Internal Operation

The MMCM uses:

- Input divider
- Phase Frequency Detector (PFD)
- Charge pump / loop filter
- Voltage Controlled Oscillator (VCO)
- Output dividers
- Feedback path

### Purpose of Feedback

Align generated clocks with source or remove routing delay.

---

# 21. Fine Phase Shift

MMCM supports dynamic phase shifting.

### Used For

- Sampling alignment
- Source synchronous interfaces
- Timing margin experiments
- Delay compensation

---

# 22. MMCM Primitives

UltraScale family commonly uses:

- `MMCME3_BASE`
- `MMCME3_ADV`

UltraScale+ uses E4 equivalents.

Usually instantiated through Clocking Wizard IP rather than handwritten primitives.

---

# 23. PLL Overview

Each CMT also contains two PLLs.

### PLL Main Uses

- I/O clock generation
- Simpler frequency synthesis
- Jitter filtering
- Basic phase shifting

### Compared with MMCM

PLLs are simpler and have fewer advanced capabilities.

They generally provide:

- Fewer features
- Less deskew flexibility
- Narrower divider/multiplier options

### When to Use PLL

Use PLL when MMCM features are unnecessary and a simpler solution is sufficient.

---

# 24. PLL Primitives

Common primitive names:

- `PLLE3_BASE`
- `PLLE3_ADV`

UltraScale+ uses E4 variants.

---

# 25. Clock Distribution Modes

Clock buffers can distribute clocks in two major ways.

## Through Routing Tracks to a Chosen Root

Clock first travels to a selected root point, then fans out.

### Benefit

Better skew optimization near grouped logic.

## Directly to Distribution Tracks

Clock fans out sooner.

### Benefit

Lower insertion delay.

---

# 26. Clocking Guidelines for Practical Designs

## Use Dedicated Clock Pins

Always bring external clocks through GC pins whenever possible.

## Use Clock Buffers Properly

Do not drive high-fanout clocks through normal LUT routing.

## Prefer Enables Over Fabric-Gated Clocks

Use BUFGCE rather than LUT-based clock gating.

## Minimize Number of Clock Domains

More clock domains increase CDC complexity.

## Use MMCM/PLL for Generated Clocks

Do not build clocks using logic dividers unless specifically justified.

## Keep Related Logic Near Its Clock Region

Helps routing and timing.

---

# 27. Zynq MPSoC Specific Professional Notes

In Zynq UltraScale+ MPSoC, clocks may originate from:

- External oscillators
- Processor system PLL outputs
- PL MMCM/PLL resources
- GT recovered clocks

Designers must carefully define:

- PL fabric clocks
- AXI bus clocks
- DDR/user clocks
- Video clocks
- Peripheral clocks

Use BUFG_PS when PS clocks must feed PL.

---

# 28. Vivado Recommended Flow

In most projects, use:

- Clocking Wizard IP for MMCM/PLL setup
- XDC constraints for clock definitions
- `create_clock`
- `create_generated_clock`

Then validate with:

- Timing summary
- Clock interaction report
- CDC analysis

---

# 29. Common Mistakes

## Using Normal Logic as Clock Gating

Causes skew/glitch risk.

## Too Many Derived Clocks

Creates unnecessary CDC complexity.

## Ignoring Clock Constraints

Leads to false timing closure assumptions.

## Using Wrong Input Pins for Clock

May degrade timing.

## Overusing MMCM Outputs Without Planning

Can exhaust clocking resources.

---

# 30. Quick Revision Takeaways

- UltraScale+ clocking is based on clock regions, HCS rows, and dedicated routing.
- CMT contains one MMCM and two PLLs.
- MMCM is the preferred advanced clock synthesis block.
- PLL is simpler and often used for I/O-oriented clocking.
- BUFG family buffers distribute clocks safely and efficiently.
- BUFGCE is preferred for glitchless clock enable.
- BUFGCTRL is used for safe clock switching.
- BUFG_PS is important for PS-to-PL clocks in Zynq MPSoC.
- Use dedicated GC pins for external clocks.
- Good clock planning is critical for timing closure and stable FPGA designs.