# X3522-PV Universal FPGA Infrastructure

**Company:** Mezzanine Equity Private Limited  
**Author:** Kenil Thathagar  
**Status:** Engineering specification; not yet a validated or deployable FPGA image.

## Objective
A reusable, board-specific fixed infrastructure for AMD Alveo X3522-PV, independent of application-specific DATA, FIRE, MAC and PCS RTL.

## Hardware and software scope
- PCIe endpoint, XDMA, BARs, interrupts and Linux driver
- DDR4/ECC, BRAM, UltraRAM, memory arbitration and diagnostics
- Four GTY network lanes across two DSFP28 cages; SerDes, gearbox profiles and test datapath
- Clocks, PLLs, CDC/RDC, reset sequencing and recovery
- Hardware timebase, PTP/PPS and timestamp services
- Satellite-controller interfaces, UART, I2C, LEDs and telemetry
- JTAG, QSPI boot, image/fallback verification and safe recovery
- Standard application interfaces for replaceable DATA/FIRE/MAC/PCS RTL

## Critical engineering boundaries
The AMD master XDC supplies pin and configuration constraints, **not** working implementations. Custom FPGA images must include every required FPGA-dependent interface. JTAG recovery and QSPI flash layout must be validated before permanent programming. A diagnostic Ethernet datapath must remain available when custom RTL is disabled. A new custom RTL module may still require a full bitstream rebuild unless DFX is deliberately implemented.

## Reference materials
- [AMD X3522-PV User Guide (UG1607)](https://docs.amd.com/r/en-US/Alveo-X3522PV-Adaptable-Accelerator-Card-User-Guide-UG1607)
- [AMD X3522 Data Sheet (DS1002)](https://docs.amd.com/r/en-US/ds1002-x3522)
- AMD X3522-PV Master XDC revision 1.00 (2022-09-16)
- AMD ADK2 debug kit documentation (UG1538)
- AMD PCIe DMA/Bridge Subsystem (PG195)

## Master PDF
The author-attributed master PDF is prepared, but its binary file must be uploaded to this repository separately. It has **not** been committed here yet.

## License
No license has been selected. All rights reserved unless a license is added by the repository owner.
