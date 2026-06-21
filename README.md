# RISC-V Memory-Mapped I/O FPGA Calculator

This project implements a microcomputing system based on the RISC-V instruction set architecture (PicoRV32 core) on a Basys 3 FPGA development board. By utilizing a Memory-Mapped I/O (MMIO) architecture, the system integrates BRAM, slide switches, physical buttons, and a dynamically scanned seven-segment display into a single system bus, achieving seamless hardware-software co-design.

## 🛠️ Development Environment & Hardware
* **Board:** Digilent Basys 3 (Artix-7 xc7a35tcpg236-1)
* **EDA Tool:** Xilinx Vivado 2025.2
* **Toolchain:** RISC-V GNU Compiler Toolchain
* **CPU Core:** PicoRV32 (Execution unit only)

## 📂 Repository Structure
```text
├── src/
│   ├── top.v             # Top-level module (includes MMIO address decoder & bus)
│   ├── memory.v          # 4KB BRAM module
│   ├── seg7_ctrl.v       # 7-segment display dynamic scanning controller
│   └── picorv32.v        # PicoRV32 CPU core (Open Source)
├── constrs/
│   └── basys3_pins.xdc   # Physical constraints / Pin assignments
├── firmware/
│   ├── main.c / main.S   # Software control logic (C or Assembly)
│   └── firmware.mem      # Compiled hex machine code for BRAM initialization
└── README.md             # Project documentation
