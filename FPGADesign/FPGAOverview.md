# FPGA Introduction and Overview

## What is an FPGA?
- FPGA stands for Field-Programmable Gate Array, which is a reconfigurable integrated circuit used to implement custom digital logic designs.  
- It consists of programmable logic blocks and programmable interconnections that can be configured to perform specific functions.  
- The functionality of an FPGA is defined by configuration data, often called a bitstream, rather than fixed hardware.  
- Unlike application-specific integrated circuits, FPGAs can be reprogrammed after manufacturing.  
- They are widely used to implement complex and high-performance digital systems.

## How an FPGA is customized (with programming)

1. **Design Entry**  
   - The system is described using a hardware description language such as Verilog or VHDL.  

2. **Synthesis and Implementation**  
   - The design is converted into a gate-level representation using synthesis tools.  
   - The design is then mapped, placed, and routed onto the FPGA resources.  

3. **Configuration**  
   - A configuration file called a bitstream is generated.  
   - This bitstream is loaded into the FPGA to define its internal hardware behavior.  

## Key Features of FPGAs
- FPGAs are reconfigurable, allowing multiple design iterations on the same hardware.  
- They support parallel processing, enabling multiple operations to execute simultaneously.  
- They allow implementation of custom hardware tailored to specific applications.  
- They provide a shorter time-to-market compared to application-specific integrated circuits.  
- They can handle designs of varying complexity, from simple logic to full systems.

## FPGA vs Microcontroller
FPGAs may sound similar to microcontrollers, but it's very important to
understand the differences. 

| Feature | FPGA | Microcontroller |
|--------|------|----------------|
| Operation | Hardware-defined functionality | Software-driven execution |
| Flexibility | Fully reconfigurable | Fixed architecture |
| Execution Model | Parallel execution | Sequential execution |
| Capability | Can implement custom logic or processors | Executes predefined instructions |
| Use Case | High-performance and custom systems | Embedded control applications |

## Programmable Logic Devices (PLDs)
Programmable Logic Devices are integrated circuits that can be configured by the user to implement custom digital logic functions.

- Unlike fixed-function ICs, PLDs allow modification of hardware behavior even after manufacturing.

- **Purpose**: Used to implement combinational and sequential logic such as decoders, counters, and state machines.

- **Advantage in Design** : Reduce the need for multiple discrete components, simplifying circuit design and improving reliability.

### Types of PLDs
- **SPLD (Simple Programmable Logic Device)** is used for basic logic functions.  
- **CPLD (Complex Programmable Logic Device)** supports moderate complexity with predictable timing.  
- **FPGA (Field-Programmable Gate Array)** supports highly complex and scalable designs. 

![PLD Classification](images/PLD.png)

- **Applications**  
  Widely used in digital systems, embedded applications, and rapid prototyping.

- FPGAs are a type of programmable logic device used for implementing digital logic.  

## CPLD vs FPGA
- CPLDs offer predictable timing and are suitable for simple control logic and glue logic applications.  
- CPLDs have limited scalability due to a smaller number of flip-flops.  
- FPGAs provide higher logic density and are suitable for complex systems such as processors and communication interfaces.  
- FPGAs offer greater flexibility due to their rich routing and architecture.  

## Application Specific Integrated Circuits (ASIC)

Application-Specific Integrated Circuits are custom-designed chips built to perform a specific function or application.

- **Key Idea**: Unlike programmable devices, ASICs have fixed functionality that cannot be changed after fabrication.

- **Purpose**: Used for high-performance and optimized implementations of specific tasks such as signal processing, networking, and consumer electronics.

- **Advantage in Design**: Provide very high performance, low power consumption, and optimized area for a given application.

- **Design Characteristics**
  - Tailored for a single application  
  - Highly optimized for speed, power, and area  
  - Requires full custom or semi-custom design flow  

- **Development Aspects**
  - High initial (non-recurring) cost  
  - Long design and fabrication cycle  
  - Cost-effective only for high-volume production  

- **Applications**  
  Used in processors, smartphones, networking chips, automotive systems, and consumer electronics.

- **Key Benefits**  
  Offer maximum efficiency and performance for specific applications, making them ideal for large-scale production.

## FPGA vs ASIC vs Microprocessor

| Feature | FPGA | ASIC | Microprocessor |
|--------|------|------|---------------|
| Reconfigurability | Reprogrammable | Fixed after fabrication | Fixed architecture |
| Performance | Moderate to high | Very high | Moderate |
| Development Cost | Low | Very high | Low |
| Unit Cost | Moderate | Low at high volume | Moderate |
| Time to Market | Short | Long | Short |
| Flexibility | High | None | Limited |

## Advantages of FPGA
- FPGAs are reprogrammable, allowing design updates without hardware changes.  
- They enable faster prototyping compared to ASIC design.  
- They have lower initial development cost.  
- They support parallel processing for high performance.  
- They are widely used for ASIC prototyping and verification.  


## Limitations of FPGA
- FPGAs consume more power compared to ASICs.  
- They offer lower performance compared to optimized ASIC designs.  
- They require more area for the same functionality.  
- They require specialized tools and design expertise.  


## Applications of FPGA
- Autonomous vehicles and advanced driver assistance systems.  
- Internet of Things and embedded systems.  
- Data centers and cloud computing acceleration.  
- Robotics and machine vision systems.  
- Communication systems including 5G networks.  
- High-resolution video processing and surveillance.  
- Medical diagnostics and bioinformatics. 

--- 

## Suggested Readings:

-   FPGAs for Dummies, Altera Version, available here: http://design.altera.com/New2FPGAeBook, Chapters 1, 2, and 5 (27 pages).

-   Rapid Prototyping of Digital Systems: SOPC Edition, by Hamblen, Hall and Furman; ISBN 9780387726700, Chapter 3 (14 pages)

-   Design Recipes for FPGAs Using Verilog and VHDL, 2nd Edition, by Peter Wilson, Chapter 2 (7 pages)

---