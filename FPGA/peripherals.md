# Memory

A memory unit is a device to which binary information is transferred for
storage and from which information is retrieved when needed for
processing. A memory unit is an integral part of any computing system,
and its primary purpose is to hold instructions and data. When data
processing takes place, information from memory is transferred to
selected registers in the processing unit. Intermediate and final
results obtained in the processing unit are transferred back to be
stored in memory.

shows a logical picture of components of a Modern Computer. One can
observe how different types of memories are interfaced with a processor.

::: center
![Component of a Modern
Computer](images/ModernComputer.png){#ModernComputer
width="\\textwidth"}
:::

## Types of memory

In a broad sense, a memory system in any digital systems can be divided
into two types:

1.  Read Only Memory (ROM), and

2.  Random Access Memory (RAM)

**Read Only Memory (ROM)** is a type of memory where the data has been
prerecorded. This means that suitable binary information is already
stored inside memory and can be retrieved or read at any time. However,
that information cannot be altered by writing. Data stored in ROM is
retained even after the computer is turned off non-volatile. There are
four types of ROM:

Programmable ROM (PROM)

:   where the data is written after the memory chip has been created. It
    is non-volatile.

Erasable Programmable ROM (EPROM)

:   where the data on this non-volatile memory chip can be erased by
    exposing it to high-intensity UV light.

Electrically Erasable Programmable ROM (EEPROM)

:   where the data on this non-volatile memory chip can be electrically
    erased using field electron emission.

Mask ROM

:   in which the data is written during the manufacturing of the memory
    chip.

**Random Access Memory (RAM)** is used to store the programs and data
being used by the CPU in real-time. The data on the random access memory
can be read, written, and erased any number of times. RAM is a hardware
element where the data being currently used is stored. It is a volatile
memory which means that the data stored on the RAM gets erased on a
power reset.

## Memory Hierarchy Design

In the Computer System Design, Memory Hierarchy is an enhancement to
organize the memory such that it can minimize the access time. The
Memory Hierarchy was developed based on a program behavior known as
locality of references. clearly demonstrates the different levels of
memory hierarchy:

::: center
![Component of a Modern
Computer](images/MemoryStructure.png){#MemoryStructure
width="\\textwidth"}
:::

This Memory Hierarchy Design is divided into 2 main types:

External Memory or Secondary Memory

:   Comprising of Magnetic Disk, Optical Disk, Magnetic Tape peripheral
    storage devices which are accessible by the processor via I/O
    Module.

Internal Memory or Primary Memory

:   Comprising of Main Memory, Cache Memory & CPU registers. This is
    directly accessible by the processor.

In the Internal Memory or Primary Memory, the entire program and data of
a given application cannot be located fully inside local memories BRAMs,
UltraRAMs(FPGAs), cache memories (processors). The memory is implemented
as a hierarchy, where we have the registers inside the processor/FPGAs
as the fastest memory, then we have caches/BRAMs. And, then the next
level of memory is known as the main memory or DRAM system.

# RAM

**Random Access Memory (RAM)** is the internal memory of the digital
system for storing data, program, and program result. It is a read/write
memory which stores data until the machine is working. There are two
types of RAM:

Static RAM (SRAM)

:   which stores a bit of data using the state of a six transistor
    memory cell.

Dynamic RAM (DRAM)

:   which stores a bit data using a pair of transistor and capacitor
    which constitute a DRAM memory cell.

## SRAM

Static random access memory (static RAM or SRAM) is a type of RAM that
uses latching circuitry (flip-flop) to store each bit. shows an SRAM
cell.

::: center
![Static RAM cell](images/SRAM.png){#SRAM width="5in"}
:::

SRAM cell can store 1 bit of information which consists of a row line
and a bitline. A pair of bit lines is used for storage of every bit, one
is bitline and the other one is bitline compliment. Bitline compliment
is a logical compliment of the bitline.

Two cross coupled NOT gates are connected by two transistor, which are
connected to the row select. So, once a particular row is selected both
T1 and T2 is going to be in on position. So, whatever value is there in
the bitline it flows into the not gates. The value in the bitline will
get stored inside the two cross coupled NOT gates loop. Hence,
transistor will basically act as a switch in this context.

### Large SRAM implementation

These SRAM memory cells, consisting of six transistors, organized as
rows and columns to get an organized structure for the main memory.
Address needs to be generated consisting two components, 'n' bits
representing the rows and 'm' bits representing the columns.

While reading from the memory, the row is chosen by using an n to
$2^(n)$ decoder.Once the row is selected, the entire contents of the row
are transferred to a sense amplifier. And, the single bit extracted by
selecting from 'm' column number.

Read sequence is as follows:

1.  Address decode

2.  Drive row select

3.  Selected bit-cells drive bitlines (entire row is read together)

4.  Column select (Data is ready)

## DRAM

Dynamic random access memory (Dynamic RAM or DRAM) is a type of random
access memory that stores each bit of data in a memory cell, usually
consisting of a tiny capacitor and a transistor, both typically based on
metal-oxide-semiconductor (MOS) technology.

::: center
![Dynamic RAM cell](images/DRAMCell.png){#DRAMCell width="5in"}
:::

Bits are basically stored as charges on the capacitor and a memory cell
lose charge when it is read. When there exists a potential difference
between the parallel plates of a capacitor, it is called as logic 1.
And, when the potential difference between the two parallel plates of a
capacitor is less than a threshold value, then it is called as logic 0.

-   Bits are stored as charges on capacitor.

-   Memory cell loses charge when read.

-   Memory cell loses charge over time.

-   A flip flop in sense amplifier amplifies and regenerates the bitline
    and data bit is multiplexed out of it.

Since the capacitor discharges over time, the information stored
eventually fades unless the capacitor is periodically REFRESHed. This is
where the 'D' in DRAM comes from. It refers to Dynamic as opposed to
static in SRAM.

### DRAM vs SRAM

**DRAM**

-   Slower access (capacitor)

-   Higher density (transistor, capacitor cell)

-   Lower cost

-   Requires refresh (power, performance, circuitry)

-   Manufacturing requires putting capacitor and logic together

**SRAM**

-   Faster access (no capacitor)

-   Lower density (6 transistor cell)

-   Higher cost

-   No need for refresh

-   Manufacturing compatible with logic process (no capacitor)

::: highlight
Density plays a crucial role in accommodating larger memory in a smaller
size memory. DRAM is preferred in order to implement the primary memory.
:::

### Asynchronous & Synchronous DRAM

In different generations of dynamic RAM there is an improvement in the
speed as well as the reduction in the power consumption. Asynchronous
Dynamic RAM can be considered as the oldest generation of dynamic RAM.
Asynchronous DRAM means that the RAM is not synchronized with the CPU
clock. The obvious disadvantage of this particular type of RAM was that
then CPU does not know the exact timing at which the data will be
available from the RAM on the input output bus.

This problem has been overcome by the next generation of RAM, which is
known as the synchronous DRAM. In case of SDRAM, the RAM is synchronized
with the CPU clock. Now, the advantage of this type of SDRAM is that the
CPU or to be precise, the DRAM memory controller knows the exact timing
or the number of cycles after which the data will be available on the
bus. And hence, the CPU does not need to wait for the memory access.
This also results in increasing memory read & write speeds. The
synchronous DRAM modules are operated at 3.3V. SDRAM or synchronous DRAM
is also known as the Single Data Rate SDRAM as the data is transferred
at the every rising edge of the clock cycle.

### Interleaving

One of the main issues in accessing a single monolithic memory is that A
single monolithic memory array takes long to access and does not enable
multiple accesses in parallel.

The solution to this problem is to divide the entire memory into
multiple banks that can be accessed independently (in the same cycle or
in consecutive cycles).

The key design issue is to map the data into different banks. This issue
is resolved by the process referred to as Interleaving, or Banking. In
interleaving,

-   Address space partitioned into separate banks

-   No increase in data store area

-   Bits in address determines which bank an address maps to

-   Cannot satisfy multiple accesses to the same bank

-   Crossbar interconnect in input as well as output

-   Bank conflicts: Two accesses to the same bank are difficult to
    handle

One simple way of implementing banking is odd even separation. All the
even addresses can be considered as mapped to bank 0 and all the odd
addresses can be considered as mapped to bank 1.

The address provided to read the data is typically referred as \"logical
address\". Logical address is translated to a physical address before it
is presented to the DRAM. The physical address is made up of the
following fields:

-   Bank Group

-   Bank

-   Row

-   Column

These individual fields are then used to identify the exact location in
the memory to read-from or write-to.

### Organization of the DRAM

DRAM consists of multiple hierarchies of channels, DIMM(Dual Inline
Memory Module), rank, chip, bank, row columns, and B-cells/ Memory
Cells. A digital system can request data reads from memory at any point
of time. To read from the memory, address has to be provided and to
write to the memory, data & address has to be provided.

shows the organization of the DRAM.

-   The processor may have multiple channels it may have multiple
    address buses or data buses.

-   A channel is formed by joining multiple DIMMs.

-   The DIMM has a front side (known as rank 0) and a back side (known
    as rank 1).

-   Rank is a set of chips that respond to the same command and same
    address at the same time, but with different pieces of requested
    data.

-   Both ranks are usually provided with a common address, and one rank,
    either rank 0 or rank 1, gives the corresponding data.

-   Rank comprises of multiple chips.

-   Each chip holds and shares a sub component of the entire data held
    by a rank.

-   Each chip has a 3D structure consisting multiple banks with each
    bank consisting a layer of rows and columns.

-   Breaking down a bank, each bank consists of rows as well as columns.

::: center
![Organization of the
DRAM](images/DRAMOrganization.png){#DRAMOrganization
width="\\textwidth"}
:::

Going down another level, DRAM consists of a page mode structure. DRAM
bank is a 2D array of cells which consists of rows and columns. Each
Bank contains the following:

-   Memory Arrays

-   Row Decoder

-   Column Decoder

-   Sense Amplifiers

Once the Bank Group and Bank have been identified, the Row part of the
address activates a line in the memory array. This is called the \"Word
Line\" and activating it reads data from the memory array into \"Sense
Amplifiers\". Sense amplifier are kept in row buffers. The Column
address then reads out a part of the word that was loaded into the Sense
Amplifiers. The width of the column is called the \"Bit Line\".

The width of a column is standard it is either 4 bits, 8 bits or 16 bits
wide and DRAMs are classified as x4, x8 or x16 based on this column
width. Another thing to note is that, the width of the data bus is same
as the column width.

### DRAM Subsystem

The DRAM talks to the ASIC or FPGA through the system called as the DRAM
Subsystem. DRAM Subsystem is made up of 3 components:

-   The DRAM memory

-   A DRAM PHY

-   A DRAM Controller

::: center
![DRAM Subsystem](images/DRAMSubsystem.png){#DRAMSubsystem
width="\\textwidth"}
:::

::: {#tab:DRAMComponents}
  -------------------------------------------------------------------
  **Block**         **Description**
  ----------------- -------------------------------------------------
  Physical (PHY)    The direct interface to the external DRAM memory
  Layer             bus. Instantiates logic resources to generate the
                    memory clock, control/address signals, and
                    data/data strobes to/from the memory. Executes
                    the DRAM power-up and initialization sequence
                    after system reset. Performs read data capture
                    timing training calibration after system reset,
                    and adjusts read data timing using (IDELAY)
                    elements.

  Controller        Generates memory commands (Read, Write,
                    Precharge, Refresh) based on commands from the
                    User Interface block. Optionally, can implement a
                    bank management scheme to reduce overhead with
                    opening and closing of bank/rows. The controller
                    logic takes over the DRAM address/control bus
                    after successful completion of DRAM memory
                    initialization and read timing calibration by the
                    PHY layer.

  User Interface    Custom interface for the user specific
                    application to issue commands and write data to
                    the DRAM memory interface, and to receive read
                    data from the DRAM memory interface.

  Clocking / Reset  Generates clocks using Digital Clock Manager
  Logic             (DCM) module. Synchronizes resets to the various
                    clock domains used in rest of design.
  -------------------------------------------------------------------

  : DRAM Memory Interface Design Major components & Descriptions
:::

The DRAM is soldered down on the board. The PHY and controller, along
with user logic are typically part of the same FPGA or ASIC. The
interface between the user logic and the controller can be user defined
and need not be standard. When the user logic makes a read or write
request to the controller, it issues a logical address. The controller
then converts this logical address to a physical address and issues a
command to the PHY. The Controller and PHY talk to each other over a
standard interface called the DFI interface. The PHY then does all the
lower level signaling and drives the physical interface to the DRAM.
This interface between the PHY and memory is specified in the JEDEC
standard. Think of the controller as the brains and the PHY as the
brains.

When you activate a row, the whole page is loaded into the Sense
Amplifiers, so multiple reads to an already open page are lesser
expensive because you can skip the first step of row activation. The
controller typically has the capability to re-order requests issued by
the user to take advantage of this. To do the re-ordering it uses a
small cache or TCAM and always returns the latest data, so you don't
have to worry about stale data or collisions occurring because of this
re-ordering done by the controller. The PHY contains the analog drivers
and provides the capability to tweak registers to increase drive
strength or change terminations, in order to improve signal integrity.

### Basic DRAM Controller Operation

**DRAM Commands Issued by the Controller:** The commands are detected by
the memory using these control signals: Row Address Select (RAS), Column
Address Select (CAS), and Write Enable (WE) signals. Clock Enable (CKE)
is held High after device configuration, and Chip Select (CS) is held
Low throughout device operation.

**DRAM Memory Commands:**

::: description
It is used to deactivate the open row in a particular bank. The bank is
available for a subsequent row activation a specified time (tRP) after
the Precharge command is issued.

Precharge command:

1.  Destructive read: Any read operation that is carried out on a
    capacitor, will discharge the charges that exist over the capacitor
    plates leading to a 0 potential layer any reading operation will
    delete the value stored.

2.  The existing value in the row buffer should be stored back for a new
    read command.

3.  The operation of storing the contents in the row buffer back to the
    appropriate row is known as Precharge.

DRAM devices need to be refreshed regularly after a certain time period.
The circuit to flag the Auto Refresh commands is built into the
controller. The controller issues an Auto Refresh command after it has
completed its current burst. Auto Refresh commands are given the highest
priority in the design of the controller.

Before any read or write commands can be issued to a bank within the
DRAM memory, a row in the bank must be activated using an active
command. After a row is opened, read or write commands can be issued to
the row.

The Read command is used to initiate a burst read access to an active
row. The values in registers select the bank address & the starting
column location in the active row. After the read burst is over, the row
is still available for subsequent access until it is precharged.

The Write command is used to initiate a burst write access to an active
row. The values in registers select the bank address & the starting
column location in the active row. DRAMs use a Write Latency (WL) equal
to Read Latency (RL) minus one clock cycle.\
$Write Latency = Read Latency - 1 = (Additive Latency + CAS Latency) - 1$
:::

DRAM Controller Operation is as follows:

-   In order to carry out the instruction execution with the help of an
    instruction pipeline, during the fetch stage cache memory will be
    used. If the required instruction or data is not available even in
    the last level cache then DRAM is required.

-   Main processing unit has to communicate with the physical DRAM
    device and that communication is carried out by the DRAM controller.
    The controller itself has it's own latency called as Controller
    latency.

-   Multiple requests coming from multiple tiles or multiple processors
    queue up inside the DRAM controller. These requests have to be
    scheduled in order to be executed by the DRAM controller resulting
    in Queuing delay & scheduling delay.

-   Once scheduling is done, these requests have to be converted into a
    couple of basic commands.

-   Appropriate commands are then propagated from the controller to the
    physical memory and generating bus latency.

-   Once the request reaches the physical memory unit, it has to split
    into column address and row address.

-   There are different scenarios while handling a request:

    -   Opened Row Scenario: A scenario where a given row is already
        kept in the row buffer is known as a open row scenario. In this
        scenario, only a Column Address Strobe (CAS) is required. There
        is no need of Activate command.

    -   Closed Row Scenario: A scenario where a given row is not already
        kept in the row buffer is known as a closed row scenario. Access
        to a closed row is as follows:

        -   Activate command

        -   Read/Write command

        -   Precharge command closes the row and prepares the bank for
            next access

    -   Row conflict Scenario: In this scenario, some other row is
        already open. In this case row has to be closed first and then
        Row Address Strobe (RAS) and Column Address Strobe (CAS) has to
        be given one after another with appropriate timing gap between
        them.

-   The physical memory unit returns the data back to the controller
    generating bus latency.

-   Once data reaches DRAM controller, the controller transfers it to
    the CPU or the last level cache.

### Internal Physical Structure of DRAM

::: center
![Top Level DRAM block diagram](images/DRAMPHY.png){#Top Level
width="\\textwidth"}
:::

Usually, DRAM has clock, reset, chip-select, address and data inputs as
shown in . The mentions all the pins in detail.

::: center
![DRAM block diagram](images/DRAMPorts.png){#DRAM ports
width="\\textwidth"}
:::

## DDR RAM

In case of the next generation of the SDR DRAM (Single Data Rate DRAM or
synchronous DRAM), the data is transferred twice during the clock cycle.
First, during the positive edge and secondly, during the negative edge
of the clock cycle. And that is why this generation of the SDRAM is
known as the **Double Data Rate** or **DDR SDRAM**.

There are different generations of DDR RAM ranging from the DDR1 up to
the DDR4 which is considered to be the latest. The first generation of
DDR RAM is known as the DDR1 RAM. As compared to the SDR SDRAM, the
voltage levels has been reduced from 3.3V to the 2.5V.

There are a total two types of frequencies associated with DRAM:

Input output clock frequency

:   is the frequency at which the data is being transferred between the
    RAM and the memory controller.

RAM Internal clock frequency

:   of the RAM is the frequency which is being used by the RAM for the
    internal operations.

In case of SDRAM, input output clock frequency and the internal clock
frequency of the RAM are same. For PC-100 specification on the SDRAM
module means that the input output clock frequency is 100 mega transfers
per second and if the data bus is 64 bit wide, then the data rate in
terms of the bits per second will be 100 MHz into 64 bits. Which is 800
Megabytes per second.

In case of DDR RAM, the data is being transferred both during the rising
as well as the falling edge of the clock cycle. Hence, in a single clock
cycle, instead of a single bit, 2 bits are pre-fetched which is known as
the **2 bit pre-fetch**. In case of DDR1 RAM, the internal clock
frequency, as well as the input output bus clock frequency, are same.
Generally, DDR1 RAM is operated in the range of 133 MHz up to 200 MHz.
But if you see the data rate at the input output bus, it will be double
compared to the clock frequency. In case of DDR1 RAM, the data is
transferred both during rising as well as the falling edge. For suppose
if DDR1 RAM is operated at 133 MHz then the data rate will be 266 Mega
transfer per second. If the bus frequency is 200 MHz then the data
transfer rate will be 400 Mega transfer per second. And if the input
output bus is 64 bits wide, then the data rate will be 3200 Megabytes
per second.

Nowadays, DDR RAMs are generally denoted by the term DDR followed by the
transfer rate of this RAM. For a DDR1 module or a DDR1 stick, most
probably will have a specification like PC-3200. It means that the
maximum speed or the maximum bandwidth which can be achieved by this
DDR1 RAM is 3200 Megabytes per second.

## DDR2 RAM

After the first generation, the second generation of DDR RAM is DDR2
RAM. DDR2 SDRAM superseded the original DDR1 SDRAM specification, and
was superseded by DDR3 SDRAM when launched in 2007. The maximum capacity
on commercially available DDR2 DIMMs is 8GB, but chipset support and
availability for those DIMMs is sparse and more common 2GB per DIMM are
used. In case of DDR2 RAM, it is operated at 1.8 V instead of 2.5 V
unlike the DDR1 RAM. The internal RAM clock frequency is same as the
previous generation. Instead the data rate is doubled compared to the
first generation which was achieved by increasing the number of bits
that are being pre-fetched during each cycle. In case of this DDR2 RAM
instead of 2 bits, 4 bits are pre-fetched during each cycle. In other
words, the internal bus width of DDR2 RAM has been doubled when compared
with DDR1.

For suppose if the input output bus is 64 bits wide, then the internal
bus width of this RAM will be equal to 128 bits. So, in this way, in a
single cycle, this RAM can handle double amount of data. To handle the
same amount of data, the clock frequency of this input output bus should
be get doubled. Suppose DDR2 RAM, is operated at 100 MHz internal clock
frequency then the input output bus should have the clock frequency of
200 MHz. And in case of this DDR RAM, as data is transferred both during
rising and falling edge, so the data rate will be doubled compared to
the clock frequency, that is 400 mega transfer per second. Suppose if
DDR2 RAM is operated at 400 MHz clock frequency, then the data rate will
be equal to 800 mega transfer per second. And in terms of DDR
terminology, it can be written as DDR2-800 or PC2-6400.

## DDR3 RAM

After the second generation, the third generation of DDR RAM is the DDR3
RAM. DDR3 SDRAM superseded the original DDR2 SDRAM specification, and
was superseded by DDR4 SDRAM when launched in 2014. The DDR3 standard
permits DRAM chip capacities of up to 8 gibibits (Gibit), and up to four
ranks of 64 bits each for a total maximum of 16 gibibytes (GiB) per DDR3
DIMM. In case of this DDR3 RAM, the voltage is further reduced from 1.8V
to the 1.5V. The internal clock frequency of DDR3 RAM is slightly
improved compared to DDR2. But the data rate that you can achieve with
the same frequency has been doubled as compared to the DDR2. In case of
DDR3 RAM, the number of bits that is being pre-fetched has been further
increased from 4 bits to the 8 bits. In other words, the internal data
bus width of RAM has been increased 2 times compared to DDR2 and 4 times
to DDR1.

For suppose if the internal clock frequency is 100 MHz, then to match
the data rate, the input output bus should be get operated at the 4
times the clock frequency that is 400 MHz. And the transfer rate will be
800 mega transfer per second. For DDR3-800 followed by PC3-6400 on any
DDR3 RAM, means that the clock frequency of this RAM is 400 MHz and the
maximum transfer rate which can be achieved is 800 mega transfer per
second. Maximum bandwidth of the RAM is 6400 Megabytes per second.

## DDR4 RAM

DDR4 SDRAM is the abbreviation for 'Double Data Rate fourth generation
synchronous dynamic random-access memory', the latest variant of memory
in computing. DDR4 is able to achieve higher speed and efficiency thanks
to increased transfer rates and decreased voltage. The primary
advantages of DDR4 over its predecessor, DDR3, include higher module
density and lower voltage requirements, coupled with higher data rate
transfer speeds. The DDR4 standard allows for DIMMs of up to 64 GiB in
capacity, compared to DDR3's maximum of 16 GiB per DIMM.

After the third generation, the fourth generation of DDR RAM is DDR4
RAM. DDR4 SDRAM superseded the original DDR3 SDRAM specification, and
was superseded by DDR5 SDRAM when launched in 2020. The DDR4 standard
allows for DIMMs of up to 64 GiB in capacity, compared to DDR3's maximum
of 16 GiB per DIMM. In case of this DDR4 RAM, the operating voltage has
been further reduced from 1.5V to the 1.2V. The number of bits that are
being pre-fetched is same as DDR3 i.e. 8 bits per cycle. In case of this
DDR4 RAM, the internal clock frequency of the RAM has been increased.
For suppose if you are operating at 400 MHz then the clock frequency of
the input output bus should be 4 times, that means 1600 MHz. The
transfer rate will be equal to 3200 Mega transfer per second. Module
terminology DDR4-3200 followed by PC4-25600. 25600 is the speed in terms
of Megabytes per second.

-   **Single channel mode:** In single channel mode, the physical RAM,
    uses the usual input output bus width (64 bits).

-   **Dual channel mode** In dual channel mode, the same physical RAM,
    uses twice the input output bus width to effectively achieve twice
    the data rate. Suppose, there is an 8 GB DDR4 RAM running in single
    channel mode and two 4 GB DDR4 RAMs running in dual channel mode,
    then the bandwidth that can be achieved with two 4 GB of DDR4 RAM
    will be better as compared to the single channel 8GB of DDR4 RAM.

## Application specific DDR versions

A compact version of DIMM module is known as Small Outline DIMM Modules
(SO-DIMM). Another version of dynamic RAMs which are used inside the
mobile or smartphones are known as the mobile DDR or Low Power DDR. Low
Power DDR RAMs are also having different generations. Starting from
LPDDR1 up to the LPDDR4. LPDDR RAMs are optimised for the low power
consumption. Another specially catered version of DDR RAMs which is used
for graphics cards is known as the graphics DDR or GDDR. As this
Graphical DDR is used for the multimedia applications, the data handling
is quite extensive. Hence, GDDR RAMs have larger bandwidth compared to
usual DDRs.

## DDR Packaging

The older generations of DRAMs were available in the Dual Inline
Package(DIP). Then after the next generation of RAMs were available in
the Single In-Line Modules (SIMM). In Single In-Line module, the memory
chips are soldered onto the one PCB, and the pins are available on the
single side of the PCB. And that is a reason, it is known as the Single
In-Line Modules. Single In-line module can provide data bus width of 32
bits. But suppose if you want 64 bits of the data bus, then you need to
connect the two single In-line modules in the parallel.

After the next generation of RAMs were available in the Dual In-Line
Module or DIMM. In Dual In-Line Module, it is possible to have 64 bits
wide data bus. Also, the pins are available both in front as well as the
back of the PCB. And that is a reason, it is known as the Dual In-Line
Module.

All the DDR generations have a different number of pins as well as the
different operating voltage. Hence, all the four generation of RAMs are
not either forward or backward compatible. So, suppose a motherboard
supporting DDR3 RAM, will not support either DDR2 or DDR4 RAM.

## Xilinx DDR MIG Controller IP

The Memory Interface Generator (MIG) generates DDR4 SDRAM, DDR3 SDRAM,
DDRII SRAM, DDR SDRAM, DDR2 SDRAM, QDRII SRAM, and RLDRAM II interfaces
for various Xilinx FPGAs. The tool takes inputs such as the memory
interface type, FPGA family, FPGA devices, frequencies, data width,
memory mode register values, and so forth, from the user through a
graphical user interface (GUI). The tool generates RTL, SDC, UCF, and
document files as output. RTL or EDIF (EDIF is created after running a
script file, where the script file is a tool output) files can be
integrated with other design files.

MIG is a tool used to generate memory interfaces for Xilinx FPGAs. MIG
generates Verilog or VHDL RTL design files, user constraints files
(UCF), and script files. The script files are used to run simulations,
synthesis, map, and par for the selected configuration.

# Flash Memory

Flash memory is an electronic (solidstate) nonvolatile computer memory
storage medium that can be electrically erased and reprogrammed. The two
main types of flash memory are named after the NAND and NOR logic gates.
The individual flash memory cells, consisting of floatinggate MOSFETs
(floatinggate metaloxidesemiconductor fieldeffect transistors), exhibit
internal characteristics similar to those of the corresponding gates.
While EPROMs had to be completely erased before being rewritten,
NANDtype flash memory may be erased, written and read in blocks (or
pages) which are generally much smaller than the entire device. NORtype
flash allows a single machine word (byte) to be written to an erased
location or read independently. A flash memory device typically consists
of one or more flash memory chips (each holding many flash memory cells)
along with a separate flash memory controller chip. The NAND type is
found primarily in memory cards, USB flash drives, solidstate drives
(those produced in 2009 or later), and similar products, for general
storage and transfer of data. NAND or NOR flash memory is also often
used to store configuration data in numerous digital products, a task
previously made possible by EEPROM or batterypowered static RAM.

**Serial Flash** Serial flash is a small, lowpower flash memory that
provides only serial access to the data rather than addressing
individual bytes, the user reads or writes large contiguous groups of
bytes in the address space serially. Serial Peripheral Interface Bus
(SPI) is a typical protocol for accessing the device. When incorporated
into an embedded system, serial flash requires fewer wires on the PCB
than parallel flash memories, since it transmits and receives data one
bit at a time. This may permit a reduction in board space, power
consumption, and total system cost. A flash memory controller (or flash
controller) manages data stored on flash memory and communicates with a
computer or electronic device. Flash memory controllers can be designed
for operating in low dutycycle environments like SD cards, Compact Flash
cards, or other similar media.

## QSPI Flash

AXI Quad SPI LogiCORE IP AXI Quad Serial Peripheral Interface (SPI) core
connects the AXI4 interface to those SPI slave devices that support the
Standard, Dual, or Quad SPI protocol instruction set. This core provides
a serial interface to SPI slave devices. The Dual/Quad SPI is an
enhancement to the standard SPI protocol (described in the Motorola
M68HC11 data sheet) and provides a simple method for data exchange
between a master and a slave.

Configurable SPI modes:

-   Standard SPI mode

-   Dual SPI mode

-   Quad SPI mode

-   Programmable SPI clock

# EMMC

eMMC stands for embedded MultiMedia Card and refers to a package
consisting of both flash memory and a flash memory controller. The
controller here is divided into 2 parts: 1. Host controller 2. Device
controller. Host controller sits on the host device and is usually
operates on a higher layer of programming. Device controller sits inside
the flash memory hardware. It takes signals controlled by the Host
controller and converts them into interpretable signals for the flash
memory. The eMMC specification covers the behavior of the interface and
the device controller. As part of this specification the existence of a
host controller and a memory storage array are implied but the operation
of these pieces is not fully specified.

## eMMC Device Overview

The eMMC device transfers data via a configurable number of data bus
signals. The communication signals are:

-   **CLK** Each cycle of this signal directs a one bit transfer on the
    command and either a one bit (1x) or a two bits transfer (2x) on all
    the data lines. The frequency may vary between zero and the maximum
    clock frequency.

-   **Data Strobe** This signal is generated by the device and used for
    data output and CRC status response output in HS400 mode. The
    frequency of this signal follows the frequency of CLK. For data
    output each cycle of this signal directs two bits transfer(2x) on
    the data one bit for positive edge and the other bit for negative
    edge. For CRC status response output, the CRC status is latched on
    the positive edge only, and don't care on the negative edge.

-   **CMD** This signal is a bidirectional command channel used for
    device initialization and transfer of commands. The CMD signal has
    two operation modes: opendrain for initialization mode, and pushpull
    for fast command transfer. Commands are sent from the eMMC host
    controller to the eMMC device and responses are sent from the device
    to the host.

-   **DAT0DAT7** These are bidirectional data channels. The DAT signals
    operate in pushpull mode. Only the device or the host is driving
    these signals at a time. By default, after power up or reset, only
    DAT0 is used for data transfer. A wider data bus can be configured
    for data transfer, using either DAT0DAT3 or DAT0DAT7, by the eMMC
    host controller. The eMMC device includes internal pullups for data
    lines DAT1DAT7. Immediately after entering the 4bit mode, the device
    disconnects the internal pull ups of lines DAT1, DAT2, and DAT3.
    Correspondingly, immediately after entering to the 8bit mode the
    device disconnects the internal pullups of lines DAT1DAT7.

All communication between host and device are controlled by the host
(master). The host sends a command, which results in a device response.
Five operation modes are defined for the eMMC system (hosts and
devices):

-   Boot mode The device will be in boot mode after power cycle,
    reception of CMD0 with argument of 0xF0F0F0F0 or the assertion of
    hardware reset signal.

-   Device identification mode The device will be in device
    identification mode after boot operation mode is finished or if host
    and /or device does not support boot operation mode. The device will
    be in this mode, until the SET_RCA command (CMD3) is received.

-   Interrupt mode Host and device enter and exit interrupt mode
    simultaneously. In interrupt mode there is no data transfer. The
    only message allowed is an interrupt service request from the device
    or the host.

-   Data transfer mode The device will enter data transfer mode once an
    RCA is assigned to it. The host will enter data transfer mode after
    identifying the device on the bus.

-   Inactive mode The device will enter inactive mode if either the
    device operating voltage range or access mode is not valid. The
    device can also enter inactive mode with GO_INACTIVE_STATE command
    (CMD15). The device will reset to Pre-idle state with power cycle.

::: center
![Internal block diagram of EMMC IP](images/emmc.png){#emmc
width="\\textwidth"}
:::

If the CMD line is held LOW for 74 clock cycles and more after powerup
or reset operation (either through CMD0 with the argument of 0xF0F0F0F0
or assertion of hardware reset for eMMC, if it is enabled in Extended
CSD register byte \[162\], bits \[1:0\]) before the first command is
issued, the slave recognizes that boot mode is being initiated and
starts preparing boot data internally. Timing diagram of EMMC IP Boot up
sequence is shown in

::: center
![Timing diagram of EMMC IP Boot up
sequence](images/BootUpSeqTiming.png){#BootUpSeqTiming
width="\\textwidth"}
:::

The partition from which the master will read the boot data can be
selected in advance using EXT_CSD byte \[179\], bits \[5:3\]. The data
size that the master can read during boot operation can be calculated as
128KB X BOOT_SIZE_MULT (EXT_CSD byte \[226\]). Within 1 second after the
CMD line goes LOW, the slave starts to send the first boot data to the
master on the DAT line(s). The master must keep the CMD line LOW to read
all of the boot data. The master must use push-pull mode until boot
operation is terminated.

The master can choose to use single data rate mode with
backward-compatible interface timing, single data rate with high-speed
interface timing or dual data rate timing (if it supported) shown in
10.6 by setting a proper value in EXT_CSD register byte \[177\] bits
\[4:3\]. EXT_CSD register byte \[228\], bit 2 tells the master if the
high-speed timing during boot is supported by the device. The master can
also choose to use the dual data rate mode with interface during boot by
setting '10' in EXT_CSD register byte \[177\], bits \[4:3\]. EXT_CSD
register byte \[228\], bit 1 tells the master if the dual data rate mode
during boot is supported by the device.

The master can choose to receive boot acknowledge from the slave by
setting '1' in EXT_CSD register, byte \[179\], bit 6, so that the master
can recognize that the slave is operating in boot mode. If boot
acknowledge is enabled, the slave has to send acknowledge pattern '010'
to the master within 50ms after the CMD line goes LOW. If boot
acknowledge is disabled, the slave will not send out acknowledge pattern
'0-1-0.' In the single data rate mode, data is clocked out by the device
and sampled by the host with the rising edge of the clock and there is a
single CRC per data line.

In the dual data rate mode, data is clocked out with both the rising
edge of the clock and the falling edge of the clock and there are two
CRC appended per data line. In this mode, the block length is always 512
bytes, and bytes come interleaved in either 4-bit or 8-bit width
configuration. Bytes with odd number (1,3,5, \... ,511) shall be sampled
on the rising edge of the clock by the host and bytes with even number
(2,4,6, \... ,512) shall be sampled on the falling edge of the clock by
the host. The device will append two CRC16 per each valid data line, one
corresponding to the bits of the 256 odd bytes to be sampled on the
rising edge of the clock by the host and the second for the remaining
bits of the 256 even bytes of the block to be sampled on the falling
edge of the clock by the host. All timings on DAT lines shall follow DDR
timing mode. The start bit, the end bit and Boot acknowledge bits are
only valid on the rising edge of the clock. The value of the falling
edge is not guaranteed. The master can terminate boot mode with the CMD
line HIGH. If the master pulls the CMD line HIGH in the middle of data
transfer, the slave has to terminate the data transfer or acknowledge
pattern within NST clock cycles (one data cycle and end bit cycle). If
the master terminates boot mode between consecutive blocks, the slave
must release the data line(s) within NST clock cycles.

Boot operation will be terminated when all contents of the enabled boot
data are sent to the master. After boot operation is executed, the slave
shall be ready for CMD1 operation and the master needs to start a normal
MMC initialization sequence by sending CMD1. Please find the boot
sequence in which will be operated by the eMMC driver in the hindsight
for initialization and then for the operation of the eMMC memory.

::: center
![EMMC IP Boot up sequence](images/BootUpSeq.png){#BootUpSeq
width="\\textwidth"}
:::

# Gigabit Ethernet

1G/10G Ethernet IP contains PCS, PMA, Phy management and reset
controller.

Transceiver: Combination tx/rx used when sending high-speed digital
data/control signals acreoss physical Medium. Used in PHY layer of OSI
model. Made up of the physical coding sublayer (PCS) and physical medium
attachment (PMA).

PCS: Digital logic that prepares and formats data for TX across a
physical medium type or restores RX data to original form. Ex. Encoding,
decoding, scrambling, descrambling.

PMA: Converts digital data to serial analog streams or reverse.

**Data link Layer** Concerned with packaging data into frames and
transmitting those frames on the network, performing error
detection/correction and uniquely identifying network devices with an
address(MAC) and flow control

MAC (Media Access Control):

-   Physical addressing: 48 bit address assigned to a device's network
    interface card (NIC)

-   Logical topology: Logical network topologies

-   Method of transmitting: CSMA/CD

LLC (Link Layer Control):

-   Connection services: provides for acknowledgement of receipt of a
    message.

    -   Flow control: Limits amount of data sender can send at one time

    -   Error Control: Allows rx to let tx know when an expected data
        frame wasn't received or was corrupted by using a checksum.

-   Synchronizing transmissions

## 1G/2.5G Ethernet IP

In computer networking, Gigabit Ethernet (GbE or 1 GigE) is the term
applied to transmitting Ethernet frames at a rate of a gigabit per
second (1 billion bits per second) and is defined by the IEEE 802.3ab
standard. There are five physical layer standards for Gigabit Ethernet
using optical fiber (1000BASEX), twisted pair cable (1000BASET), or
shielded balanced copper cable (1000BASECX). The IEEE 802.3z standard
includes 1000BASESX for transmission over multimode fiber, 1000BASELX
for transmission over singlemode fiber, and the nearly obsolete
1000BASECX for transmission over shielded balanced copper cabling. These
standards use 8b/10b encoding, which inflates the line rate by 25%, from
1000 Mbit/s to 1250 Mbit/s, to ensure a DC balanced signal. The symbols
are then sent using NRZ. Optical fiber transceivers are most often
implemented as userswappable modules in SFP form or GBIC on older
devices. IEEE 802.3ab, which defines the widely used 1000BASET interface
type, uses a different encoding scheme in order to keep the symbol rate
as low as possible, allowing transmission over twisted pair.

::: center
![Internal block diagram of 1G/2.5G Ethernet Subsystem
IP](images/1G.png){#1G width="\\textwidth"}
:::

The AXI Ethernet Subsystem provides a control interface to internal
registers via a 32bit AXI4Lite Interface subset. This AXI4Lite slave
interface supports single beat read and write data transfers (no burst
transfers). The transmit and receive data interface is via the
AXI4Stream interface. This core has been designed incorporating the
applicable features described in IEEE Std. 802.3. This core supports the
use of MII, GMII, SGMII, RGMII, and 1000BASEX interfaces to connect a
media access control (MAC) to a physicalside interface (PHY) chip. The
internals of 1G/2.5G Ethernet Subsystem IP is shown in .

The subsystem provides an AXI4Lite bus interface for a simple connection
to the processor core to allow access to the registers. This AXI4Lite
slave interface supports single beat read and write data transfers (no
burst transfers). 32bit AXI4Stream buses are provided for moving
transmit and receive Ethernet data to and from the subsystem. These
buses are designed to be used with an AXI Direct Memory Access (DMA) IP
core, AXI4Stream Data FIFO, or any other custom logic in any supported
device. The AXI4Stream buses are designed to provide support for TCP/UDP
partial or full checksum offload in hardware if required. The PHY side
of the subsystem is connected to an offtheshelf Ethernet PHY device,
which performs the BASET standard at 1 Gb/s, 100 Mb/s, and 10 Mb/s
speeds. The PHY device can be connected using any of the following
supported interfaces: GMII/MII, RGMII, or, by using the 1G/2.5G Ethernet
PCS/PMA or SGMII module.

## 10G/25G Ethernet IP

::: center
![Internal block diagram of 10G/25G Ethernet Subsystem
IP](images/10G.png){#10G width="\\textwidth"}
:::

The Xilinx LogiCORE IP 10G/25G Ethernet solution provides a 10 Gigabit
or 25 Gigabit per second (Gbps) Ethernet Media Access Controller
integrated with a PCS/PMA in BASER/KR modes or a standalone PCS/PMA in
BASER/KR modes. The core is designed to work with the latest Xilinx
UltraScale and UltraScale+ FPGAs. The 25G Ethernet IP is designed to the
new 25 Gb/s Ethernet Consortium standard and supports the demand of
cloud data centers to enable lower cost and increased performance
solutions between the server and the top of rack switch and to increase
the front panel density by two. The internals of 10G/25G Ethernet
Subsystem IP is shown in .

# Direct Memory Access
