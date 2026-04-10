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
