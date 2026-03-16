# Nguyễn Tô Quốc Việt

RTL Design & Verification · Computer Engineering @ HCMUT-VNU Honors Program · CGPA 3.4/4.0

---

## Skills

| | |
|---|---|
| **HDL** | Verilog, SystemVerilog |
| **Design** | RTL · FSM · Pipelined CPU · Cache Subsystem · On-Chip Interconnect |
| **Protocols** | AMBA APB · AXI4 · AXI4-Lite |
| **ISA** | RISC-V RV32IMF · MIPS32 |
| **EDA** | Vivado · Quartus · Cadence Genus · Cadence Innovus |
| **Verification** | Directed Testbench · Functional & Code Coverage |

---

## Projects

### Advanced 32-bit RISC-V SoC &nbsp;`SystemVerilog` `2026 – present`

> **RV32IM** · **AXI4** · **Cache Subsystem**

RV32IM core from micro-arch spec to RTL. 4KB direct-mapped I-Cache + 4KB 2-way D-Cache (write-through, write-no-allocate, 4-entry write buffer, load-to-store forwarding). AXI4 Bus Arbiter mediating concurrent cache requests with burst transaction scheduling.

---

### 32-bit MIPS 5-Stage Pipelined CPU &nbsp;`Verilog` `FPGA` `2025`

> **75 MHz** · **BTB + 2-bit BHT** · **Hazard Control Unit** · **PLRU**

Full RTL flow → FPGA synthesis at 75 MHz. 4-way set-associative caches (write-back, PLRU). Dynamic branch prediction via BTB + 2-bit BHT. Hazard Control Unit with EX→EX / MEM→EX forwarding and stall logic. Verified against golden reference model.

---

### 64-bit Timer IP — AMBA APB Slave &nbsp;`Verilog` `2025`

> **APB** · **RW1C** · **Coverage Closure**

Reusable 64-bit Timer IP: dual-mode, ÷256 prescaler, RW1C interrupt. Full APB slave — PSTRB byte-lane access, PREADY wait-states, PSLVERR error response. Verified against ICTC golden model with functional and code coverage closure.

---

## Certifications

- **ICTC** — Fundamentals of IC Design & Verification · *Excellent*
- **IELTS** Academic · 6.5
