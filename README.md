# Nguyễn Tô Quốc Việt

**RTL Design & Verification · Computer Engineering, Honors Program @ HCMUT – VNU-HCM · CGPA 3.5/4.0**

---

## Skills

| | |
|---|---|
| **HDL** | SystemVerilog · Verilog |
| **Hardware Design** | SoC Design · Pipelined CPU · Cache Subsystem · On-Chip Interconnect · FSM |
| **Protocols** | AXI4 · AXI4-Lite · AXI4-Stream · APB |
| **EDA** | Vivado · Vitis HLS |
| **Verification** | Cocotb · pyUVM · Directed & Random Testing · Golden-Model Verification · Functional & Code Coverage |

---

## Projects

### RISC-V SoC with Cache Subsystem `SystemVerilog` `FPGA` `2026`

> **RV32I** · **7-Stage Pipeline** · **I/D Cache** · **KV260**

Designed and implemented a 32-bit RV32I SoC in SystemVerilog, including a 7-stage pipelined CPU, hazard handling, a 4 KB direct-mapped I-Cache, and a 4 KB 2-way set-associative D-Cache with write-through / no-write-allocate policy. Integrated the processor and cache subsystem and verified all 38 RV32UI architectural tests. Synthesized the complete design on AMD Kria KV260 at approximately 140 MHz.

---

### Streaming ISP — Black Level & Bad Pixel Correction `C++` `Vitis HLS` `2026`

> **RAW12 Bayer** · **AXI4-Stream** · **Streaming Architecture**

Designed hardware-oriented ISP blocks for RAW Bayer image processing as part of Viettel Digital Talent 2026. Implemented Black Level Correction with saturating arithmetic and AXI4-Stream interfaces, and developed an Adaptive Directional Bad Pixel Correction architecture using same-CFA neighborhood statistics and line-buffer-based streaming processing.

Developed software reference models, image-based test datasets, and verification flows for algorithm and hardware validation.

---

### 64-bit Timer IP — APB Slave `Verilog` `2025`

> **APB** · **RW1C Interrupt** · **Coverage Closure**

Designed a reusable 64-bit timer peripheral with dual operating modes, ÷256 prescaler, and RW1C interrupt handling. Implemented an APB slave supporting PSTRB byte-lane writes, programmable PREADY wait states, and PSLVERR error responses.

Verified the design against the ICTC golden reference model with functional and code coverage closure.

---

## Certifications & Recognition

- **Viettel Digital Talent Program 2026** — Certificate of Achievement  
  *Phase I · Semiconductor — Digital Design and Verification*
- **Viettel Digital Talent Program 2026** — Certificate of Recognition  
  *Talent Ambassador*
- **ICTC — Fundamentals of IC Design & Verification** · *Excellent*
- **IELTS Academic** · 6.5
