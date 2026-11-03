<h1 align="center">Nguyễn Tô Quốc Việt</h1>

<p align="center">
  <b>RTL Design Engineer</b><br>
  Computer Engineering, Honors Program at HCMUT – VNU-HCM · CGPA 3.4 / 4.0
</p>

I design RTL for pipelined CPUs, cache subsystems, AMBA bus interfaces and streaming image datapaths, and I close it out with directed and random tests checked against golden models. I also build the verification harness around that flow, so AI agents can run and check the tests inside a loop I control.

---

## Projects

### Adaptive Directional Bad Pixel Correction · ISP pipeline
`C++` `Vitis HLS` `AXI4-Stream` `AXI4-Lite` · Viettel Semiconductor · 08/2026 – 10/2026 · [repo](https://github.com/NguyenToQuocViet/hls_isp)

A Bayer-aware bad pixel corrector and a four-phase black level corrector for a team ISP, written entirely in C++ for HLS. The BPC went through five algorithm revisions in under two months.

- **Algorithm:** 5×5 window, eight same-color neighbors. V5 predicts along the minimum-gradient direction, uses an adaptive threshold, and applies a four-direction veto so a pixel that any direction supports is left alone.
- **Quality:** five parameters tuned on 1,194 FiveK/HDR+ images, benchmarked on 298 test images with reproducible hot/dead-pixel injection. Against AMD Vitis Vision:

  | Metric | AMD Vitis Vision | V5 |
  |---|---|---|
  | Balanced restoration gain | 87.01% | **91.24%** |
  | Clean-image pixel changes (BCR) | 10.07% | **0.92%** |
  | Off-target changes from injected defects (IOTCR) | 0.00718% | **0.00069%** |

- **Hardware:** 1920×1080 RAW10 streaming design with four line buffers. Pixel loop at II=1, 5.60 ns estimated period at a 150 MHz target, no DSPs. Versus the AMD kernel including stream adapters:

  | Resource | AMD kernel | V5 |
  |---|---|---|
  | LUT | 2,327 | **1,933** |
  | FF | 995 | **854** |
  | BRAM18K | 10 | **8** |

- **Verification:** hand-derived reference cases for the veto logic, threshold boundaries, CFA phases and arithmetic. C simulation and RTL co-simulation match an independent C++ golden model on 2,073,600 Full HD pixels and on 768 pixels across three 16×16 frames without reset: zero missing, mismatched or extra pixels. Output order, SOF/EOL, TKEEP/TSTRB and zero-extension are checked too.

---

### Advanced RV32I Core · Cache Subsystem · Dynamic Branch Prediction
`SystemVerilog` `Vivado` `Verilator` `AXI4` · 02/2026 – present · [repo](https://github.com/NguyenToQuocViet/Advanced-RISC-V-32-bit-SoC)

A 7-stage in-order RV32I core (IF1 · IF2 · ID · EX · MEM1 · MEM2 · WB) with forwarding, hazard detection and stall/flush control.

- **Branch predictor:** pipelined, with a 1024-entry BHT of 2-bit saturating counters and a 1024-entry SRAM-backed tagged BTB. IF1 lookups line up with IF2 predictions; EX-stage training, stalls, flushes and misprediction recovery are handled.
- **Caches:** 4 KB direct-mapped I-Cache and 4 KB 2-way D-Cache (write-through, no-write-allocate) behind AXI4 memory-side interfaces. The I-Cache restarts early from the refill buffer for same-line fetches before the full line commits, and loads are forwarded from a 4-entry write buffer.
- **Result:** 38/38 RV32UI tests pass at the core level, and the design meets 140 MHz post-synthesis timing on the AMD Kria KV260.

---

### 64-bit Configurable Timer IP · AMBA APB slave
`Verilog` `APB` `ICTC scripts` · 06/2025 – 08/2025 · [repo](https://github.com/NguyenToQuocViet/Timer-Advanced-IP)

A reusable timer peripheral with byte-lane access through PSTRB, a clock prescaler from ÷1 to ÷256, a compare-match interrupt cleared by RW1C, debug-halt support, and PSLVERR on illegal configuration. Verified against the ICTC golden reference model, with functional and code coverage closed across every APB transaction type and timer mode.

---

## Experience

### Viettel Digital Talent 2026

**Phase 2 traineeship** · 08/2026 – 11/2026

Owner of the BLC and BPC blocks in a four-member ISP team, covering the whole chain: algorithm evaluation, C++ reference model, HLS implementation, and C/RTL verification.

- Designed the Adaptive Directional BPC over five revisions in under two months. The final version beats AMD Vitis Vision on balanced restoration gain (91.24% vs 87.01%), changes far fewer clean pixels (0.92% vs 10.07%), and uses fewer LUTs, FFs and BRAMs.
- Closed HLS timing at pixel-loop II=1 for 1920×1080 streaming, and verified against an independent golden model with zero mismatched pixels.
- Both blocks went into the team's ZCU102 prototype, which runs at **35.6 fps** and produces **bit-exact output across 32 Full HD frames**.

**Phase 1 internship** · 05/2026 – 08/2026

- Trained in RTL design, SystemVerilog/UVM, SVA, synthesis, static timing analysis and SDC constraints.
- Built an AXI4 RAM and integrated it with the Ibex core.
- Wrote testbenches for a RISC-V decoder and a pipelined arithmetic unit in SystemVerilog/UVM, cocotb and pyuvm.

---

## Toolbox

| | |
|---|---|
| **Languages** | Verilog · SystemVerilog · C/C++ · Python · Tcl |
| **RTL design** | Pipelined CPUs · Cache subsystems · On-chip interconnect · Image signal processing |
| **High-level synthesis** | Vitis HLS |
| **Bus protocols** | AMBA APB · AXI4 · AXI4-Lite · AXI4-Stream |
| **Verification** | Directed and randomized testing against software golden models · SystemVerilog testbenches · cocotb · pytest |
| **Tools** | AMD Vivado · AMD Vitis · Verilator · Linux · Zsh · Git · Makefile · Vim · VS Code |

---

## Education

**HCMUT – VNU-HCM**, B.Eng. Computer Engineering, Honors Program (2023 – 2027)

Coursework: Digital System Design, Logic Design with HDL, Computer Architecture, Operating Systems, Microprocessors & Microcontrollers, LSI Design.

---

## Certificates

- **Viettel Digital Talent Program 2026: Talent Ambassador** · Certificate of Recognition. Ranked 1st in the Digital Design stream of the Semiconductor – Digital Design and Verification track.
- **Viettel Digital Talent Program 2026: Phase 1, Semiconductor – Digital Design and Verification** · Certificate of Achievement. Completed the Phase 1 training of the track.
- **IC Training Center Vietnam (ICTC):** Fundamentals of IC Design & Verification, grade Excellent.
- **IELTS Academic:** 6.5 overall (2022).

---

## Activities

- **Student Ambassador, BK-FC, HCMUT:** mentoring high school students through university outreach and admissions guidance.

**Languages:** Vietnamese (native), English (IELTS 6.5).

---

## Contact

quocviet26105@gmail.com · Ho Chi Minh City, Vietnam
