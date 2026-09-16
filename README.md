# fpga-soc-306

FAMU-FSU Senior Design Group 306

## Folder structure

```text
fpga-soc-306/
├── constraints/    # FPGA timing and pin constraints (.xdc)
├── docs/           # Documentation for each hardware subsystem
├── fpga/           # Vivado project (fpga.xpr) and generated project files
├── rtl/            # SystemVerilog hardware source files
├── sw/             # Software and related documentation
└── tb/             # SystemVerilog testbenches, organized to mirror rtl/
```

The `rtl/` and `tb/` folders contain matching subsystem folders:

| Folder | Purpose |
| --- | --- |
| `cpu/` | Processor core |
| `fft/` | Fast Fourier transform hardware |
| `interconnect/` | Connections between SoC components |
| `matmul/` | Matrix multiplication hardware |
| `memory/` | Memory subsystem |
| `peripherals/` | Peripheral devices and interfaces |
| `soc/` | Top-level system-on-chip integration |

Each subsystem has a corresponding Markdown file in `docs/`, such as `docs/cpu.md`.

## SystemVerilog conventions

- Each SystemVerilog (`.sv`) file must contain exactly one module.
- The module name must match the file name without the `.sv` extension. For example, `cpu.sv` must declare `module cpu`.
- A testbench must use the name of the module it tests followed by `_tb`, for both its module name and file name. For example, the testbench for `cpu` is `cpu_tb.sv` and declares `module cpu_tb`.
- Place hardware modules in the appropriate `rtl/` subsystem folder and their testbenches in the matching `tb/` folder. For example, `rtl/cpu/cpu.sv` is tested by `tb/cpu/cpu_tb.sv`.
