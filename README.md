# Sequential (Registered) Adder Verification using UVM

This repository contains the design and verification of a sequential 4-bit adder. The verification environment is built from scratch using the Universal Verification Methodology (UVM) in SystemVerilog.

---

### Project Overview

This project demonstrates the verification of a sequential (clocked) design. Unlike a simple combinational adder, this DUT includes a clock, a reset, and registers its output, which requires the testbench to manage timing and reset sequences.

-   **DUT**: A 4-bit sequential adder that registers its output on the positive edge of the clock and can be reset asynchronously.
-   **Verification Environment**: A UVM testbench that includes a clock generator, a reset sequence, and timing-aware driver and monitor components.

---

### Folder Structure

A professional folder structure is used to separate design and verification code:

-   `rtl/sequential_adder_design.v`: Contains the Verilog design for the sequential adder and its interface.
-   `tb/sequential_adder_tb.sv`: Contains the complete SystemVerilog/UVM code, including all UVM components and the top-level testbench module which handles clock generation.

---

### Key Verification Components

-   **Clock and Reset**: The top-level testbench (`add_tb`) is responsible for generating the clock and the initial `uvm_config_db` setup. The driver is responsible for initiating and managing the reset sequence for the DUT.
-   **Timing-Aware Driver/Monitor**: The driver and monitor are synchronized with the DUT's clock to drive inputs and sample outputs at the correct time, demonstrating an understanding of verifying sequential logic.
-   **Scoreboard**: The scoreboard logic remains the same, comparing the registered output `y` against the expected sum of the inputs that caused it.

---

### How to Run

To run this simulation, you will need a simulator that supports SystemVerilog and UVM (e.g., Synopsys VCS, Cadence Xcelium, or Mentor Questa/ModelSim).

1.  Compile both `rtl/sequential_adder_design.v` and `tb/sequential_adder_tb.sv`.
2.  Ensure the UVM library is included in your compilation command.
3.  Set `add_tb` as the top-level module for simulation.
4.  Run the simulation. The test will automatically execute and report PASS/FAIL status in the log.
