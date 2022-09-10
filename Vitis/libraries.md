Vitis Unified Software Platform includes an extensive set of
open-source, performance-optimized libraries that offer out-of-the-box
acceleration with minimal to zero-code changes to the existing
applications.

-   Xilinx offers the following Vitis accelerated-libraries:

    -   **Common Vitis accelerated-libraries** for Math, Statistics,
        Linear Algebra, and DSP offer a set of core functionality for a
        wide range of diverse applications.

    -   **Domain-specific Vitis accelerated libraries** offer
        out-of-the-box acceleration for workloads like Vision and Image
        Processing, Quantitative Finance, Database, and Data Analytics,
        Data Compression etc.

    -   Leverage the rich growing ecosystem of **partner-accelerated
        libraries**, framework plug-ins, and accelerated applications to
        hit the ground running and accelerate your path to production.

-   Vitis accelerated-libraries can be **used in commonly-used
    programming languages** like C, C++, and Python.

-   Vitis accelerated-libraries are accessible to all developers through
    GitHub and scalable across all Xilinx platforms and hence are
    **scalable and flexible.**

# Vitis Vision Library

The Vitis Vision library is a set of 90+ kernels, optimized for Xilinx
FPGAs, AI Engine, and SoCs, based on the OpenCV computer vision library.
The kernels in the Vitis Vision library are optimized and supported in
the Xilinx Vitis Tool Suite. The library provides a software interface
for computer vision functions accelerated on FPGA and AI Engine devices.

## Overview

The Vitis vision library has been designed to work in the Vitis
development environment, and provides a software interface for computer
vision functions accelerated on an FPGA device. Vitis vision library
functions are mostly similar in functionality to their OpenCV
equivalent.

### Basic Features

All Vitis vision library functions follow a common format. The following
properties hold true for all the functions.

-   All the functions are designed as templates and all arguments that
    are images, must be provided as xf::cv::Mat.

-   All functions are defined in the xf::cv namespace.

-   Some of the major template arguments are:

    -   Maximum size of the image to be processed

    -   Datatype defining the properties of each pixel

    -   Number of pixels to be processed per clock cycle

    -   Other compile-time arguments relevant to the functionality.

### Vitis Vision Library Contents

The following table lists the contents of the Vitis vision library.

[]{#id20 label="id20"}

## Getting Started with Vitis Vision

Describes the methodology to create a kernel, corresponding host code
and a suitable makefile to compile a Vitis Vision kernel for any of the
supported platforms in Vitis.

### Vitis Design Methodology

There are three critical components in making a kernel work on a
platform using Vitis:

-   Host code with OpenCL constructs

-   Wrappers around HLS Kernel(s)

-   Makefile to compile the kernel for emulation or running on hardware.

#### Host Code with OpenCL

Host code is compiled for the host machine that runs on the host and
provides the data and control signals to the attached hardware with the
FPGA. The host code is written using OpenCL constructs and provides
capabilities for setting up, and running a kernel on the FPGA. The
following functions are executed using the host code:

-   Loading the kernel binary on the FPGA - xcl::import_binary_file()
    loads the bitstream and programs the FPGA to enable required
    processing of data.

-   Setting up memory buffers for data transfer - Data needs to be sent
    and read from the DDR memory on the hardware. cl::Buffers are
    created to allocate required memory for transferring data to and
    from the hardware.

-   Transfer data to and from the hardware - enqueueWriteBuffer() and
    enqueueReadBuffer() are used to transfer the data to and from the
    hardware at the required time.

-   Execute kernel on the FPGA - There are functions to execute kernels
    on the FPGA. There can be single kernel execution or multiple kernel
    execution that could be asynchronous or synchronous with each other.
    Commonly used command is enqueueTask().

-   Profiling the performance of kernel execution - The host code in
    OpenCL also enables measurement of the execution time of a kernel on
    the FPGA. The function used in our examples for profiling is
    getProfilingInfo().

#### Wrappers around HLS Kernel(s)

All Vitis Vision kernels are provided with C++ function templates
(located at \<Github repo\>/include) with image containers as objects of
xf::cv::Mat class. In addition, these kernels will work either in stream
based (where complete image is read continuously) or memory mapped
(where image data access is in blocks).

Vitis flow (OpenCL) requires kernel interfaces to be memory pointers
with width in power(s) of 2. So glue logic is required for converting
memory pointers to xf::cv::Mat class data type and vice-versa when
interacting with Vitis Vision kernel(s). Wrapper(s) are build over the
kernel(s) with this glue logic.

**Stream Based Kernels** To facilitate the conversion of pointer to
xf::Mat and vice versa, two adapter functions are included as part of
Vitis Vision xf::cv::Array2xfMat() and xf::cv::xfMat2Array(). It is
necessary for the xf::Mat objects to be invoked as streams using HLS
pragma with a minimum depth of 2.

-   Array2xfMat function converts the input array to xf::cv::Mat.

-   xfMat2Array function converts the input xf::cv::Mat to output array.

-   There are two utility functions available in Vitis Vision,
    axiStrm2xfMat and xfMat2axiStrm to support streaming of data between
    two kernels.

-   axiStrm2xfMat is used by consumer kernel to support streaming data
    transfer between two kernels.

-   xfMat2axiStrm is used by producer kernel to support streaming data
    transfer between two kernels.

**Memory Mapped Kernels** In the memory map based kernels such as crop,
Mean-shift tracking and bounding box, the input read will be for
particular block of memory based on the requirement for the algorithm.
The streaming interfaces will require the image to be read in raster
scan manner, which is not the case for the memory mapped kernels.

### Evaluating the Functionality

One can build the kernels and test the functionality through software
emulation, hardware emulation, and running directly on a supported
hardware with the FPGA.

-   **Software emulation** is equivalent to running a C-simulation of
    the kernel. The time for compilation is minimal, and is therefore
    recommended to be the first step in testing the kernel.

-   **Hardware emulation** runs the test on the generated RTL after
    synthesis of the C/C++ code. The simulation, since being done on RTL
    requires longer to complete when compared to software emulation.

-   **Testing on the Hardware:** To test on the hardware, the kernel
    must be compiled into a bitstream (building for hardware). This
    would consume some time since the C/C++ code must be converted to
    RTL, run through synthesis and implementation process before a
    bitstream is created.
