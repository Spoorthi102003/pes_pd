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

![Screenshot 2023-09-18 104950](https://github.com/Spoorthi102003/pes_pd/assets/143829280/e8b1fc0a-cd4a-46f5-8048-3a1ef0ea80b6)

![Screenshot 2023-09-17 225232](https://github.com/Spoorthi102003/pes_pd/assets/143829280/a96a1184-5347-4793-b79e-9e98beef5876)

![Screenshot 2023-09-17 230314](https://github.com/Spoorthi102003/pes_pd/assets/143829280/62f44d5c-a2a8-4a41-a063-860600e14698)
</details>

<details>
<summary>DAY2</summary>
  
# Chip Floor planning considerations

**Utilization Factor and Aspect Ratio**
Define Width and height of core and die: The die refers to the entire semiconductor chip, including the core, I/O pads, and any additional features.The core refers to the central area of the chip where most of the active circuitry resides. It includes components like the CPU, GPU, memory, and other logic.

**Utilization factor**=Area occupied by netlist/Area of the core

**Aspect ratio**=Height/width
* **Pre-placed cells**: Preplaced cells are a group of fixed-location standard cells that are manually placed by the chip designer in specific locations on the silicon die during the chip floor planning process. Unlike regular standard cells, which are placed automatically by Electronic Design Automation (EDA) tools, preplaced cells are positioned by the designer before automated placement and routing.
  
![image](https://github.com/Spoorthi102003/pes_pd/assets/143829280/2821dbea-1e2b-408b-9abf-5a0e2b65e126)

* **Decoupling capacitors**: A decoupling capacitor, often referred to simply as a "decap," is an essential electronic component used in electronic circuits, particularly on printed circuit boards (PCBs) and integrated circuits (ICs). Its primary purpose is to stabilize and filter the power supply voltage to ensure that sensitive components receive a stable and noise-free supply of power. Here are the key aspects of decoupling capacitors:

* **Pin Placement**:Pin placement is an essential part of floorplanning to minimize buffering and improve power consumption and timing delays we use the HDL netlist to determine where a specific pin should be placed in the circuit. We join the common pins and try to keep the connections as efficient as possible. In the pin placement step, we use the HDL netlist to determine where a specific pin should be placed in the circuit. We join the common pins and try to keep the connections as efficient as possible. Pins are placed in the Die area.
# Steps to run floorplan
Give the command `run_floorplan` after run_synthesis

![Screenshot 2023-09-18 105210](https://github.com/Spoorthi102003/pes_pd/assets/143829280/1ffd0935-dadf-4ddb-841f-7e29cbdfa2a6)

To open the Floorplan we go to the following directory:
`vsduser@vsdsquadron:~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/11-09_15-36/results/floorplan`

Then type the following command:
`magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &`

The layout looks like this:
![Screenshot 2023-09-18 004841](https://github.com/Spoorthi102003/pes_pd/assets/143829280/6242cf1b-14e4-4691-9852-b40cd2c2de12)

The zoomed-in view:
![Screenshot 2023-09-18 004906](https://github.com/Spoorthi102003/pes_pd/assets/143829280/5210b11c-409c-4bdc-ad97-8b359c0fa987)

**Library Binding and Placement**
Netlist Binding and Initial Place Design: The Library consists of cells, sizes of cells, various flavors and shapes of the cells, Timing, Power, and delay information. Now, we have the floorplan, netlist, and representation of components of netlist in the library. Place all the components such that the timing is not disturbed and distribute them properly.
![image](https://github.com/Spoorthi102003/pes_pd/assets/143829280/9f0e948c-d8c4-4931-bdfa-c74813443e20)

# Placement
* After run_floorplan, give the command `run_placement`
![Screenshot 2023-09-18 105413](https://github.com/Spoorthi102003/pes_pd/assets/143829280/68bd746d-fc98-4095-9b5f-adb54eddb58e)

* To view the placement type the command `magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def`
![Screenshot 2023-09-18 011459](https://github.com/Spoorthi102003/pes_pd/assets/143829280/24dbfecf-c9de-4889-8074-2c7c9539a9f1)

* After we zoom in we can see the placement of the standard cells in the standard cell rows.
![Screenshot 2023-09-18 011513](https://github.com/Spoorthi102003/pes_pd/assets/143829280/c8bf3138-63db-4dd1-8023-00c3ee6244f8)

# Cell Design and Characterization Flow

**Cell Design Flow**
* Inputs - PDKs (Process design kits), DRC & LVS rules, SPICE models, library & user-defined specs.
* Design Steps - The design steps of cell design involve Circuit Design, Layout Design, and Characterization. The software GUNA is used for characterization. The characterization can be classified as Timing characterization, Power characterization, and Noise characterization.
* Outputs - Outputs of the Design are CDL (Circuit Description Language), GDSII, LEF, extracted Spice netlist (.cir), timing, noise, and power.libs, function.

**Characterization**: timing, noise power.libs functions read in the models and tech files and generate extracted spice Netlist. Read the subcircuits and attach power sources. Apply stimulus to characterization setup, provide necessary output capacitance loads, and provide necessary simulation commands.

**This is for an inverter**
* Read the model files.
* Read the extracted SPICE netlist.
* Recognize the behavior of the buffer.
* Attaching the necessary power sources
* Apply the stimulus, which is the input signal to the circuit.
* Read the sub-circuit of the inverter.
* Provide necessary output capacitances.
* Provide the necessary simulation commands
  
# General Timing characterization parameters
**Timing threshold**:
* slew_low_rise_thr - 20% from bottom power supply when the signal is rising
* slew_high_rise_thr - 20% from top power supply when the signal is rising
* slew_low_fall_thr - 20% from bottom power supply when the signal is falling
* slew_high_fall_thr - 20% from top power supply when the signal is falling
* in_rise_thr - 50% point on the rising edge of input
* in_fall_thr - 50% point on the falling edge of input
* out_rise_thr - 50% point on the rising edge of ouput
* out_fall_thr - 50% point on the falling edge of ouput
  
These are the main parameters that we use to calculate factors such as propogation delay and transition time

**propogation delay**= time(out_thr) - time(in_thr)
**Transition time**= time(slew_high_rise_thr) - time(slew_low_rise_thr)
</details>

<details>
<summary>DAY3</summary>

# Inception of Layout and CMOS Fabrication Process
* Substrate Selection: In the initial phase, the appropriate semiconductor substrate is chosen.
Create an active region for transistors: to isolate the active regions for transistors SiO2 and Si3N2 deposited. Pockets were created using photoresist and lithography.
* N-well & P-well formation: P-well formation involves photolithography and ion implantation of p-type Boron material into the p-substrate. N-well is formed similarly with n-type Phosphorus material. Drive in diffusion by placing it in a high-temperature furnace.
Gate Formation.A polysilicon layer is deposited and photolithography techniques are applied to create NMOS and PMOS gates
* Lightly Doped Drain (LDD) formation: LDD is done to avoid the hot electron effect and short channel effect.
* Source & Drain Formation: Thin oxide layers are added to avoid channel effects during ion implantation.N+ and P+ implants are performed using Arsenic implantation and high-temperature annealing.
* Local Interconnect Formation: Thin screen oxide is removed through etching in HF solution. Titanium deposition through sputtering is initiated. Heat treatment results in chemical reactions, producing low-resistant titanium silicon dioxide for interconnect contacts and titanium nitride for top-level connections, enabling local communication.
* Higher Level Metal Formation: To achieve suitable metal interconnects, non-planar surface topography is addressed. Chemical Mechanical Polishing (CMP) is utilized by doping silicon oxide with Boron or Phosphorus to achieve surface planarization. TiN and blanket Tungsten layers are deposited and subjected to CMP. An aluminum (Al) layer is added and subjected to photolithography and CMP
* Dielectric Layer Addition: Finally, a dielectric layer, typically Si3N4, is applied to safeguard the chip.

![Screenshot 2023-09-18 113336](https://github.com/Spoorthi102003/pes_pd/assets/143829280/fd86cf56-7141-4c17-be50-b809f71e76b8)

# LAB
Clone the following github repo using the command
`git clone https://github.com/nickson-jose/vsdstdcelldesign.git`

Now we need to copy the 'sky130A.tech' file into the directory we just cloned
`cp sky130A.tech /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/vsdstdcelldesign`

![Screenshot 2023-09-18 112129](https://github.com/Spoorthi102003/pes_pd/assets/143829280/5ed58903-816f-48db-b31b-49b935ba6bea)

Then type the following command:
` magic -T sky130A.tech sky130_inv.mag &`
![Screenshot 2023-09-18 113116](https://github.com/Spoorthi102003/pes_pd/assets/143829280/80170082-ba02-4acc-9e4b-b35823932dfd)

We can get to know the details of the inverter by hovering the mouse cursor over it and pressing 's' on the keyboard. Then we can type what in the tkcon.

Pressing 's' three times will show what parts are connected to the selected part.

![Screenshot 2023-09-18 151332](https://github.com/Spoorthi102003/pes_pd/assets/143829280/aba69f2c-8a2d-482f-81e1-038cbffd6a4e)

**Steps to Create Standard Cell Layout and Extract Spice Netlist**

We can view the DRC error:

![Screenshot 2023-09-18 151842](https://github.com/Spoorthi102003/pes_pd/assets/143829280/9be1fcfa-d24f-477f-9481-db8cc22d3e2b)

To extract Spice Netlist we perform the following steps in the tkcon window:
* `pwd`
* `extract all`
* `ext2spice cthresh 0 rthresh 0`
* `ext2spice`

![Screenshot 2023-09-18 152243](https://github.com/Spoorthi102003/pes_pd/assets/143829280/2bd7f09f-0741-45f0-bda3-667149c8a700)

Now the files sky130_inv.ext and sky130_inv.spice are in 'vsdstdcelldesign' directory

# Sky130 PDKS and Steps to Download Magic Tool
* Type the following commands:
` wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz`
* Move the file to desktop using the following command:
`mv drc_tests.tgz Desktop/`
* Go to the Desktop directory and extract the file by `tar xfz drc_tests.tgz`
* To open the software type `magic -d XR` in the drc_tests directory

![Screenshot 2023-09-18 182314](https://github.com/Spoorthi102003/pes_pd/assets/143829280/382b856e-8515-4ce9-92ea-bdf144112935)

* Open the met3.mag file 
* If we select an area and type `drc why` in the tkcon window, it will show us the DRC error.
![Screenshot 2023-09-18 182443](https://github.com/Spoorthi102003/pes_pd/assets/143829280/768c511d-bc7a-4a94-9375-b98a3e489ee3)

* To add contact cuts to metal3, first select an area using left and right click. Then hovering over the m3contact we click middle mouse button.
* Type the command `cif see VIA2 ` in the tckon window

![Screenshot 2023-09-18 183215](https://github.com/Spoorthi102003/pes_pd/assets/143829280/45f916ab-d363-42ff-9fd9-fd25a0715884)

# Fixing DRC errors
* There is an error in poly.mag file
* In the tckon window type  `load poly`
* In the drc_tests directory open sky130A.tech file by typing the command `gedit sky130A.tech`
* Fix the following errors
![Screenshot 2023-09-18 185638](https://github.com/Spoorthi102003/pes_pd/assets/143829280/3b66a69c-3719-4f9e-a0e4-da38f2720fdf)

![Screenshot 2023-09-18 185706](https://github.com/Spoorthi102003/pes_pd/assets/143829280/c5b4f7ac-89d4-4633-a0c4-dd5358407eb8)

![image](https://github.com/Spoorthi102003/pes_pd/assets/143829280/56587be9-39c5-46ec-8d49-4eac7e0bfc87)

* Again in the tckon window type `load tech sky130A.tech` and `drc check`
* We can see that the drc error has been corrected

![Screenshot 2023-09-18 191934](https://github.com/Spoorthi102003/pes_pd/assets/143829280/84b171d5-4d3a-4020-9861-643891f9c411)

**DRC error as geometrical construct**
* Open nwell.mag file

![Screenshot 2023-09-18 204136](https://github.com/Spoorthi102003/pes_pd/assets/143829280/5f3fe5df-f0be-4b35-9fab-3d8afae5ba7d)

* Type the following command
* `cif ostyle drc`
* `cif see dnwell_shrink`
* `cif see nwell_missing`

* To find incorrect or missing rules and fix them
* Open sky130A.tech file on gedit as `gedit sky130A.tech`
* Make the following changes:
![Screenshot 2023-09-18 203456](https://github.com/Spoorthi102003/pes_pd/assets/143829280/508b3fce-66f9-4d77-a4a0-f8973bff1205)

![Screenshot 2023-09-18 203427](https://github.com/Spoorthi102003/pes_pd/assets/143829280/fb8bebe1-f587-4ded-945b-2c90743c863e)

* In the tckon window type

`tech load sky130A.tech`
`drc check`
`drc style drc(full)`
`drc check`
* As we can see the error still persists

![Screenshot 2023-09-18 202246](https://github.com/Spoorthi102003/pes_pd/assets/143829280/abf85918-733c-430a-8489-d88340c0ac00)

We can fix it by doing this:

![Screenshot 2023-09-18 204404](https://github.com/Spoorthi102003/pes_pd/assets/143829280/b9584a3c-01c7-4c57-9353-f4718dca8aec)

</details>

<details>
<summary>DAY4</summary>
  
# Timing Modelling using Delay Tables
Place and routing (PnR) is performed using an abstract view of the GDS files generated by Magic. The PnR tool will use the abstract view information, formally defined as LEF information, to perform interconnect routing. From PnR POV, We have to follow certain guidelines to get standard cell set.

Input and output ports must lie on the intersection of vertical and horizontal tracks Width of the standard cell should be odd multiples of the track pitch and height should be odd multiple of vertical track pitch

# To convert grid info to track info
Go to the following directory:
`Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/openlane/sky130fd_sc_hd`
We open the track.info file by giving the command `less tracks.info`
![Screenshot 2023-09-18 212445](https://github.com/Spoorthi102003/pes_pd/assets/143829280/6e05e8d8-8ea8-4251-80a9-24661a089f33)
The 'tracks.info' file is used during the routing stage.Routes are the metal traces.Since the PNR is an automated flow, we need to specify where we want the routes to go.
![Screenshot 2023-09-18 212653](https://github.com/Spoorthi102003/pes_pd/assets/143829280/a1f04f75-f85c-4d3c-b939-5f354670ba7a)
* Type the command  `grid 0.46um 0.34um 0.23um 0.17um` in the tckon window
* Then save the file as `save sky130_vsdinv.mag`

![Screenshot 2023-09-18 214949](https://github.com/Spoorthi102003/pes_pd/assets/143829280/37a89e54-6f88-4479-8b3c-7ae9199332fa)

* The following is the result.

![Screenshot 2023-09-18 212910](https://github.com/Spoorthi102003/pes_pd/assets/143829280/926aaae5-f751-4469-bcd2-e9f90f84afa9)

* This shows that the routing of 'li1' layer can happen only along this grid.Having the ports at the intersection of horizontal and vertical tracks ensure that the route can reach that port from the 'y' as well as 'x' direction.

![Screenshot 2023-09-18 212910](https://github.com/Spoorthi102003/pes_pd/assets/143829280/b09f049c-d78e-43f6-b6e9-6b74dfbf657b)

The next requirement is that the width of the cell should be the odd multiple of xpitch which is '0.46' as seen in the 'tracks.info' file. As we can see it encloses two full boxes and two halves of one box, totally making three boxes as indicated by the white rectangle.

**Convert Magic Layout to Standard Cell LEF**
* To make our own mag file give the command `lef write`

![Screenshot 2023-09-18 215424](https://github.com/Spoorthi102003/pes_pd/assets/143829280/96c6904a-682d-4797-8dba-6c87620231ed)

* Type `less sky130_vsdinv.lef`.

![Screenshot 2023-09-18 215456](https://github.com/Spoorthi102003/pes_pd/assets/143829280/b1d90e95-aaed-4eae-a6e9-7f4b63be806f)

**Steps to Include New Cell in Synthesis**
* We copy the .mag file that we created to the 'src' folder of picorv32a folder.

  * Next we have to go to this directory
`cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a`
and type `gedit config.tcl`
and make the following changes

![Screenshot 2023-09-18 181122](https://github.com/Spoorthi102003/pes_pd/assets/143829280/2c444007-fc10-4f23-a5f0-33160f8f3d17)

Next open Openlane on interactive mode:

* In this directory type `cd ~/Desktop/work/tools/openlane_working_dir/openlane`
* `docker`
* `./flow.tcl -interactive`
* `package require openlane 0.9`
* `prep -design picorv32a -tag 16-09_17-39 -overwrite`
* `set lefs [glob $::env(DESIGN_DIR)/src/*.lef]`
* `add_lefs -src $lefs`
* `run_synthesis`
![Screenshot 2023-09-19 092005](https://github.com/Spoorthi102003/pes_pd/assets/143829280/989a1221-ee28-494b-9682-bada8d1811b6)

* We see that it is being violated 
* To fix this,

![Screenshot 2023-09-19 092144](https://github.com/Spoorthi102003/pes_pd/assets/143829280/2f718614-5d3d-4a47-8587-0a6434e7e987)

* `init_floorplan`
* `run_placement`
* Then go to the following directory `cd ~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/16-09_17-39/results/placement`
And type `magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &`
![Screenshot 2023-09-19 092820](https://github.com/Spoorthi102003/pes_pd/assets/143829280/b4c51fe0-b038-4613-836b-28870ab161fb)
![Screenshot 2023-09-19 092849](https://github.com/Spoorthi102003/pes_pd/assets/143829280/43fc67e6-f6c8-4ddd-baca-ce0e4422c404)
![Screenshot 2023-09-19 095009](https://github.com/Spoorthi102003/pes_pd/assets/143829280/0ed9541a-4e2a-4f4e-9b6f-73f70cd22395)

# Timing Analysis with Ideal Clocks using OpenSTA
**Configure OpenSTA for Post-Synth Timing Analysis**
* In openlane directory create a file called `pre_sta.conf'
* Then create `my_base.sdc` in the picorv32a/src directory
![Screenshot 2023-09-21 161718](https://github.com/Spoorthi102003/pes_pd/assets/143829280/4b63f074-c570-43b3-b415-52c560b82123)

![Screenshot 2023-09-21 161800](https://github.com/Spoorthi102003/pes_pd/assets/143829280/c341c723-bdb1-4f08-8878-2585668457fc)

*When we run `sta pre_sta.conf` we see slack violation.

![Screenshot 2023-09-21 162258](https://github.com/Spoorthi102003/pes_pd/assets/143829280/9c6a232b-781c-43b6-9ac4-964f52256231)

* To reduce slack violation we set the (SYNTH_MAX_FANOUT) = 4
![Screenshot 2023-09-21 163002](https://github.com/Spoorthi102003/pes_pd/assets/143829280/65812ee9-766d-4a28-b2a2-6a2c61955206)

# Timing analysis with real clocks using openSTA
* In the openlane directory type the folowing commands:
* `docker`
* `./flow.tcl -interactive`
* `package require openlane 0.9`
* `prep -design picorv32a -tag 16-09_17-39 -overwrite`
* `set lefs [glob $::env(DESIGN_DIR)/src/*.lef]`
* `add_lefs -src $lefs`
* `run_synthesis`
* `init_floorplan`
* `run_placement`
* `run_cts`

![Screenshot 2023-09-21 164917](https://github.com/Spoorthi102003/pes_pd/assets/143829280/68931150-666b-46c1-b146-9e580f600a7e)
![Screenshot 2023-09-21 165145](https://github.com/Spoorthi102003/pes_pd/assets/143829280/e0fb0dfc-cd6e-4c6e-b45c-f450770b0f87)
* `openroad`
![Screenshot 2023-09-21 165315](https://github.com/Spoorthi102003/pes_pd/assets/143829280/9ad6db3d-305d-4fb6-8da3-90f2eafb1ac9)

* `read_lef /openLANE_flow/designs/picorv32a/runs/18-09_06-26/tmp/merged.lef`
* `read_def /openLANE_flow/designs/picorv32a/runs/18-09_06-26/results/cts/picorv32a.cts.def`
* `write_db pico_cts.db`
* `read_db pico_cts.db`
* `read_verilog /openLANE_flow/designs/picorv32a/runs/18-09_06-26/results/synthesis/picorv32a.synthesis_cts.v`
* `read_liberty -max $::env(LIB_SLOWEST)`
* `read_liberty -max $::env(LIB_FASTEST)`
* `set_propagated_clock [all_clocks]`
* `report_checks -path_delay min_max -format full_clock_expanded -digits 4`
![Screenshot 2023-09-21 165644](https://github.com/Spoorthi102003/pes_pd/assets/143829280/0e394f0e-230d-44c5-8ab9-dee7553542d7)
![Screenshot 2023-09-21 165758](https://github.com/Spoorthi102003/pes_pd/assets/143829280/0e57aba4-b50e-481e-8f38-bdd4b0b7150f)

* Lab steps to Observe Setup and Hold Timing is:
`report_clock_skew -hold` and `report_clock_skew -setup`
</details>

<details>
<summary>DAY5</summary>

#  Final steps for RTL2GDS using tritonRoute and openSTA
**Introduction to Maze routing**:
 Maze routing is a method used in electronic design automation (EDA) and integrated circuit (IC) design to determine efficient paths for interconnecting various components, such as logic gates, on a chip's layout. The goal is to find a path through a maze-like grid of obstacles while optimizing for factors like wire length, signal delay, and area utilization.

- Lee's algorithm, also known as Lee's breadth-first search (BFS) algorithm, is a graph traversal and pathfinding algorithm that is commonly used in maze routing, maze solving, and other grid-based problems. Named after its creator, C. Y. Lee, the algorithm is particularly useful for finding the shortest path between two points in a grid while exploring the grid layer by layer.

**DRC**

* Lambda rules are process-specific design rules used in semiconductor manufacturing to ensure that integrated circuit (IC) layouts adhere to the capabilities and constraints of a particular semiconductor process. These rules are expressed in terms of lambda (λ), a normalized unit of measurement relative to the process technology. Lambda rules can vary between semiconductor foundries and process nodes, but they typically cover various aspects of IC design. Here's a list of common lambda rules and design considerations:

* Minimum Feature Size: Specifies the minimum allowed width and spacing for features such as transistors, metal tracks, and vias, often expressed as multiples of λ.
* Aspect Ratio: Defines the acceptable aspect ratio (width-to-height ratio) for rectangular structures, ensuring manufacturability.
* Metal Layer Constraints: Specifies minimum metal track widths, metal-to-metal spacings, and via sizes on metal layers.
* Poly Pitch: Defines the minimum pitch (spacing between features) for the poly-silicon (poly) layer, which affects the size of transistors and gates.
* Active Area Constraints: Specifies minimum active area dimensions, ensuring that transistors meet process requirements.
* Well and Substrate Taps: Covers the placement and size of well and substrate taps for connecting to power and ground planes.
* Gate Length: Specifies the minimum gate length for transistors, affecting their performance characteristics.
* Contact and Via Rules: Defines the minimum size and spacing of contacts and vias used to connect different layers in the IC.
* Local Interconnects: Provides rules for local interconnects, which are used for routing within a cell or macro.
* Minimum Metal to Active Spacing: Sets the minimum separation between metal tracks and active areas.
* Minimum Metal to Contact Spacing: Specifies the minimum distance between metal tracks and contacts.

**Power Distribution Network and routing**
* After generating our clock tree network and verifying post routing STA checks we are ready to generate the power distribution network gen_pdn in OpenLANE:
* `cd ~/Desktop/work/tools/openlane_working_dir/openlane`
* `docker`
* `./flow.tcl -interactive`
* `package require openlane 0.9`
* `prep -design picorv32a -tag 16-09_19-58`
* `echo $::env(CURRENT_DEF)`
* `gen_pdn`
* `run_routing`

![Screenshot 2023-09-21 171250](https://github.com/Spoorthi102003/pes_pd/assets/143829280/a8d9d3a8-b649-41a6-8a95-542c86c896b1)

![Screenshot 2023-09-21 170850](https://github.com/Spoorthi102003/pes_pd/assets/143829280/4f774ecd-1ee4-4488-9152-3bb0b6e2040f)

![Screenshot 2023-09-21 170932](https://github.com/Spoorthi102003/pes_pd/assets/143829280/fb478b2f-05a6-4003-95d5-9361c826d8eb)

* To extract the parasites.
`cd ~/Desktop/work/tools/SPEF_Extractor/`
* We are using SPEF Extrctor : SPEF Extractor is a software tool used to automatically generate Standard Parasitic Exchange Format (SPEF) files. These files represent parasitic electrical characteristics in integrated circuits, aiding accurate simulation and timing analysis during the design process.
`python3 /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/16-09_17-39/tmp/merged.lef /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/16-09_17-39/results/routing/picorv32a.def`

</details>
