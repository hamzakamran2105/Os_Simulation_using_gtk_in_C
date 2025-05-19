# Os_Simulation_using_gtk_in_C

Based on your project structure from the screenshot, here's a suggested `README.txt` content tailored to your **Operating System Simulator project**. This covers the purpose, structure, task list, compilation, and execution:

---

# Operating System Simulator

**Author**: \Hamza_kamran
**Date**: May 2025

## 🖥️ Project Overview

This Operating System Simulator replicates a basic desktop environment using C and GTK on Linux. It allows users to launch multiple applications (tasks) in separate terminal windows, simulating process management, memory allocation, and inter-process communication (IPC).

Each application is launched as a **separate process** using `fork()` and `exec()`. Tasks communicate with the system for resource requests (RAM, HDD) via IPC. A GTK-based desktop interface acts as the main control panel.

---

## 📁 Project Structure

| File/Folder          | Description                              |
| -------------------- | ---------------------------------------- |
| `main.c`             | Entry point of the OS simulator          |
| `desktop.c/h`        | Handles the desktop UI (GTK based)       |
| `os_simulator`       | Final compiled binary (desktop launcher) |
| `task_manager.c`     | Manages processes and task scheduling    |
| `resource_monitor.c` | Monitors memory and CPU usage            |
| `include/`           | Header files                             |
| `makefile`           | Builds all modules                       |
| `notes.txt`          | Project notes or reminders               |
| `*.c` files          | Individual application/task source code  |

---

## 🧩 Applications/Tasks Available

Each of the following runs as a separate child process:

* `calculator.c` - Basic calculator
* `notepad.c` - Text editor
* `clock.c` - Real-time digital clock
* `calendar.c` - Displays a calendar
* `age_calculator.c` - Calculates age from birthdate
* `factorial.c` - Computes factorial
* `fibonacci.c` - Displays Fibonacci series
* `num_guess.c` - Number guessing game
* `tic_tac.c` - Tic-Tac-Toe game
* `file_creator.c` - Creates files
* `copy_file.c`, `move_file.c`, `delete_file.c` - File operations
* `encrypt.c`, `decrypt.c` - File encryption/decryption
* `beep.c` - Beep sound (if supported)

---

## ⚙️ Compilation Instructions

To compile all components, run:

```bash
make clean && make
```

Or compile individually:

```bash
gcc filename.c -o os_simulator `pkg-config --cflags --libs gtk+-3.0`
```

---

## ▶️ How to Run

Run the desktop simulator with:

```bash
make && make clean
./os_simulator ramSize hardsize no_of_cores
```

Click on any application icon to launch it in a new terminal window.

---

## 📡 Features Simulated

* **Process Creation:** Each task is a separate process (`fork()` + `exec()`).
* **Terminal Separation:** Each task opens in its own terminal window.
* **Resource Management:** RAM and HDD resources monitored and allocated.
* **Scheduling:** Task execution is scheduled and managed by `task_manager`.

---

## 📝 Notes

* Make sure you have GTK installed (preferably GTK 4).
* Works best on Linux/WSL with terminal emulator support (`xterm`, `gnome-terminal`, etc.).
* Run `chmod +x os_simulator` if the binary is not executable.
