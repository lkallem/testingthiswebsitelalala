---
layout: page
title: "Technical Documentation"
permalink: /docs/
---

### MoSAIC P-38 Interface and Registry Specification

#### Memory Map Organization
Individual tiles maintain localized code/scratchpad visibility windows. External structural synchronization steps pass through memory-mapped IO registers.

| Base Register Address | Scope / Boundary Access | Core Functional Parameter |
|-----------------------|-------------------------|---------------------------|
| `0x40000000`          | Read/Write Access       | Network Packet Payload Out|
| `0x40000004`          | Read-Only State         | Incoming Buffer Length    |
| `0x40000008`          | Read/Write Control      | Tile Status Configuration |

#### Toolchain Compiler Prerequisites
To construct and emit valid target binary executable files compatibility layers, ensure your developer workstation includes:
* **RISC-V GNU Toolchain** (`riscv32-unknown-elf-gcc`)
* **Icarus Verilog** v11.0 or newer (or alternative SystemVerilog compliant simulator)
* **Perl Core Framework Interconnects**
