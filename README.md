<h1 align="center">Mainak Sil</h1>
<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&size=18&pause=1000&color=2EC866&center=true&vCenter=true&width=650&lines=Digital+IC+Design;Physical+Design;RTL+to+GDSII" alt="Typing SVG" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Verilog-1a1a1a?style=for-the-badge&logo=v&logoColor=2EC866" />
  <img src="https://img.shields.io/badge/SystemVerilog-1a1a1a?style=for-the-badge&logo=v&logoColor=2EC866" />
  <img src="https://img.shields.io/badge/TCL-1a1a1a?style=for-the-badge&logo=tcl&logoColor=3E8E7E" />
  <img src="https://img.shields.io/badge/Cadence Virtuoso-1a1a1a?style=for-the-badge&logo=cadence&logoColor=white" />
  <img src="https://img.shields.io/badge/Cadence Innovus-1a1a1a?style=for-the-badge&logo=cadence&logoColor=white" />
  <img src="https://img.shields.io/badge/Cadence Genus-1a1a1a?style=for-the-badge&logo=cadence&logoColor=white" />
  <img src="https://img.shields.io/badge/Synopsys Primetime-1a1a1a?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Xilinx%20Vivado-1a1a1a?style=for-the-badge&logo=xilinx&logoColor=E4002B" />
</p>

---

### `whoami`

```verilog
module mainaksil (
    input  wire        clk,
    input  wire         rst_n,
    output reg  [2:0]   focus,     // 000: ASIC | 001: FPGA | 010: RTL | 011: GDSII
    output reg          curiosity  // never gated
);
    // Hands-on across the full RTL-to-GDSII flow

    always @(posedge clk or negedge rst_n) begin
        if (!rst_n) begin
            focus      <= 3'b010;
            curiosity  <= 1'b1;
        end else begin
            curiosity  <= 1'b1;     // always high, never resets
        end
    end

endmodule
```

---

### `synth.tcl` — currently in flow

```tcl
# report_status.tcl

read_design -source rtl/
set_top     current_focus

foreach block { bitnet_bitlinear_accel  des_asap7_pnr } {
    puts "-- exploring: $block"
}

# STATUS
# [x] RTL-to-GDSII flow for a RTL on ASAP7 7nm (Genus -> Innovus -> PrimeTime)
# [~] BitNet b1.58 BitLinear kernel in Verilog, targeting a Zybo Z7-10 (Zynq-7000)

report_qor -summary
```

---

### Toolchain

| Layer | Tools |
|---|---|
| **HDL** | Verilog, SystemVerilog |
| **Synthesis / PnR / Signoff** | Cadence Genus, Cadence Innovus, Synopsys PrimeTime |
| **Simulation** | Xilinx Vivado|
| **Scripting** | TCL, Python |
| **Languages** | Python, C/C++, Embedded C, Assembly (8085, ARM)|
| **Other** | COMSOL Multiphysics (Semiconductor Module) |

---

<p align="center">
  <a href="https://github.com/MainakSil">
    <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" />
  </a>
</p>
