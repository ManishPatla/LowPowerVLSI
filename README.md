<img width="356" alt="image" src="https://github.com/ManishPatla/LowPowerVLSI/assets/109287423/3d9bbc14-91a3-41c0-8f8f-5b2725daa40e">

# LowPowerVLSI

## Design of Low Power TSPC CMOS D Flip Flop using SVL method:

## Introduction

This project focuses on the design and analysis of a Low Power TSPC CMOS D Flip-Flop using Supply Voltage Level (SVL) Methods.
The primary goal is to reduce power consumption, especially due to leakage currents, and optimize battery backup time while the circuit is in standby mode.

### Motivation

- **Power Consumption**: In CMOS technology, power dissipation is a significant concern, especially due to leakage currents. This project aims to minimize power consumption.

- **Battery Backup**: Reducing power consumption during standby mode is crucial for extending the time available for battery backup.

### Key Objectives

- Design an efficient D Flip-Flop circuit.
- Implement supply voltage level (SVL) methods to reduce power consumption.
- Minimize power consumption and leakage currents through the use of a minimal number of transistors.
- Enable the D Flip-Flop for applications like binary counters, shift registers, and analog and digital circuit systems.

### Technology

The project leverages CMOS technology, with a specific focus on mitigating leakage power to enhance energy efficiency and extend battery backup time.

## Performance Comparison

In this report, we conduct a performance comparison among different TSPC D Flip-Flops. The comparison is based on the following criteria:

- Transistor Density
- Power Consumption
- Energy Efficiency

## Project Details

- **Technology**: 180nm
- **Tools**: Cadence Virtuoso for design and simulation

## Getting Started

To explore this project and its findings, please refer to the detailed documentation in the repository.

## License

This project is open-source and available under the [MIT License](LICENSE). Feel free to use, modify, and share as you explore the realm of low-power CMOS design.

## Acknowledgments

This project was completed as part of the coursework in Low Power VLSI Design at PES University, under the guidance of Professor Chiranjeevi. Special thanks to the dedicated efforts of students:

- Manish Patla
- Shri Sagar A

We express our sincere gratitude for their valuable contributions and commitment to the success of this project.

----------

## Project Details

### Design of 5T-TSPC CMOS D Flip-flop

#### Introduction

Achieving high performance in Very Large Scale Integration (VLSI) systems is paramount, especially with the continuous growth of semiconductor technology. As technology advances, Systems-On-a-Chip (SOC) designs contain more components, leading to higher transistor density and increased power consumption. These designs also require faster clock speeds, which can consume even more power.

To enhance both frequency of operation and component integration in VLSI Integrated Circuits (ICs), Complementary Metal Oxide Semiconductor (CMOS) technology has made significant advancements. However, distributing the global clock input and its inverse can result in clock skew problems and higher power consumption.

**True Single Phase Clock (TSPC)** flip-flops offer an effective solution. TSPC is a highly dynamic flip-flop that operates at high speed while minimizing power consumption. It relies on a single-phase clock for synchronization, effectively addressing clock skew issues. Research has demonstrated that TSPC-based designs feature small footprints and support higher clock frequencies, ultimately improving the performance of digital systems.

#### Applications

TSPC-based flip-flops find applications in a variety of domains, including:

- Digital VLSI clocking systems
- Microprocessors
- Buffers
- Wireless communication systems
- And more

By leveraging the advantages of TSPC-based flip-flops, designers can achieve a balance between high performance and low power consumption, making them a valuable choice in modern VLSI design.

For in-depth technical details and analysis, please refer to the project documentation.

------------------

## Implementation

### Circuit and Truth Table

![Circuit svl TSPC DFF](https://github.com/ManishPatla/LowPowerVLSI/assets/109287423/06d52d94-6d6e-4bd9-995d-82860aad4fb4)


**Figure 1: Circuit of Positive Edge Triggered 5T-TSPC D Flip-flop**

<img width="415" alt="image" src="https://github.com/ManishPatla/LowPowerVLSI/assets/109287423/8844cbf7-12a3-46c9-976d-c9d99974d8da">


**Table 1: Truth Table of Positive Edge Triggered 5T-TSPC D Flip-flop**

### Description

The Positive Edge Triggered 5T-TSPC CMOS D Flip-flop is constructed using 3 NMOS and 2 PMOS transistors. This design employs a single clock phase signal for synchronization, leading to efficient power management and improved performance.

#### Transistor Count

One notable feature of this flip-flop is its low transistor count. With only 5 transistors in its construction, it consumes less area and power, contributing to enhanced performance.

#### Working Principle

The working principle of this flip-flop can be summarized as follows:

- When the clock (clk) and input signal (D) are HIGH (i.e., clk=1, D=1), NMOS transistors m2 and m3 turn ON, while PMOS transistor m1 turns OFF. This action subsequently activates PMOS transistor m4 and deactivates NMOS transistor m5, pulling the output (Q) HIGH (i.e., Q=1).

- Similarly, when clk=1 and D=0, PMOS transistor m1 and NMOS transistor m2 are ON, while m3 is OFF. This operation triggers m5, producing a LOW output. Thus, during the ON period of the clock signal, the output follows the input.

- When clk=0, the output retains its previous value, as it does not respond to the input.

### Significance of TSPC Design

TSPC (True Single Phase Clocked) logic design utilizes one aspect of the clock pulse, avoiding skew problems during the design process, and performs well in digital structures. Due to these advantages, TSPC designs are known for their low power consumption and improved performance in digital systems.

----------------------

## Design Strategy 2: SVL Method Enforced on CMOS D Flip-Flop

### Introduction

SVL, which stands for Self-Voltage Level, is a technique utilized to minimize power dissipation in clocked structures, particularly in Flip-flops when they are in standby mode.

#### SVL Working Principle

- When Clock=0, the SVL method employs both PMOS and NMOS transistors equivalently for the pull-up and pull-down networks. The gate of pull-up transistors is connected to the complement of the clock signal, while the gate of pull-down transistors is connected to the clock signal itself. This technique reduces leakage power by using the clock signal as a control signal to manage the supply voltage to the D flip-flop. Hence, the name "self-voltage level" is justified.

- When the clock = 1, and clock bar (complement of clock) = 0, Psw1 (power switch 1) will become ON, and Nsw1 (negative switch 1) will be in the off state. The clocked circuit will be connected to Vdd.

- When the clock = 0, the circuit is in standby mode and does not require a higher power supply to maintain operation. Even if we reduce the supply voltage during standby mode, it will function perfectly, reducing power consumption, especially leakage power that occurs when transistors are in the off state.

### Operation in Active Mode (clock = 1)

- In active mode, Psw1 is ON, Nsw2 is ON, Psw2 is OFF, and Nsw1 is OFF. The D flip-flop is connected to Vdd and ground for normal circuit operation.

    - If D_in = 0, P1, N1, N3 are ON, and P2, N2 are OFF, connecting Q to ground (Q = 0).
    
    - If D_in = 1, P1, N3 are OFF, and N1, N2, P2 are ON, connecting Q to Vdd (Q = 1).

### Operation in Standby Mode (clock = 0)

- In standby mode, Psw1, Nsw2 are in the OFF state, i.e., open circuits. Nsw1 is ON but, as it is used as a pull-up, it provides Vdd-Vth as the supply voltage for the D flip-flop. The drop is due to the resistive nature of NMOS when used as a pull-up. Similarly, Psw2 is ON, but as it is used as a pull-down, it provides a finite positive voltage instead of ground (0 volts). This virtual ground positive voltage slightly reverse biases the NMOS transistors of the D flip-flop, reducing leakage power in standby mode. The PMOS transistors of the D flip-flop also have reduced leakage power, as they are connected to a virtual supply in standby mode.

![Circuit svl TSPC DFF](https://github.com/ManishPatla/LowPowerVLSI/assets/109287423/97c1ac9e-e1a5-43bb-98e6-1b8946997f07)

**Figure 2: Schematic Diagram of CMOS D Flip-Flop using SVL Method**

For further insights and simulation outcomes, please refer to the project documentation.

---

## Design Strategy 3: Modified SVL Technique applied on CMOS D-Flip Flop

### Introduction

Figure 3 illustrates the structure of a D Flip-Flop (DFPFP) utilizing an enhanced SVL (Self-Voltage Level) method. The DFPFP is designed using five transistors, comprising two PMOS transistors (P1 & P2) and three NMOS transistors (N1, N2, & N3).

### Operation in Active Mode (clock = 1)

In the active mode (when the clock signal is '1'), the following operations occur:

- P1 turns ON
- N2 turns ON
- P2 and P3 turn OFF
- N1 and N3 turn OFF

This configuration connects the DFPFP to Vdd and ground for normal circuit operation. The behavior of the DFPFP during this state depends on the value of Din:

- If Din is 0, P1, N1, N3 turn ON, while P2 and N2 turn OFF. This causes 'Q' to connect to ground, resulting in Q = 0.

- If Din is 1, P1, N3 turn OFF, while N1, N2, and P2 turn ON. This configuration connects 'Q' to Vdd, resulting in Q = 1.

### Operation in Standby Mode (clock = 0)

In standby mode (when the clock signal is '0'), the following operations occur:

- P1 and N3 turn OFF (operate as open switches)
- N1 and N2 turn ON

Due to the transistors in the pull-up network, VDD - Vth is supplied to the D Flip-Flop. Additionally:

- P2 and P3 turn ON, providing a limited positive potential instead of ground (0 volts).

The virtual ground positive potential moderately reverse biases the NMOS transistors of the DFF, optimizing power dissipation in standby mode. The PMOS transistors of the DFF also experience reduced leakage power, as they are connected to a virtual supply in standby mode.

### Enhanced SVL Method Significance

The enhanced SVL method optimizes power dissipation and minimizes leakage current flow due to the inclusion of extra two transistors. This optimization is achieved by substantially optimizing the supply potential for the flip-flop design in static mode. Power dissipation, under ideal conditions, is directly related to supply potential and current, resulting in reduced power dissipation for the same values due to the enhanced SVL method.

The projected SVL technique not only optimizes power dissipation but also reduces the count of clocked transistors. This leads to an increase in the working speed of the design and optimization of dynamic power consumption. Therefore, this DFF method in standby mode is utilized to reduce power consumption.

![Modifiedsvl design ](https://github.com/ManishPatla/LowPowerVLSI/assets/109287423/edbe59d7-b86e-4f6d-901d-c5c8295cbba8)


**Figure 3: DFPFP Structure using Enhanced SVL Method**

For more details and simulation results, please refer to the project documentation.

---











