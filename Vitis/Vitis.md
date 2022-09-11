Vitis Unified Software Platform

# Vitis Unified Software Platform Overview

The Vitis unified software platform is a tool that combines all aspects
of Xilinx software development into one unified environment. The Vitis
unified software platform enables the development of embedded software
and accelerated applications on heterogeneous Xilinx platforms including
FPGAs, SoCs, and Versal ACAPs. It provides a unified programming model
for accelerating Edge, Cloud, and Hybrid computing applications.

Leverage integration with high-level frameworks, develop in C, C++, or
Python using accelerated libraries or use RTL-based accelerators &
low-level runtime APIs for more fine-grained control over
implementation.

The Vitis unified software platform includes:

-   Comprehensive core development kit to seamlessly build accelerated
    applications

-   Rich set of hardware-accelerated open-source libraries optimized for
    Xilinx FPGA and Versal ACAP hardware platforms

-   Plug-in domain-specific development environments enabling
    development directly in familiar, higher-level frameworks

-   Growing ecosystem of hardware-accelerated partner libraries and
    pre-built applications

-   Vitis Model Composer, a Model-Based Design tool that enables rapid
    design exploration and verification within the MathWorks MATLAB and
    Simulink environment and accelerates the path to production on
    Xilinx devices.

-   Vitis Networking P4 allows for the creation of soft-defined
    networks. VitisNetP4 data plane builder generates systems that can
    be programmed for a wide range of packet processing functions from
    simple packet classification to complex packet editing.


![Vitis Unified Software Platform
Overview](images/overview.jpg){#VitisOverview width="\\textwidth"}


Vitis Unified Software Platform documentation is divided into the
following:

1.  Accelerated application development (UG1393)

2.  Embedded software development (UG1400)

3.  Vitis HLS (UG1399)

4.  AI Engine (UG1076), AI Engine Kernel Coding Best Practices (UG1079)

Key Components of the Vitis Unified Software Platform are as follows:

## Vitis AI Development Environment

The Vitis AI development environment is a specialized development
environment for accelerating AI inference on Xilinx embedded platforms,
Alveo accelerator cards, or on the FPGA-instances in the cloud. Vitis AI
development environment supports the industry's leading deep learning
frameworks like Tensorflow and Caffe, and offers comprehensive APIs to
prune, quantize, optimize, and compile your trained networks to achieve
the highest AI inference performance for your deployed application.

## Vitis Accelerated Libraries

Open-source, performance-optimized libraries that offer out-of-the-box
acceleration with minimal to zero-code changes to your existing
applications, written in C, C++ or Python. Leverage the domain-specific
accelerated libraries as-is, modify to suit your requirements or use as
algorithmic building blocks in your custom accelerators.

## Vitis Core Development Kit

Complete set of graphical and command-line developer tools that include
the Vitis compilers, analyzers and debuggers to build, analyze
performance bottlenecks and debug accelerated algorithms, developed in
C, C++ or OpenCL. Leverage these features within your own IDEs or use
the standalone Vitis IDE.

## Xilinx Runtime library

Xilinx Runtime library (XRT) facilitates communication between your
application code (running on an embedded ARM or x86 Host) and the
accelerators deployed on the reconfigurable portion of PCIe based Xilinx
accelerator cards, MPSoC based embedded platforms or ACAPs. It includes
user-space libraries and APIs, kernel drivers, board utilities, and
firmware.

## Vitis Target Platforms

The Vitis target platform defines base hardware and software
architecture and application context for Xilinx platforms, including
external memory interfaces, custom input/output interfaces and software
runtime.

-   For Xilinx accelerator cards on-premise or in the cloud, the Vitis
    target platform automatically configures the PCIe interfaces that
    connect and manage communication between your FPGA accelerators and
    x86 Application code you dont need to implement any connection
    details!

-   For Xilinx embedded devices, the Vitis target platform also includes
    the operating system for the processor on the platform, boot loader
    and drivers for platform peripherals, and root file system. You can
    use predefined Vitis target platforms for Xilinx evaluation boards
    or define your own in Vivado Design Suite.

## Vitis Model Composer

The Vitis Model Composer is a Xilinx toolbox for MATLAB and Simulink
enabling rapid design exploration and verification within the MATLAB and
Simulink environment and accelerates the path to production on Xilinx
devices.

-   Create a design using optimized blocks targeting AI Engines and
    Programmable Logic. Visualize and analyze simulation results and
    compare the output to golden references generated using MATLAB and
    Simulink.

-   Seamlessly co-simulation AI Engine and Programmable Logic (HLS, HDL)
    blocks.

-   Automatically generate code (AI Engines dataflow graph, RTL, HLS
    C++) and test bench for a design.

-   Validate your design in Hardware with unparalleled Ease of Use.

# Vitis Application Acceleration Development

# Vitis Tutorials

# Vitis Accelerated Libraries

# References

-   [Vitis Tutorials](https://github.com/Xilinx/Vitis-Tutorials/)

-   [Vitis - Hardware Acceleration Tutorials](https://github.com/Xilinx/Vitis-Tutorials/tree/2021.1/Hardware_Acceleration)

-   [Vitis Accel Examples Repository](https://github.com/Xilinx/Vitis_Accel_Examples)

-   [Vitis Unified Software Platform Documentation (UG1393)](https://www.xilinx.com/support/documentation/sw_manuals/xilinx2020_2/ug1393-vitis-application-acceleration.pdf)

-   [Vitis Vision Library User Guide](https://xilinx.github.io/Vitis_Libraries/vision/2021.2/overview.html#)

-   [Vitis Vision Library](https://github.com/Xilinx/Vitis_Libraries/tree/master/vision)

-   [XRT architecture documentation](https://xilinx.github.io/XRT/)
