# Elevator_verilog

Smart Elevator Control System (Verilog FSM)

This project implements a 4-Floor Smart Elevator Controller in Verilog HDL, using a Finite State Machine (FSM) for request handling, movement control, and door operations.
The design is developed and simulated in Xilinx Vivado with a full Verilog testbench.

 Features

Supports 4 floors (0 → 3).

Handles upward and downward movement.

Door operation logic: opens when the elevator reaches a requested floor.

Request handling for multiple floors.

Designed as a Finite State Machine (FSM) with states:

IDLE

MOVE_UP

MOVE_DOWN

OPEN_DOOR

 Tools & Environment

HDL: Verilog

Simulator: Xilinx Vivado (Behavioral Simulation)

Target: FPGA (Basys 3 / Nexys / Any Xilinx board)

 Project Structure
Smart-Elevator-Controller/
│
├── elevator_controller.v       # Main Verilog HDL module (FSM design)
├── tb_elevator_controller.v    # Testbench for simulation
├── simulation_waveform.png     # Example Vivado simulation output
└── README.md                   # Documentation (this file)

⚙️ How It Works

Elevator starts at floor 0 after reset.

Request signal (request[3:0]) is set high for the desired floor:

Example: request = 4'b0100 → request floor 2.

FSM checks:

If request is at the current floor → open door.

If request is above → move up until floor is reached.

If request is below → move down until floor is reached.

When elevator reaches the requested floor → door opens for one cycle.

FSM returns to IDLE until a new request is received.

▶ Simulation Procedure in Vivado

Open Vivado → Create Project → Add elevator_controller.v and tb_elevator_controller.v.

Set tb_elevator_controller as top module for simulation.

Run Behavioral Simulation.

Observe waveforms:

floor changes as elevator moves.

moving_up / moving_down indicate direction.

door_open goes HIGH at requested floor.



