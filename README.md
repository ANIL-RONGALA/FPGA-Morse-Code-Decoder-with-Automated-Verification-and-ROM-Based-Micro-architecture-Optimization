🛰 ROM-Based Morse Code Challenge on FPGA

An interactive Morse code challenge game implemented on the Intel Cyclone V FPGA (5CEBA4F23C7N) using Verilog, combining hardware design, embedded system architecture, memory-mapped logic, and real-time simulation. Features include multi-user authentication (via EPCS64 flash), time-limited levels, score tracking (via on-chip RAM), progressive difficulty, and full testbench verification (using ModelSim). Synthesised using Intel Quartus Prime.

🎮 1. Project Overview

This project serves as a compact but complete hardware/firmware design for a game logic system on an FPGA. Key capabilities:

ROM-based storage of Morse-code phrases

EPCS64 flash for user authentication & profile data

On-chip RAM for dynamic levels / score tracking

Time-limited challenges and progressive game difficulty

Modular Verilog architecture (logic, memory, control)

Full simulation coverage and testbench suite in ModelSim

Quartus Prime design flow: synthesis, place & route, timing closure

The repository includes all HDL sources, testbenches, simulation scripts, and project files for Quartus Prime.

🛠 2. Tools & Versions
Tool	Recommended Version
Intel Quartus Prime	20.1 (or earlier 18.x)
ModelSim-Intel	10.7 or matching version
FPGA Board	Cyclone V 5CEBA4F23C7N or equivalent

These versions ensure compatibility with the EPCS64 IP core, Cyclone V device family, and the simulation models used.

📁 3. Repository Structure
ROM-FPGA-MorseGame/
│
├── src/
│   ├── auth/              # EPCS64 flash authentication logic
│   ├── memory/            # ROM, RAM, memory-mapping modules
│   ├── control/           # Game control FSMs, timer logic
│   ├── game/              # Morse-code phrase logic, levels
│
├── sim/
│   ├── testbench/         # ModelSim testbenches
│   ├── scripts/           # Simulation run scripts
│
├── quartus_project/
│   ├── MorseGame.qpf      # Quartus project file
│   ├── MorseGame.qsf      # Quartus settings file
│
├── docs/
│   ├── Wiring_Diagram.pdf
│   ├── Architecture_Overview.pdf
│   ├── BOM_and_FPGA_board.pdf
│
└── README.md

📦 4. Getting Started

Clone the repository

git clone https://github.com/ANIL-RONGALA/ROM-FPGA-MorseGame.git
cd ROM-FPGA-MorseGame


Simulate in ModelSim

Open sim/testbench in ModelSim

Run relevant .do script to verify modules (e.g., run_auth.do, run_game.do)

Check waveforms, assertion logs, and coverage reports

Synthesize in Quartus Prime

Open quartus_project/MorseGame.qpf in Quartus Prime

Set device to 5CEBA4F23C7N (Cyclone V)

Compile full design

Ensure timing constraints are met, no critical warnings

Program FPGA

Connect your FPGA board (Cyclone V dev board)

Use Quartus Programmer to load the .sof file onto the device

Ensure EPCS64 flash contains correct user database (as described in docs)

Power on and run the game

✅ 5. Game Operation

On power‐up, the FPGA reads user credentials from EPCS64 flash

After successful authentication, user selects a level

A Morse code sequence is played back (via on-board LEDs/outputs)

Player must decode the Morse code within a fixed time limit

Score is incremented in RAM and displayed (via output port or console)

Levels increase in difficulty (shorter intervals, more characters, faster pace)

After game over, score is stored and user may replay or logout

🔍 6. Design Highlights

Modular Verilog Architecture — separates memory modules, control FSMs, game logic

Memory Mapping — ROM for static phrases, RAM for dynamic data, flash for persistent storage

Time-Critical Logic — all synchronous design, no asynchronous resets beyond global reset

Testbench Coverage — full coverage for authentication, timer logic, phrase decoding, level transitions

Board Integration — ready to deploy on Cyclone V dev board; includes pin assignment, constraints, and I/O mapping

🎯 7. Future Research & Expansion

Integrate SPI/I2C sensors (microphone, accelerometer) to enrich gameplay

Expand to FPGA-based learning platform: Morse game → state-machine training tool

Use the architecture for educational FPGA labs: memory hierarchy, timing, authentication

Adapt design for low-cost SoC+FPGA board → embed in mobile device or drone controller

Implement networked multiplayer mode using Ethernet/USB-UART to connect multiple FPGA boards

📄 8. License & Credits

This project is made available for educational, research, and academic use.
Contributions and derivatives are welcome under the terms of the LICENSE
 file.

✍ Acknowledgment

This repository’s structure, documentation, and design were drafted utilizing conventional digital design practices. A minor portion of the documentation text was refined using AI-based tools for clarity and polish; all hardware logic, Verilog code, simulation frameworks, and overall architecture are original work of the author.
