# MiniVM-16

**A Custom 16-bit Mini Virtual Machine Implemented in 8086 Assembly**

MiniVM-16 is an educational project that aims to simulate a lightweight 16-bit virtual CPU using 8086 Assembly language.

The project explores fundamental computer architecture concepts, including instruction decoding, virtual registers, memory management, arithmetic operations, and program execution.

> **Project status:** In development.

## Overview

The goal of this project is to build a small virtual machine that executes its own custom instruction set, independently of the native 8086 instruction set.

The 8086 processor executes the emulator, while MiniVM-16 maintains its own virtual CPU state and interprets a separate sequence of virtual instructions.

The virtual machine is designed around the following components:

- A custom instruction set architecture (ISA).
- Four 16-bit virtual registers.
- A virtual instruction pointer.
- A 256-byte virtual data memory.
- An instruction fetch-decode-execute cycle.
- Basic arithmetic, memory, and control-flow instructions.
- Instruction validation and error handling.

## Objectives

- Understand how instruction decoding and execution work.
- Implement a simple virtual CPU in 8086 Assembly.
- Design a custom instruction encoding format.
- Simulate virtual registers and memory.
- Implement arithmetic operations and conditional jumps.
- Test the virtual machine using small example programs.

## Architecture

The virtual machine follows a simplified fetch-decode-execute cycle.

1. **Fetch:** Read the next instruction byte from the virtual program.
2. **Decode:** Identify the opcode and determine the instruction's operands.
3. **Execute:** Perform the requested operation on virtual registers or memory.
4. **Update state:** Update the virtual instruction pointer and applicable flags.
5. **Repeat:** Continue until a halt instruction or execution error occurs.

### Virtual CPU specification

| Component | Specification |
|---|---|
| Word size | 16 bits |
| Virtual registers | R0, R1, R2, R3 |
| Register width | 16 bits |
| Virtual data memory | 256 bytes |
| Virtual instruction pointer | 16-bit byte offset |
| Initial status flag | Zero Flag |
| Instruction encoding | Opcode-based, variable-length instructions |

## Instruction Set

The planned instruction set includes:

| Opcode | Instruction | Description |
|---|---|---|
| `01h` | `MOVI` | Load an immediate value into a register |
| `02h` | `MOV` | Copy one register into another |
| `03h` | `ADD` | Add two register values |
| `04h` | `SUB` | Subtract one register value from another |
| `05h` | `LOAD` | Load a word from virtual memory |
| `06h` | `STORE` | Store a word in virtual memory |
| `07h` | `JMP` | Jump to a virtual program address |
| `08h` | `JZ` | Jump if the Zero Flag is set |
| `09h` | `AND` | Perform a bitwise AND |
| `0Ah` | `OR` | Perform a bitwise OR |
| `0Bh` | `XOR` | Perform a bitwise XOR |
| `FFh` | `HLT` | Halt virtual machine execution |

The instruction set and encoding format may evolve during development. Refer to the ISA documentation for the finalized specification.

## Technology Stack

- **Assembly language:** Intel 8086 Assembly
- **Development environment:** EMU8086
- **Version control:** Git
- **Repository hosting:** GitHub

## Project Structure

```text
MiniVM-16/
├── src/
│   └── minivm.asm
├── docs/
│   ├── ISA.md
│   └── architecture.md
├── tests/
│   ├── arithmetic/
│   ├── memory/
│   └── control_flow/
├── screenshots/
├── README.md
├── LICENSE
└── .gitignore
```

## Getting Started

### Requirements

- EMU8086 installed on your computer.
- Basic knowledge of 8086 Assembly.
- Git, if you want to clone and manage the repository.

### Running the Project

1. Clone or download this repository.
2. Open `src/minivm.asm` in EMU8086.
3. Assemble the source code.
4. Run the program in the emulator.
5. Follow the program output to inspect the virtual machine's state and execution results.

**Note:** The source code and supported instructions are under active development. The exact execution and output procedures may change as features are implemented.

## Testing

The project will be tested using small virtual programs covering:

- Immediate values and register operations.
- Addition and subtraction.
- Virtual memory reads and writes.
- Unconditional and conditional jumps.
- Halt behavior.
- Invalid opcodes and invalid memory addresses.
- Incomplete instructions and program boundaries.

Expected and actual results will be documented as implementation progresses.

## Roadmap

- [ ] Define the virtual CPU architecture.
- [ ] Implement virtual registers and initialization.
- [ ] Implement instruction fetching.
- [ ] Implement opcode decoding.
- [ ] Add `MOVI` and `MOV`.
- [ ] Add `ADD` and `SUB`.
- [ ] Implement virtual memory with `LOAD` and `STORE`.
- [ ] Add `JMP` and `JZ`.
- [ ] Add `HLT` and error handling.
- [ ] Implement bitwise operations.
- [ ] Complete the test suite.
- [ ] Document the ISA and architecture.
- [ ] Capture execution screenshots and finalize the report.

## Limitations

MiniVM-16 is an educational simulator, not a replacement for a physical CPU or a production virtual machine.

The supported instruction set, memory model, and execution behavior are limited to the features implemented in this project.

## Academic Context

This project is developed as part of an Assembly Language course to explore CPU architecture, instruction execution, memory management, and low-level programming.

## License

A license has not yet been selected. Usage and redistribution terms will be specified when a license is added.
