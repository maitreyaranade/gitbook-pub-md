# AXI

## Protocol Overview

Xilinx adopted the Advanced eXtensible Interface (AXI) protocol for
Intellectual Property (IP)

There are three types of AXI4 interfaces:

1.  AXI4: For high-performance memory-mapped requirements

2.  AXI4-Lite: For simple, low-throughput memory-mapped communication
    (for example, to and from control and status registers)

3.  AXI4-Stream: For high-speed streaming data.

### Summary of AXI4 Benefits

1.  Productivity: By standardizing on the AXI interface, developers need
    to learn only a single protocol for IP.

2.  Flexibility: Providing the right protocol for the application:

    1.  AXI4 is for memory-mapped interfaces and allows high throughput
        bursts of up to 256 data transfer cycles with just a single
        address phase.

    2.  AXI4-Lite is a light-weight, single transaction memory-mapped
        interface. It has a small logic footprint and is a simple
        interface to work with both in design and usage.

    3.  AXI4-Stream removes the requirement for an address phase
        altogether and allows unlimited data burst size. AXI4-Stream
        interfaces and transfers do not have address phases and are
        therefore not considered to be memory-mapped.

3.  Availability: By moving to an industry-standard, you have access not
    only to the Vivado IP Catalog, but also to a worldwide community of
    ARM partners.

    1.  Many IP providers support the AXI protocol.

    2.  A robust collection of third-party AXI tool vendors is available
        that provide many verification, system development, and
        performance characterization tools. As you begin developing
        higher performance AXI-based systems, the availability of these
        tools is essential.

### How AXI Works

1.  The AXI specifications describe an interface between a single AXI
    master and AXI slave, representing IP cores that exchange
    information with each other. Multiple memory-mapped AXI masters and
    slaves can be connected together using AXI infrastructure IP blocks

2.  Both AXI4 and AXI4-Lite interfaces consist of five different
    channels:

    1.  Read Address Channel

    2.  Write Address Channel

    3.  Read Data Channel

    4.  Write Data Channel

    5.  Write Response Channel

3.  Data can move in both directions between the master and slave
    simultaneously, and data transfer sizes can vary. The limit in AXI4
    is a burst transaction of up to 256 data transfers (Requires a
    single address and then bursts up to 256 words of data). AXI4-Lite
    allows only one data transfer per transaction.

4.  AXI4 Read Transaction:

    
    ![AXI4 Read Transaction](images/AXIREAD.png){#AXIREAD width="4in"}
    

5.  AXI4 Write Transaction:

    
    ![AXI4 Write Transaction](images/AXIWRITE.png){#AXIWRITE
    width="4in"}
    

6.  At a hardware level, AXI4 allows systems to be built with a
    different clock for each AXI master-slave pair. In addition, the
    AXI4 protocol allows the insertion of register slices (often called
    pipeline stages) to aid in timing closure.

7.  AXI4-Lite is similar to AXI4 with some exceptions: The most notable
    exception is that bursting is not supported.

8.  The AXI4-Stream protocol defines a single channel for transmission
    of streaming data. The AXI4-Stream channel models the write data
    channel of AXI4. Unlike AXI4, AXI4-Stream interfaces can burst an
    unlimited amount of data.
