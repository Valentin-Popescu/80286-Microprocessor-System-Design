#80286 Microprocessor System Design

##Project Overview

This repository contains the hardware schematic design for a microprocessor system based on the Intel 80286 CPU. The project demonstrates low-level computer architecture design, including memory interfacing, address decoding, and peripheral I/O mapping using OrCAD.

##System Architecture

The system architecture integrates the following core memory and I/O components:
CPU: Intel 80286
EPROM (16KB): Implemented using two 2764 modules (8KB each) configured in Low and High banks to manage even and odd addresses.
SRAM (32KB): Implemented using four CY6264SO modules (8KB each).
DRAM: 512KB system main memory.
I/O Module: Integrates programmable peripheral interfaces including 8259A, 8255, 8254, and 8279 chips.

##Memory Map

The memory address space is strictly defined utilizing address decoders (such as the 74ALS138) and logic gates:
`000000H - 07FFFFH`: DRAM 512KB
`080000H - 087FFFH`: SRAM 32KB
`0F0000H - 0F3FFFH`: EPROM 16KB

##I/O Port Configuration

The I/O module is designed to respond to the base address `740H`. Peripheral chips are addressed consecutively using logic gates to decode the address prefix:
8255: `740H`, `742H`, `744H`, `746H`
8254: `748H`, `74AH`, `74CH`, `74EH`
8259A: `750H`, `752H`
8279: `754H`, `756H`

##Repository Structure

`ProiectSM.opj` / `PROIECTSM_0.DBK`: Source files for the OrCAD schematic design.
`Popescu Marian-Valentin.pdf`: Comprehensive project documentation detailing schematic block diagrams, logic gate configurations, and address tables.

##Author
Popescu Marian-Valentin
