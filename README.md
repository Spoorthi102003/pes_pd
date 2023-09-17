![image](https://github.com/VardhanSuroshi/pes_asic_class/assets/132068498/33403244-c9dd-4aef-a022-da52e2eef51c)
# ADVANCED PHYSICAL DESIGN USING OPENLANE/SKY130
<details>
<summary>DAY1</summary>
  
## Inception of open-source EDA, OpenLANE and Sky130 PDK
* How to talk to computers??

An Arduino board is a popular open-source electronics platform that consists of a microcontroller and, a development environment. It is a small computer chip that processes instructions and controls the behavior of your electronic project.
Arduino boards work by providing a platform for you to write and upload code that controls the behavior of the microcontroller on the board.

![image1](https://github.com/Spoorthi102003/pes_pd/assets/143829280/82a03804-6217-4eda-82a7-367467fefcc9)

The board is in the form of a block diagram.

![266850462-9a3fb263-e0bd-4a43-96c4-6cf5bfe105e8](https://github.com/Spoorthi102003/pes_pd/assets/143829280/7a2d7b6d-00b0-49b4-aef1-2608f7afb88a)

The IC looks like this

![266850906-4eb85a39-26e1-4977-b477-e1954dbf552a](https://github.com/Spoorthi102003/pes_pd/assets/143829280/a83ed91b-c8d0-4a33-b21b-ac699cc131f8)

The main chip is located at the center of the package and is connected to the pins by wire bounds. These wire bounds transfer all the incoming signals to the chip.
![image](https://github.com/Spoorthi102003/pes_pd/assets/143829280/bcaa7ffb-1944-47e9-9eb5-eccaddf9c730)

PADs in a chip are like the metal points on the bottom of the chip that are used to connect the chip to a circuit through which a signal can be sent into the chip. The core of a chip is the central part that processes the information. It's a place where all our Digital logic sits like the AND gate, OR gate, MUXs, etc. A die is a tiny, flat piece of silicon that contains the actual electronic circuits and defines the size of the chip. The Die is manufactured on a Silicon wafer.This the Die that gets manufactured on the "Silicon Wafer".
The typical Core of a CHIP consists of an SoC(we will be working with RISC-V SoC),SRAM,ADCs,DACs,PLL,SPI and couple of components shown below:
![image](https://github.com/Spoorthi102003/pes_pd/assets/143829280/1caca3ac-e58f-438f-b571-698ee104fa01)

# Introduction to RISC-V
# ISA (Instruction Set Archhitecture)
  ISA defines the interface between a computer's hardware and its software, specifically how the processor and its components interact with the software instructions that drive the execution of tasks.
 It encompasses a set of instructions, addressing modes, data types, registers, memory organization, and the mechanisms for executing and managing instructions.

- **RISC-V (Reduced Instruction Set Computing - Five)**.
  - It is an open-source Instruction Set Architecture (ISA) that has gained significant attention and adoption in the world of computer architecture and semiconductor design.
  - RISC architectures simplify the instruction set by focusing on a smaller set of instructions, each of which can be executed in a single clock cycle. This approach usually leads to faster execution of individual instructions. 

<img width="536" alt="image" src="https://github.com/Veda1809/pes_asic_class/assets/142098395/4eabe0b7-4581-419b-88e7-84c7ac1dac8e">

## From Apps to Hardware
1. **Apps:** Application software, often referred to simply as "applications" or "apps," is a type of computer software that is designed to perform specific tasks or functions for end-users.
2. **System software:** System software refers to a category of computer software that acts as an intermediary between the hardware components of a computer system and the user-facing application software. It provides essential services, manages hardware resources, and enables the execution of application programs. System software plays a critical role in maintaining the overall functionality, security, and performance of a computer system.'
3. **Operating System:** The operating system is a fundamental piece of software that manages hardware resources and provides various services for both users and application programs. It controls tasks such as memory management, process scheduling, file system management, and user interface interaction. Examples of operating systems include Microsoft Windows, macOS, Linux, and Android.

4. **Compiler:** A compiler is a type of software tool that translates high-level programming code written by developers into assembly-level language.

5. **Assembler:** An assembler is a software tool that translates assembly language code into machine code or binary code that can be directly executed by a computer's processor.

6. **RTL:** RTL serves as an abstraction level in the design process that represents the behavior of a digital circuit in terms of registers and the operations that transfer data between them.

 7. **Hardware:** Hardware refers to the physical components of a computer system or any electronic device. It encompasses all the tangible parts that make up a computing or electronic device and enable it to perform various tasks.

## Detail Description of Course Content
**Pseudo Instructions:** Pseudo-instructions are used to simplify programming, improve code readability, and reduce the number of explicit instructions a programmer needs to write. They are especially useful for common programming patterns that involve multiple instructions.
`Ex: li, mv`.

**Base Integer Instructions:** The term "base integer instructions" refers to the fundamental set of instructions that form the foundation for performing basic arithmetic, logical, and data movement operations.
`Ex: add, sub, and, or, xor, sll`.

**Multiply Extension Intructions:** The RISC-V architecture includes a set of multiply and multiply-accumulate (MAC) extension instructions that enhance the instruction set to perform efficient multiplication and multiplication-accumulate operations.
`Ex: mul, mulh, mulhu, mulhsu`.

**Single and Double Precision Floating Point Extension:** The RISC-V architecture includes floating-point extensions that provide support for both single-precision (32-bit) and double-precision (64-bit) floating-point arithmetic operations. These extensions are often referred to as the "F" and "D" extensions, respectively. Floating-point arithmetic is essential for handling real numbers with fractional parts and for performing accurate calculations involving decimal values.

**Application Binary Interface:** ABI stands for "Application Binary Interface." It is a set of rules and conventions that govern how software components interact with each other at the binary level. The ABI defines various aspects of program execution, including how function calls are made, how parameters are passed and returned, how memory is allocated and managed, and more.

**Memory Allocation and Stack Pointer** 
- Memory allocation refers to the process of assigning and managing memory segments for various data structures, variables, and objects used by a program. It involves allocating memory space from the system's memory pool and releasing it when it is no longer needed to prevent memory leaks.
- The stack pointer is a register used by a program to keep track of the current position of the program's execution on the call stack. 

![image](https://github.com/Spoorthi102003/pes_pd/assets/143829280/b5132a62-4171-4c63-8a43-82b858622fad)
RISC-V execution for stop watch application:
![image](https://github.com/Spoorthi102003/pes_pd/assets/143829280/f6cfd7f0-366c-4225-a220-8f1279982649)

# RTL
RTL stands for Register-Transfer Level. It's a level of abstraction used in digital circuit design and describes how data moves between registers and how operations are performed on that data.In RTL design, the behavior of the digital system is defined by describing how data is transferred between registers and how operations are performed on that data. This is typically done using a hardware description language (HDL) like Verilog or VHDL.

![image](https://github.com/Spoorthi102003/pes_pd/assets/143829280/73d6b827-e227-42d4-beec-4e4ed7c6527b)


# SOC and Openlane
![image](https://github.com/Spoorthi102003/pes_pd/assets/143829280/f3dad6fe-e1af-4dd5-a4c2-b9e9e0f577ba)

* PDK
PDK (Process Design Kit) is a set of files provided by semiconductor manufacturers to help designers use their fabrication process to create integrated circuits (ICs). It contains a comprehensive set of information, models, and files that enable designers to develop and verify their designs using the specific process technology offered by the manufacturer.
Device Models: These are mathematical representations of transistors, diodes, resistors, capacitors, and other electronic components that are used in integrated circuits. Device models describe the behavior of these components under different operating conditions.

**Process Design Rules (PDRs)**: PDRs are a set of guidelines and constraints that dictate how certain components should be designed to ensure compatibility with the manufacturing process. They specify minimum feature sizes, spacing rules, and other design constraints.

**Simulation and Modeling Tools**: PDKs often include software tools for simulating and modeling the behavior of integrated circuits. These tools allow designers to predict how a circuit will perform before it is manufactured.

**Layout and Mask Design Tools**: These tools are used to create the physical layout of the integrated circuit, including the placement of components and the routing of interconnects. They ensure that the design adheres to the PDRs.

**Calibration Data**: PDKs may include data and calibration files that are used to fine-tune the simulation models to match the actual behavior of the manufacturing process. This helps ensure that the designs are accurate and manufacturable.

**Libraries of Standard Cells**: Standard cells are pre-designed and pre-characterized functional blocks, such as logic gates and flip-flops, that can be used as building blocks for designing custom integrated circuits. PDKs often include libraries of these standard cells.

**Technology Files**: These files contain information about the manufacturing process itself, including details about the materials, layer structures, and fabrication steps used in the semiconductor manufacturing process.

**Design Rule Checker (DRC) and Layout Versus Schematic (LVS) Tools**: These tools are used to check the design against the PDRs to ensure that it meets the manufacturing constraints and is free of errors.

**Documentation**: PDKs typically include extensive documentation that explains how to use the tools, libraries, and data effectively. This documentation is crucial for designers to understand and work with the PDK.

**Design Examples and Testbenches**: PDKs may include sample designs and testbenches to help designers get started and test their designs against known benchmarks.

**Support and Training**: Some PDK providers offer support and training to assist designers in using the PDK effectively.

# The RTL2GDS flow:
![image](https://github.com/Spoorthi102003/pes_pd/assets/143829280/85be2520-c6c4-41c5-8d87-eac3b1c3a314)

![Screenshot 2023-09-16 204356](https://github.com/Spoorthi102003/pes_pd/assets/143829280/697c0153-9bef-4d39-b1a2-d2e7d8091849)

* **Synthesis**: is the process of converting the RTL description of a digital design into a gate-level netlist. This netlist consists of logical elements (gates) and their interconnections.
* **Floor planning**: Floor/Power Planning: In this phase, the chip's overall floor plan is defined. It determines the approximate locations of key components, such as blocks and macros, and how power is distributed across the chip.

  Macro Floor Planning - We define the macro dimensions, pin locations, and rows are defined.

  Chip Floor Planning - Partition the chip die between different system building blocks and place the I/O pads.
* **Power planning**: In power planning the power Network is constructed, typically its chip is powered by multiple VDD and Ground Pins.
* **Placement**: Placement involves assigning specific locations on the chip for each gate and macro from the synthesized netlist. The goal is to optimize for various objectives, including minimizing wire length, meeting timing constraints, and managing thermal considerations.
* **Clock Tree Synthesis**: Clock tree synthesis (CTS) is a crucial step in ensuring that the clock signals reach all parts of the chip with minimal skew and jitter. It involves the generation of a hierarchical tree structure to distribute the clock signals uniformly and meet timing requirements.
* **Routing**: After placement and CTS, routing is performed to create the physical wires (metal traces) that connect all the components on the chip. This process adheres to design rules and timing constraints.
* **Signoff**: The Signoff stage encompasses a series of verification and validation steps
# Getting familiar with open-source EDA tools
**Design preparation steps**
Type the following command to open the Openlane EDA tool

`cd Desktop/work/tools/`
`cd openlane_working_dir/`
`cd openlane`
`docker`

Now the shell opens. In the shell type `./flow.tcl -interactive`

To import all packages type `package require openlane 0.9`

![Screenshot 2023-09-17 213922](https://github.com/Spoorthi102003/pes_pd/assets/143829280/a9aa9cfa-d74d-41bb-babd-3335ba2e37a0)
* After preparing the design, we can see that a new 'runs' folder is created.
* To synthesize the design we type `run_synthesis`
* After the synthesis we calculate the flop ratio as: no. of flops/number of cells
* Here we have done it for dfxtp_2 (2:1 dmux)
* Also under the runs folder we can check out the netlist file generated after synthesis.

![Screenshot 2023-09-17 225232](https://github.com/Spoorthi102003/pes_pd/assets/143829280/a96a1184-5347-4793-b79e-9e98beef5876)

![Screenshot 2023-09-17 230314](https://github.com/Spoorthi102003/pes_pd/assets/143829280/62f44d5c-a2a8-4a41-a063-860600e14698)
</details>

<details>
<summary>DAY2</summary>
  
# Chip Floor planning considerations




















