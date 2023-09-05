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

![Positive Edge Triggered 5T-TSPC D Flip-flop Circuit](circuit.png)

**Figure 1: Circuit of Positive Edge Triggered 5T-TSPC D Flip-flop**

| D Input | Clock (clk) | Q Output |
|---------|-------------|----------|
|    0    |      0      |    Q     |
|    0    |      1      |    0     |
|    1    |      0      |    Q     |
|    1    |      1      |    1     |

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








