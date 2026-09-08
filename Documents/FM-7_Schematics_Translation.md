# FM-7 Complete Schematics — English translation index

Source: **I/O (アイ・オー) magazine, April 1983 (1983年04月号), pp. 281–300** — "FM-7 全回路図" (*FM-7 Complete Circuit Diagrams*).
Compiled PDF: `Documents/IO_198304_FM-7_Schematics.pdf` (20 pages: PDF p.1 = magazine p.281).

The schematics themselves are drawn almost entirely in Latin script — part numbers, pin names and net names are already in English. **The only Japanese on the sheets is the title printed at the top of each page**, plus the contents list and editor's note on the title page. This file translates all of it.

---

## Running header (every page)

| Japanese | English |
|---|---|
| FM-7 回路図 | FM-7 Circuit Diagrams |
| FM-7 全回路図 (title page) | FM-7 Complete Circuit Diagrams |
| 目次 | Contents |

## Editor's note (title page, p.281)

> 本資料は編集部の責任において、あくまでも参考資料として掲載しました。したがって、本資料に関してメーカーに直接問い合わせることはご遠慮ください。（編）

> "This material is published on the editorial department's own responsibility, purely as reference material. Please therefore refrain from contacting the manufacturer directly with enquiries about it. — *Ed.*"

---

## Sheet index

| PDF pg | Mag. pg | Japanese title | English title | What's on the sheet |
|---|---|---|---|---|
| 1 | 281 | FM-7 全回路図 / 目次 | Title page & contents | Photo of the system, editor's note, contents list |
| 2 | 282 | メインCPU部 | **Main CPU section** | MB68B09 main CPU, address/data bus buffers (MB74LS244/245), interrupt & control pull-ups (RB8), power-on reset (D1 1S4468, C5, MB74LS14), `MCPUCLK` → EXTAL, `Z80` / `*DMA` / `*MRDY` / `*HALT` handling |
| 3 | 283 | クロック制御部 | **Clock control section** | X1 4.9152 MHz oscillator, SN74LS93 divider (2 MHz / 1.2 MHz taps), SW2 speed select (`SCLK1`/`SCLK2`), generation of `MCPUCLK`, `SCPUCLK`, `*RESETB`, `EB`, `2MS`, `*MRDY`, MB84040B counter, interrupt-mask/timer logic |
| 4 | 284 | メインI/Oアドレス部 | **Main I/O address (decode) section** | MB74LS138/LS27/LS30 address decoders producing `*FD00–*FD07`, `*RFD00–*RFD05`, `*WFD00–*WFD03`, `*IOS`, `*WTQE`, `*RDE`, `*PL_TREG` |
| 5 | 285 | メインROM部 | **Main ROM section** | MB83256 (32 K) F-BASIC ROM, MB7063/MB8561 boot ROMs, SW1 boot-mode select, `*BTROM`, `*SUBSEL`, `*MOS`, `*RAMHB0/HB1` |
| 6 | 286 | メインRAM部 | **Main RAM section** | 8 × MB8265A-15 (64 K×1 DRAM) = 64 KB main RAM, row/column address mux (MB74LS158), `*RAS`/`*CAS`/`*WE` generation, refresh (`*REFCNT`, `*REFCK`) |
| 7 | 287 | メイン・サブ部 | **Main–Sub interface section** | MB14415 main-side interface gate array, `*SCLKNMI`, `*DMA`, `*BREAK`, `BUSY`, `*ATTENT`, `*EXTDET`, `*RESETB`, buzzer/sound gating, `*GRNT`/`Z8W` handshake between the two CPUs |
| 8 | 288 | メイン プリンタ・カセット部 | **Main printer & cassette section** | Centronics printer port (CN5, SN74LS273 latches, `LPBUSY`, `*LPNT`, `*PGCLR`), cassette interface (CN6 DIN, MB3614 op-amp, `*CANCEL`, `*SUBHALTREQ`), `*RESETB` |
| 9 | 289 | 共有メモリ部 / サブCPU部 | **Shared-memory section / Sub-CPU section** | *Upper:* the 128-byte shared window (MB74LS244/245 buffers, `*SHALTAC`, `*SSMEM`, `*SUBSEL`, `*SRDQE`/`*SQANDE`) between main and sub address/data buses. *Lower:* MC68B09 sub CPU, `SCPUCLK` → EXTAL, `*SRESET` (from `*RESETB` via MB74LS08), `*SHALT`, `*SCLKNMI`, `*SUBIRQ`, `*KSTROBE`, sub bus buffers |
| 10 | 290 | サブ アドレス・デコード部 | **Sub address decode section** | MB74LS138 decoders for the sub CPU map: `*SROMSEL`, `*SRAMCS`, `*SRAMOE`, `*SSMEM`, VRAM `*SDRAM(R/G/B)`, `*SCRTSW`, `*SVRACS`, `*SLED`, `*SBUSYSET`, `*KACKING`, `*BUZZER`, DL1 delay line for `SCPURAS`/`SCPUCAS` |
| 11 | 291 | サブROM/RAM部 | **Sub ROM / RAM section** | MBM2764-20 and MBM2732A-20 sub-monitor ROMs (J1/J2 jumpers select `*SROMSEL`), 2 × MB8128 (2 K×8) sub SRAM |
| 12 | 292 | サブCRT CNTRL部 | **Sub CRT controller section** | MB61030 (MB610301) CRTC gate array, X2 16.128 MHz dot clock, `SVRAS`/`SVCAS`, `*SCSYNC`, `*SBLANK`, `SCLK1–3`, `*SVSYNC`/`*SHSYNC`, `*SVDHALT`, `*SFTCLK`, `*SLOAD`, register select (`*SREGL`/`*SREGH`, `SADRSEL`) |
| 13 | 293 | サブREG/FLAG部 / サブCRTアドレス部 | **Sub register/flag section / Sub CRT address section** | *Upper:* MB74LS74A flip-flops for `*SVDOFF`, `SRWB`, `SVOHALT`, `*SHALTST`/`SHALTAC`, `BUSY`, `*SUBIRQ`, `*CANSEL`, `*SIRQCLR`, and the SN74LS273 page/plane register (`*VPAGE1–3`, `DPAGE1–3`). *Lower:* MB8462 VRAM address mux, plane selects `*SVCASB/R/G`, DL2 delay line, J9/J10 jumpers, `SADRSEL` |
| 14 | 294 | サブCRT RAM部 | **Sub CRT RAM (VRAM) section** | The 48 KB video RAM: three 16-device banks of MB81416 (16 K×4 DRAM) — blue, red and green planes — with MB74LS244 data buffers and per-plane `*SDRAM`/`*SVCAS` strobes |
| 15 | 295 | サブCRTインターフェイス部 | **Sub CRT interface section** | MB13501 video output gate array, MB74LS166 shift registers (dot serialisation), RGB drive transistors (2SC1213), CN4 digital RGB connector, CN6 8-pin DIN, sync mixing (`*SHSYNC`, `*SVSYNC`, `SVIDEOCLK`) |
| 16 | 296 | キーインターフェイス部 | **Keyboard interface section** | MB88401 keyboard-scan microcontroller, CN6 keyboard connector, MB74LS145 row drivers, `*KSTROBE`, `*KEYIN`, `*KACKING`, `*KDATA9`, `*BREAK`, `*LPMASK`/`*TIMMASK`, `SCLK2` |
| 17 | 297 | コネクタ(拡張Z80)部 / コネクタPSG部 | **Connector section (Z80 expansion) / PSG connector section** | *Upper:* CN7 50-pin Z80-card slot and CN8/CN9 (`EADDRBUS`, `EDATABUS`, `*EIRQ`, `*ENMI`, `*EFIRQ`, `EBA`/`EBS`, `ERW`, `*EMRDY`, `EQ`/`EE`, `Z80↓`, `*EEXTDET`). *Lower:* CN8A/CN8B PSG board connector (`AUDOUT`, `1.2MHz`, `*RESETB`, `EB`) |
| 18 | 298 | コネクタ(RS-232C, 漢字)部 / 拡張バス・バッファ部 | **Connector section (RS-232C, Kanji ROM) / Expansion-bus buffer section** | *Upper:* CN12/CN13 A- and B-side option connectors (`EAB0–7`, `EE`, `*ERESET`, `*EEXTDET`, ~2.3 MHz, ±12 V, +5 V). *Lower:* MB74LS245/LS244/LS241 buffers isolating `MADDRBUS`/`MDATABUS` from `EADDRBUS`/`EDATABUS`, plus interrupt pass-through (`*EIRQ`, `*EFIRQ`, `*ENMI`, `*EMRDY`) |
| 19 | 299 | メインPSG部 | **Main PSG (sound) section** | AY-3-8910 PSG, LM386 audio amp, CN1/CN4 audio out, MB74LS74/LS244 register and address latches, `BC1`/`BDIR` control, `*WFD0E`/`*RFD0E`/`*WFD0D`, `1.2MHz` clock, `*RESETB` |
| 20 | 300 | 電源部 | **Power-supply section** | CN10 PSU input (+12 V, +5 V, −12 V, GND), MC7805CT regulator, bulk caps C24/C25/C27/C28, and the decoupling-capacitor allocation blocks — each box lists which board positions (M1, M2, M5 …) the 0.1 µF caps CB1, CB39, CB43, CB56 etc. belong to |

---

## Reading the sheets — conventions

- **`*` prefix = active low.** `*RESETB`, `*SHALT`, `*IRQ` etc. are all asserted low. (The original uses an overbar; the typesetting renders it as a leading asterisk.)
- **`M…` prefix = main-CPU side**, **`S…` prefix = sub-CPU side**, **`E…` prefix = expansion bus.** So `MADDRBUS`/`MDATABUS` vs `SADDRBUS`/`SDATABUS` vs `EADDRBUS`/`EDATABUS`.
- **`M<number>` = board reference designator** (M1, M28, M75 …), matching the silkscreen on the PCB. `RB<n>` = resistor network, `CB<n>` = decoupling cap, `DL<n>` = delay line.
- **`≫` / `≪` arrows** at sheet edges are off-sheet net connectors — follow the net name to the sheet that drives it.
- Fujitsu **MB74LSxx** = second-sourced 74LSxx; **MB…** four-digit parts (MB14415, MB61030, MB13501, MB8462, MB88401) are Fujitsu custom gate arrays with no public datasheet.

## Most useful sheets for a dead-CPU fault

| Question | Sheet |
|---|---|
| Where does the main CPU's reset, HALT, MRDY and DMA come from? | p.282 (PDF 2) |
| Is the CPU clock reaching EXTAL, and how is `*RESETB` generated? | p.283 (PDF 3) |
| Why is the sub CPU halted / what drives `*SHALT` and `*SRESET`? | p.289 (PDF 9), with the handshake on p.287 (PDF 7) |
| Which decoupling cap and rail belongs to a given IC position | p.300 (PDF 20) |
