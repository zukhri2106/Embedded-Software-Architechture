# 🛠 Tools & Setup (Free & Open Source)

This guide explains how to set up the development environment for this project.
All tools are **free and open source**, and everything works **without real hardware** (using QEMU emulator).

> 🪟 This guide is for Windows 11.  
> Similar tools exist for Linux/macOS; adjust paths accordingly.

---

## ✅ Tools you need

| Tool                        | What it’s for                                  |
| --------------------------- | ----------------------------------------------- |
| QEMU                        | Simulate ARM Cortex-M MCU                      |
| arm-none-eabi-gcc           | Cross-compiler for ARM Cortex-M                |
| arm-none-eabi-gdb          | Debugger (usually comes with the toolchain)    |
| Make / CMake                | Build system                                   |
| VSCode + extensions         | Editor and IDE                                 |
| (Optional) MSYS2 / Git Bash | Unix-like shell tools (rm, cp, etc.)           |

---

## 📦 Step-by-step installation

### 1️⃣ QEMU (emulator)

- Download from [https://qemu.org/download/](https://qemu.org/download/).
- Make sure you choose a build **with ARM support** (includes `qemu-system-arm.exe`).
- Extract and add to your system `PATH`.

✅ **Verify**  
```bash
qemu-system-arm --version
````

---

### 2️⃣ Arm toolchain (compiler + debugger)

* Download from official Arm site:
  👉 [Arm GNU Toolchain Downloads](https://developer.arm.com/downloads/-/arm-gnu-toolchain-downloads)
* Choose: `x86_64 Windows hosted cross toolchain`
* Installer will ask: *Add to PATH* → ✅ yes.

✅ **Verify**

```bash
arm-none-eabi-gcc --version
arm-none-eabi-gdb --version
```

---

### 3️⃣ Build system

#### 🛠 Option A: Make

* Easiest: Install via Chocolatey

  ```bash
  choco install make
  ```
* Or install [GnuWin32 Make](http://gnuwin32.sourceforge.net/packages/make.htm).
* Or use [MSYS2](https://www.msys2.org/) (recommended, gives Unix tools).

✅ **Verify**

```bash
make --version
```

#### 🛠 Option B: CMake

* Download installer: [https://cmake.org/download/](https://cmake.org/download/)
* Check *“Add CMake to system PATH”* during install.

✅ **Verify**

```bash
cmake --version
```

---

### 4️⃣ VSCode & extensions

Install VSCode from [https://code.visualstudio.com/](https://code.visualstudio.com/)

Inside VSCode → Extensions (Ctrl+Shift+X):

* ✅ C/C++ (by Microsoft)
* ✅ Cortex-Debug
* (Optional) Makefile Tools

---

### 5️⃣ (Optional) MSYS2

MSYS2 provides Unix-like tools (`rm`, `cp`, `mkdir`, etc.) on Windows:

* [https://www.msys2.org/](https://www.msys2.org/)

---

## ⚙️ Quick test checklist

Open Command Prompt / PowerShell and run:

```bash
qemu-system-arm --version
arm-none-eabi-gcc --version
arm-none-eabi-gdb --version
make --version      # if using make
cmake --version     # if using cmake
```

If all print version info → ✅ setup complete.

---

## 🧪 Next steps

* Create workspace folder:

```
embedded-architecture/
└── stage-1-foundation/
    ├── module-1.1-c-basics/
    ├── module-1.2-bare-metal-project/
    └── ...
```

* Configure VSCode (launch.json & tasks.json) — see separate guide.

---

## ✏️ Document decisions

Keep this file updated if you:

* Change compiler versions
* Switch to different emulator
* Add new tools

---

## 📚 References

* [QEMU ARM wiki](https://wiki.qemu.org/Documentation/Platforms/ARM)
* [GNU Arm Embedded Toolchain docs](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm)
* [CMake](https://cmake.org/)
* [Cortex-Debug extension](https://marketplace.visualstudio.com/items?itemName=marus25.cortex-debug)

---

