## 🌱 **Stage 1: Foundation**

> ✅ Goal: Build strong low-level embedded knowledge — master C, understand how MCU starts up, memory maps, build flow, and get comfortable debugging and running code *without hardware*.

---

### 📦 Tools & setup (all free / open source)

* **Compiler:** `arm-none-eabi-gcc` (or Clang)
* **Emulator:** [QEMU](https://www.qemu.org/) with Cortex-M support
* **Debugger:** `gdb` (integrated in VSCode)
* **Build:** Make or [CMake](https://cmake.org/)
* **Editor:** VSCode + Cortex-Debug extension
* **Reference MCU:** Cortex-M3/M4 (common, widely documented)
* **Docs:** ARMv7-M Architecture Reference Manual, ARM CMSIS headers

---

### 🧰 **Module 1.1: C language essentials for embedded**

✅ Learning:

* Fixed-width types: `uint8_t`, `uint16_t`, etc.
* Volatile, const, static (and why `volatile` matters)
* Bitwise operations, masks, shifting
* Structs and unions for peripheral registers

🛠 Practical:

* Implement register bit manipulation macros
* Write a small module to toggle a “virtual” LED (a memory bit)

---

### ⚙️ **Module 1.2: Bare-metal project structure**

✅ Learning:

* Understand build flow: compiler → assembler → linker → binary
* What are `.text`, `.data`, `.bss` segments
* How a linker script places code and data in memory

🛠 Practical:

* Create a bare project: `main.c`, `startup.s`, `linker.ld`
* Write your own minimal linker script (place vector table at address 0x00000000)
* Build with `make` or `cmake`

---

### 🧪 **Module 1.3: Startup & Reset**

✅ Learning:

* Vector table, reset handler, interrupt handlers
* Stack setup
* Zeroing `.bss` and copying `.data` on startup

🛠 Practical:

* Write a startup assembly file:

  * Define vector table
  * Implement reset handler that calls `main()`
* Verify vector table layout in the ELF file (`objdump -h`)

---

### 🧰 **Module 1.4: Simulate on QEMU**

✅ Learning:

* How to run firmware without hardware
* Understand output formats: ELF, BIN, HEX
* Basic GDB debugging

🛠 Practical:

* Build `blink.elf` and run on `qemu-system-arm` (e.g., `-M lm3s6965evb`)
* Use GDB to:

  * Step through `main`
  * Inspect memory and registers
* Simulate toggling GPIO by writing to known addresses (even if no real LED)

---

### 🔍 **Module 1.5: Low-level debugging**

✅ Learning:

* Breakpoints, watchpoints
* Inspect stack, memory
* Understand exception vectors

🛠 Practical:

* Set breakpoints in `main` and interrupt handlers
* Use watchpoints to track memory changes (e.g., GPIO register)
* Observe stack pointer changes during interrupts

---

### 🧩 **Module 1.6: Memory map & peripheral registers**

✅ Learning:

* Understand memory regions: Flash, SRAM, peripheral space
* How to define peripheral structs in C
* Use CMSIS headers

🛠 Practical:

* Define a `struct` mapping to a fake GPIO peripheral base address
* Access fields to set/clear bits
* Use QEMU to see what happens when you write to these addresses

---

## 🏁 **Stage 1 milestones**

✅ Compile and run minimal firmware on QEMU
✅ Write your own startup file & linker script
✅ Step through code in GDB
✅ Document architecture & memory map
