## History of Programmable Logic

TTL(Transistor Transistor Logic) logic design

:   Implementng logic by using basic logic funtions available on
    separate chips/ ICs (ex: Texas Instruments 7400 device family) on a
    breadboard. Methodology:

    -   Creating truth table.

    -   Cration Karnaugh map.

    -   Generate logical expression.

    -   Final logic implementation.

Programamble logic

:   

    Programamble Array Logic(PAL)

    :   Simplest implementation of programmable logic. Logic gates and
        registers fixed. Programmable sum of products array and output
        control. Floating-gate transistors at array crossings set to
        never conduct after applying programming voltages.\
        Put image here

    Programamble Logic Devices (PLD)

    :   Arrange multiple PAL arrays in a single device. It is comprised
        of: i. Variable product term distribution ii. Programmable
        macrocells

        Programmable macrocells: Generated programmable output from sum
        of products. Provided feedback (using output pin as input)

Complex Programamble Logic Devices (CPLD)

:   Combine multiple PLDs(logic blocks) in a single device with
    programmable interconnect and I/O.

    Put image here:

    CPLD logic block or Logic Array Blocks(LAB):

    Contain multiple macrocells (typically 4 to 20) Local programmable
    interconnect like a PLD.

Other architectures

:   

    Programmable Interconnect Array(PI or PIA)

    :   Similar to PAL programming technology. Global routing connects
        any signal to any destination in device. Programmed wih
        EPROM,EEPROM or flash technology.

    I/O control blocks

    :   Introduction in CPLDs. Seprated from logic by PI. I/O specific
        logic provides control, more features. Tri-state buffer control
        to enable input, outputs, or bidirectional on any I/O pin.

    In-System Programming (ISP) with JTAG

    :   Simple 4 or 5 wire serial interface. Shifts data through one or
        more devices on a board (JTAG chain). Used for device self test
        or ISP. PLD Hardware generates EEPROM programming voltages
        controlled by JTAG interface.
