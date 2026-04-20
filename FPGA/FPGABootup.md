# FPGA Bootup Sequence

- FPGA bootup is the process from **power-on to functional operation** where the device is configured and starts executing logic or software.  
- The sequence differs for:
  - **Pure FPGA (SRAM-based devices)**  
  - **Non-volatile FPGA / CPLD-like devices**  
  - **SoC FPGA (with processors and OS boot)**  
- Control transitions from **hardware initialization to configuration logic, then to FPGA fabric or processor software**.  

## 1. Generic FPGA Boot Sequence (SRAM-Based)

### Step 1: Power-On Reset and Physical Initialization
- Power rails stabilize and internal reset circuits hold the device in reset.  
- Voltage monitors and power sequencing logic ensure correct startup conditions.  
- Internal configuration controller is activated.  

### Step 2: Configuration Mode Selection
- Boot mode pins or configuration settings determine the configuration source.  
- Possible sources include JTAG, SPI flash, parallel flash, or SD card.  

### Step 3: Configuration Controller Activation
- Internal configuration logic reads bitstream from selected source.  
- Timing controller manages data transfer and synchronization.  
- Error checking such as CRC validation is performed.  

### Step 4: Bitstream Loading
- Configuration data is loaded into SRAM cells controlling LUTs, routing, and I/O.  
- Physical resources such as CLBs, BRAM, DSP, and interconnect are configured.  

### Step 5: Initialization Phase
- Internal registers and memory elements are initialized.  
- I/O pins transition from high-impedance to configured states.  
- Global reset signals are released.  

### Step 6: User Mode Entry
- FPGA enters user mode and begins executing programmed logic.  
- Clock networks become active.  
- Control shifts from configuration logic to user design.  

## 2. Non-Volatile FPGA / CPLD Boot
- Configuration is stored internally in non-volatile memory.  
- No external bitstream loading is required.  
- Device becomes operational immediately after power stabilization.  
- Faster startup and lower complexity compared to SRAM-based FPGAs.  

## 3. SoC FPGA Boot Sequence (Detailed)

### Step 1: Power-On and Reset
- Power rails stabilize and reset logic initializes both processor and FPGA fabric.  
- Boot ROM inside processor becomes active.  

### Step 2: Boot ROM Execution
- Embedded processor executes Boot ROM code.  
- Determines boot source such as QSPI, SD card, NAND, or JTAG.  
- Initializes minimal hardware such as clocks and memory interfaces.  

### Step 3: FSBL (First Stage Boot Loader)
- FSBL is loaded into on-chip memory and executed.  
- Initializes critical subsystems such as DDR memory and peripherals.  
- Configures FPGA fabric by loading bitstream if required.  
- Sets up system for next boot stage.  

### Step 4: FPGA Configuration (PL Initialization)
- Bitstream is loaded into programmable logic.  
- Hardware accelerators and custom logic become available.  
- Physical IP blocks and hard IP cores are configured.  

### Step 5: U-Boot or Second Stage Boot Loader
- U-Boot initializes higher-level system components.  
- Loads operating system image from storage.  
- Sets up environment variables and boot parameters.  

### Step 6: Operating System Boot
- OS such as Linux is loaded into memory and executed.  
- Device drivers initialize peripherals and FPGA interfaces.  
- System transitions to application-level execution.  

### Step 7: Runtime Operation
- Processor runs software and manages system control.  
- FPGA fabric performs hardware acceleration.  
- Control is shared between software and hardware.  

## Control Transition Summary

| Stage | Control Owner |
|------|--------------|
| Power-On Reset | Hardware reset and configuration logic |
| Configuration Phase | FPGA configuration controller |
| User Mode (FPGA) | FPGA logic |
| Boot ROM (SoC) | Processor Boot ROM |
| FSBL Stage | Processor (low-level software) |
| U-Boot Stage | Processor (bootloader) |
| OS Stage | Operating system |
| Runtime | Processor and FPGA jointly |

## Xilinx vs Intel FPGA Boot Comparison

| Aspect | Xilinx FPGA | Intel FPGA |
|-------|-------------|------------|
| **Configuration Type** | SRAM-based | SRAM-based (most families) |
| **Configuration Controller** | Internal configuration logic | Internal configuration logic |
| **Bitstream File** | .bit | .sof / .pof |
| **Boot Sources** | JTAG, QSPI, SD, flash | JTAG, QSPI, flash, SD |
| **Startup Sequence** | Standard configuration then user mode | Similar configuration then user mode |
| **Non-Volatile Options** | Limited (external flash) | Some families support non-volatile |
| **Initialization Control** | Startup sequencer with defined phases | Similar initialization control |

## Xilinx vs Intel SoC Boot Comparison

| Stage | Xilinx SoC (Zynq) | Intel SoC FPGA |
|------|------------------|----------------|
| **Boot Start** | Boot ROM in processor | Boot ROM in processor |
| **First Stage Loader** | FSBL | Preloader |
| **FPGA Configuration** | Done during FSBL or later | Done during preloader or later |
| **Second Stage Loader** | U-Boot | U-Boot |
| **OS Boot** | Linux or RTOS | Linux or RTOS |
| **Interconnect** | AXI-based | AXI/Avalon-based |
| **Control Flow** | PS initializes PL | HPS initializes FPGA |

## Important Components in Boot Flow
- **Configuration Controller** manages FPGA bitstream loading.  
- **Timing Controller** ensures correct sequencing of configuration signals.  
- **Hard IP Blocks** such as DDR and transceivers are initialized early.  
- **Bootloaders (FSBL / Preloader / U-Boot)** manage system startup.  
- **Clock and Reset Systems** ensure stable operation.  

---