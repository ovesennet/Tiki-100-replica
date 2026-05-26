# TIKI-100 computer replica schematics

## What is the TIKI-100

The TIKI-100 (also known as KONTIKI-100) is a Z80-based microcomputer designed and manufactured by Tiki Data AS in Norway, first released in 1984. It was primarily used in Norwegian schools and homes during the mid-1980s as part of a national initiative to introduce computers into education.

### Technical specifications

- **CPU:** Zilog Z80A running at 4 MHz
- **RAM:** 64 KB main memory (8× 4164 DRAM) + 32 KB video RAM (4× 4416 DRAM)
- **ROM:** 16 KB system ROM (2× 2732A EPROM)
- **Video:** Custom logic with palette RAM (2× 74S189), supporting multiple display modes — 1024×256 monochrome, 512×256 4-color, and 256×256 16-color. Active-matrix RGB output with resistor DAC ladder and LM1886 RGB-to-composite encoder
- **Sound:** General Instrument AY-3-8912 PSG (3 channels + noise)
- **Storage:** Built-in floppy disk controller (FD1797) supporting two drives
- **Serial:** Dual RS-232 ports via Z80 DART with 75188/75189A level shifters
- **Parallel:** Active-low Centronics printer port via Z80 PIO
- **Expansion:** Three 50-pin expansion slots carrying the full system bus
- **Keyboard:** Matrix-scanned via 74159 decoder and 74LS244 buffer
- **Peripheral ICs:** Z80 CTC (timer), Z80 DART (serial), Z80 PIO (parallel I/O), 9216B (floppy data separator)
- **Operating system:** TIKO, CP/M-80 compatible, TIKI-BASIC

### History

The TIKI-100 saw widespread adoption in Norwegian schools throughout the 1980s, and a loyal community of enthusiasts kept it alive well beyond its commercial lifespan. The original schematics were drawn as sheets 29095-1 through 29095-6 (Rev C).

## About this project

This project is a replica of the TIKI-100 mainboard schematics, recreated in KiCad 10. The schematics follow the original Rev C design as closely as possible, using the same component references, signal names, and circuit topology. Only the mainboard is included — the power supply is not part of this project.

The KiCad project is located in `src/Tiki-100-mainboard/` and consists of a hierarchical schematic with the following sheets:

| File | Description |
|------|-------------|
| `Tiki-100-mainboard.kicad_sch` | Top-level schematic (hierarchical sheet references) |
| `CPU.kicad_sch` | Z80A CPU, crystal oscillator, clock divider, reset circuit, wait-state logic |
| `Memory.kicad_sch` | 64 KB main RAM (8× 4164), 16 KB ROM (2× 2732A), address multiplexers, data buffers |
| `Address_Decode.kicad_sch` | Address decoding PROM (63LS140), active bus signal pull-ups |
| `Serial.kicad_sch` | Z80 DART dual serial ports, RS-232 level shifters (75188/75189A), connectors P5/P6 |
| `Parallel.kicad_sch` | Z80 PIO parallel port, Centronics connector P4, cassette interface (LM393 comparator) |
| `Timer.kicad_sch` | Z80 CTC counter/timer |
| `Sound.kicad_sch` | AY-3-8912 PSG, scroll offset registers, bus transceiver (LS245) |
| `FDC.kicad_sch` | FD1797 floppy disk controller, 9216B data separator, 34-pin floppy connector P1 |
| `Keyboard.kicad_sch` | Keyboard matrix scanner (74159 decoder, LS244 buffer), connector P2 |
| `Expansion.kicad_sch` | Three 50-pin expansion slots (P7/P10/P12), LM1886 RGB encoder, DIN video connectors, phono sound output |
| `Video.kicad_sch` | Video RAM (4× 4416), pixel shift registers, palette RAM (2× 74S189), RGB DAC, address multiplexers, scan counters, sync generation |
| `Tiki-100-mainboard.kicad_pro` | KiCad project file |
| `Tiki-100-mainboard.kicad_pcb` | PCB layout (empty — schematics only) |

---

Created by Arctic retro 2026
