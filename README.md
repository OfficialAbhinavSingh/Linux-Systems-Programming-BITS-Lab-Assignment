# 🐧 Linux Systems Programming — BITS Lab Assignment

> **Course**: Operating Systems & Linux Systems Programming  
> **Assignment Type**: Graded Lab Assignment (Modules 5–10)  
> **Total Marks**: 20 (4 marks per question × 5 questions)  

---

## 📋 Project Overview

This repository contains a complete, production-quality solution for the Linux Systems Programming Lab Assignment covering core concepts across Linux development environments:

- **Shell Scripting**: Automated file duplicate detection using MD5 checksums and backup reporting.
- **Process Management**: Multiprocess creation, process monitoring, signal handling (SIGTERM/SIGKILL), and zombie prevention in C.
- **File I/O System Calls**: Low-level Linux system call operations (`open`, `read`, `write`, `lseek`, `close`) for binary record management.
- **Real-Time Log Pipelines**: Non-blocking real-time log analysis and filtering using Unix command pipelines (`tail -f | grep`).
- **Text Editor Crash Recovery**: Detailed technical evaluation of `vi`/`vim` crash recovery mechanisms and swap files.

All implementations adhere strictly to POSIX standards, include comprehensive error checking, clean build configurations (Makefiles), and extensive documentation.

---

## 🎯 Assignment Structure & Rubric

| # | Module / Topic | Core Technical Stack | Marks |
|---|----------------|----------------------|-------|
| **Q1** | Shell Script: Duplicate Detection & Backup | Bash, MD5 Checksums, File I/O | 4 |
| **Q2** | C Program: Process Monitoring & Signals | C11, POSIX `fork()`, `waitpid()`, `kill()` | 4 |
| **Q3** | C Program: Low-Level System Call I/O | C11, `open()`, `read()`, `write()`, `lseek()` | 4 |
| **Q4** | Command Pipeline: Real-Time Log Monitoring | Shell Pipelines, `tail`, `grep`, `awk` | 4 |
| **Q5** | Report: `vi` Crash Recovery Analysis | Technical Documentation & Diagnostics | 4 |
| **Total** | | | **20** |

---

## 📁 Repository Directory Layout

```
Linux-Lab-Assignment/
│
├── README.md                          ← Main project documentation
│
├── Question1/                         ← Shell Script: Duplicate Detection & Backup
│   ├── README.md                      ← Detailed question overview & execution guide
│   ├── duplicate_backup.sh            ← Main shell script (POSIX-compliant)
│   ├── execution_commands.md          ← Command execution steps with explanations
│   ├── explanation.md                 ← Technical design & logic walkthrough
│   ├── outputs.md                     ← Terminal output logs
│   ├── errors.log                     ← Log file for execution errors
│   ├── sample_submissions/            ← Sample dataset (10 files, 3 duplicates)
│   ├── backup/                        ← Destination folder for unique backed-up files
│   ├── reports/                       ← Timestamped execution summary reports
│   └── screenshots/                   ← Visual execution evidence
│
├── Question2/                         ← C Program: Process Monitor & Zombie Prevention
│   ├── README.md
│   ├── process_monitor.c              ← C source code for process controller
│   ├── Makefile                       ← Automated build configuration
│   ├── execution_commands.md
│   ├── explanation.md
│   ├── outputs.md
│   └── screenshots/
│
├── Question3/                         ← C Program: System Call Binary File I/O
│   ├── README.md
│   ├── employee_records.c             ← Low-level C database manipulation
│   ├── employees.dat                  ← Fixed-width binary database file
│   ├── employees_dat_note.txt         ← Data layout specification
│   ├── execution_commands.md
│   ├── explanation.md
│   ├── outputs.md
│   └── screenshots/
│
├── Question4/                         ← Pipeline: Real-Time Log Monitoring
│   ├── README.md
│   ├── sample.log                     ← Multi-level sample log file
│   ├── error_report.log               ← Extracted log findings report
│   ├── monitoring_commands.md         ← Real-time log monitoring pipelines
│   ├── execution_commands.md
│   ├── explanation.md
│   ├── outputs.md
│   └── screenshots/
│
└── Question5/                         ← Technical Report: vi Crash Recovery
    ├── README.md
    ├── vi_recovery.md                 ← In-depth evaluation report
    ├── execution_commands.md
    ├── explanation.md
    ├── outputs.md
    └── screenshots/
```

---

## 🚀 Build & Execution Guide

### Question 1 — Shell Script (Duplicate Detection & Backup)
```bash
cd Question1
chmod +x duplicate_backup.sh
./duplicate_backup.sh
```
*Generates unique file backups in `backup/` and a detailed summary in `reports/`.*

### Question 2 — C Process Controller
```bash
cd Question2
make
./process_monitor
```
*Forks multiple child worker processes, monitors their states, sends signals (`SIGTERM`/`SIGKILL`), and reaps exit statuses using `waitpid()`.*

### Question 3 — Low-Level C File I/O
```bash
cd Question3
gcc -Wall -Wextra -std=c11 employee_records.c -o employee_records
./employee_records
```
*Creates, reads, and updates fixed-size binary records in `employees.dat` using `open`, `read`, `write`, `lseek`, and `close`.*

### Question 4 — Real-Time Log Stream Pipeline
```bash
cd Question4
# Terminal 1: Monitor ERROR logs live as they are appended
tail -f sample.log | grep --line-buffered "ERROR"

# Terminal 2: Simulate writing log entries
echo "[$(date '+%Y-%m-%d %H:%M:%S')] ERROR: Database timeout" >> sample.log
```

### Question 5 — `vi`/`vim` Crash Recovery Analysis
```bash
cd Question5
cat vi_recovery.md
```
*Contains step-by-step instructions for recovering unsaved file edits using swap files (`.swp`) and `-r` recovery flags.*

---

## 💻 Environment & Requirements

- **OS**: Linux / macOS (POSIX compliant)
- **Compiler**: GCC 9+ / Clang with `-std=c11 -D_POSIX_C_SOURCE=200809L`
- **Shell**: Bash 4.0+
- **Utilities**: `md5sum` (or `md5`), `grep`, `tail`, `awk`, `make`, `vim`

---
*Submitted for Operating Systems & Linux Systems Programming Lab Assignment.*
