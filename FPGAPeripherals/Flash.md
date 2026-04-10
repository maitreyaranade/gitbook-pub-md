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
