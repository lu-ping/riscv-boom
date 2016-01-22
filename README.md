The Berkeley Out-of-Order RISC-V Processor
================================================

This is the source repository for the RV64G RISC-V superscalar Berkeley Out-of-Order Machine (BOOM), 
written in the [Chisel hardware construction language](http://chisel.eecs.berkeley.edu). BOOM 
is a synthesizable core that targets ASIC processes. It can run on an FPGA (50 MHz on a zc706), 
but optimizing it to be an FPGA soft-core is a non-goal.


 Feature | BOOM
--- | ---
ISA | RISC-V (RV64G)
Synthesizable |√
FPGA |√
Parameterized |√
Floating Point (IEEE 754-2008) |√
Atomic Memory Op Support |√
Caches |√
Viritual Memory |√
Boots Linux |√

**Google group:** (https://groups.google.com/forum/#!forum/riscv-boom)

For documentation on BOOM visit (https://ccelio.github.io/riscv-boom-doc).

The [wiki](https://github.com/ucb-bar/riscv-boom/wiki) may also have more information. 

**Important!**

This repository is **NOT A SELF-RUNNING** repository. To instantiate a BOOM core, please use the Rocket chip generator found in the rocket-chip git repository (https://github.com/ucb-bar/rocket-chip).

BOOM depends on the Chisel project. It also depends on [Rocket](https://github.com/ucb-bar/rocket), [uncore](https://github.com/ucb-bar/uncore), and [junction](https://github.com/ucb-bar/junctions) source codes.


**Requirements**

These instructions assume you have already installed the [riscv-tools](https://github.com/riscv/riscv-tools) toolchain.

If you have not, follow additional instructions below.


**Directions**

To build a BOOM C++ emulator and run BOOM through a couple of simple tests:

````
   $ export ROCKETCHIP_ADDONS="boom"
   $ git clone https://github.com/ucb-bar/rocket-chip.git
   $ cd rocket-chip
   $ git checkout boom
   $ git submodule update --init
   $ cd riscv-tools
   $ git submodule update --init --recursive riscv-tests
   $ cd ../emulator; make run CONFIG=BOOMCPPConfig
````
 
**Installing the RISC-V Toolchain**

The following (modified) instructions will also build the RISC-V toolchain (if
you have not already do so). You will need to set the $RISCV environment
variable (where the toolchain will be installed) and you will need to add
$RISCV/bin to your $PATH.

````
   $ export RISCV=/path/to/install/riscv/toolchain
   $ export PATH="${PATH}:$RISCV/bin"
   $ export ROCKETCHIP_ADDONS="boom"
   $ git clone https://github.com/ucb-bar/rocket-chip.git
   $ cd rocket-chip
   $ git checkout boom
   $ git submodule update --init
   $ cd riscv-tools
   $ git submodule update --init --recursive
   $ ./build.sh
   $ cd ../emulator; make run CONFIG=BOOMCPPConfig
````

For more detailed information on the toolchain, visit 
[the riscv-tools repository](https://github.com/riscv/riscv-tools).


**More Info**

* **The Design Spec** - https://ccelio.github.io/riscv-boom-doc
* **The Wiki** - https://github.com/ucb-bar/riscv-boom/wiki
* **Tech Report** - The Berkeley Out-of-Order Machine (BOOM): An Industry-Competitive, Synthesizable, Parameterized RISC-V Processor (https://www.eecs.berkeley.edu/Pubs/TechRpts/2015/EECS-2015-167.html)
* **Slides** - RISC-V Workshop #2 (http://riscv.org/workshop-jun2015/riscv-boom-workshop-june2015.pdf)
* **Video** - RISC-V Workshop #2 (https://www.youtube.com/watch?v=z8UInbiQbdA)


**Disclaimer!**

The RISC-V privileged ISA and platform specs are still in flux. BOOM will do its best to stay up-to-date with it!

BOOM is a work-in-progress and remains in active development.


**FAQ**

To be filled in as questions are asked...
