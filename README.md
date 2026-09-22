# 🖥️ 8-Bit Custom Discrete-Logic CPU & Datapath Architecture

A discrete 8-bit custom CPU datapath implementation featuring a shared bus, dedicated register transfer logic, cascaded ALUs (**74HC181**), static RAM (**6116**), and a 7-segment output display (**4543**), simulated using **Proteus Professional**.

![8-Bit CPU Schematic](8Bit_CPU_Schematic.jpg)

---

## 📐 Architecture Overview

This project implements an 8-bit bus-based processor design inspired by classic computer architecture concepts from M. Morris Mano's *Computer System Architecture*.

---

## 🛠️ Hardware Specifications

| Module | IC Components | Description |
| :--- | :--- | :--- |
| **8-Bit ALU** | `2x 74HC181` | Cascaded 4-bit ALUs handling 8-bit arithmetic & bitwise logic operations. |
| **Bus Arbitration** | `74HC173` | Paired 4-bit Tri-State D-type registers managing 8-bit bus line access. |
| **Address Decoder** | `2x 74HC137` | 3-to-8 line decoders with address latches for hazard-free control line selection. |
| **Main Memory** | `6116` | 2K x 8 Static CMOS RAM with dedicated Address and Data registers. |
| **Output Driver** | `4543` | BCD-to-7-segment latch/decoder/driver for visualization. |

---

## 🔄 Verified Execution Flow

1. **Operand Fetch:** Inputs A and B loaded sequentially from I/O onto the 8-bit bus into Registers A and B.
2. **ALU Operation:** Dual 74HC181 ICs compute arithmetic/logic results across all 8 bits.
3. **RAM Write Cycle:** Address and ALU Output data loaded into Memory Registers; written into 6116 SRAM via pulsed control logic.
4. **RAM Read & Render:** Data retrieved from SRAM onto the bus and rendered on the 7-segment display.

---

## 📚 References

- **M. Morris Mano**, *Computer System Architecture* (3rd Edition):
  - **Chapter 4:** Register Transfer and Microoperations (Bus & ALU Logic).
  - **Chapter 5:** Basic Computer Organization and Design.
  - **Chapter 12:** Memory Organization.
