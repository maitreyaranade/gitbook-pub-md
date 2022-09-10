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
