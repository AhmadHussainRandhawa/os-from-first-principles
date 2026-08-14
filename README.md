<div align="center">

# OS, From First Principles

**A complete, handwritten deep-dive into how Operating Systems actually work** — built for understanding, not memorization.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Format](https://img.shields.io/badge/Format-Handwritten%20%2B%20Diagrams-blue)](#-nature-of-the-notes)
[![Chapters](https://img.shields.io/badge/Chapters-7-informational)](#-scope)
[![Status](https://img.shields.io/badge/Status-Complete-success)](#-access-the-notes)

[Scope](#-scope) · [Preview](#-notes-preview) · [Full Coverage](#-conceptual-coverage) · [Access the Notes](#-access-the-notes) · [Who This Is For](#-who-this-is-for)

</div>

---

## 📖 About

This repository is a complete, handwritten set of notes covering core Operating System concepts — built through **systematic study, cross-referencing, and deep exploration**, organized to reflect how systems actually work internally rather than how a textbook chapter happens to be laid out.

These aren't lecture-slide summaries. Concepts like process synchronization and memory management are explored in genuine depth — the underlying pages for those two sections alone run past 100 pages *each*, because the goal was never to condense a topic down to what's needed for an exam, but to actually understand **why** the mechanism exists before writing down **how** it works.

---

## 📸 Notes Preview

<details>
<summary><b>Click to see sample pages</b></summary>

<br/>

Selected pages from across the notes — a glimpse of the depth and diagram density. Full PDFs are linked below.

<img src="doc/screenshots/01_intro_and_background_6.jpg" width="240" alt="Introduction & Background - Types of OS" />
<img src="doc/screenshots/01_intro_and_background_8.jpg" width="240" alt="Introduction & Background - Architectural requirements for a Multiprogrammed OS" />
<img src="doc/screenshots/01_intro_and_background_13.jpg" width="240" alt="Introduction & Background - Mode Shifting" />
<img src="doc/screenshots/02_process_management_14.jpg" width="240" alt="Process Management - Process" />
<img src="doc/screenshots/02_process_management_15.jpg" width="240" alt="Process Management - Process Structure" />
<img src="doc/screenshots/02_process_management_19.jpg" width="240" alt="Process Management - Process States" />
<img src="doc/screenshots/03_cpu_scheduling_4.jpg" width="240" alt="CPU Scheduling - Diagram" />
<img src="doc/screenshots/03_cpu_scheduling_14.jpg" width="240" alt="CPU Scheduling - FCFS" />
<img src="doc/screenshots/04_process_synchronization_82.jpg" width="240" alt="Process Synchronization - Checking Perfect Sync" />
<img src="doc/screenshots/04_process_synchronization_94.jpg" width="240" alt="Process Synchronization - NASA Mars Pathfinder Problem" />
<img src="doc/screenshots/04_process_synchronization_118.jpg" width="240" alt="Process Synchronization - Dining Philosophers" />
<img src="doc/screenshots/04_process_synchronization_122.jpg" width="240" alt="Process Synchronization - Concurrency Models" />
<img src="doc/screenshots/06_memory_management_171.jpg" width="240" alt="Memory Management - Loading vs Linking" />
<img src="doc/screenshots/06_memory_management_172.jpg" width="240" alt="Memory Management - Unresolved References" />
<img src="doc/screenshots/06_memory_management_177.jpg" width="240" alt="Memory Management - Address Binding" />
<img src="doc/screenshots/06_memory_management_210.jpg" width="240" alt="Memory Management - Hashed Page Table" />
<img src="doc/screenshots/06_memory_management_231.jpg" width="240" alt="Memory Management" />
<img src="doc/screenshots/07_file_management_260.jpg" width="240" alt="File Management - Disk Physical Structure" />
<img src="doc/screenshots/07_file_management_272.jpg" width="240" alt="File Management - Directory Structure" />
<img src="doc/screenshots/07_file_management_294.jpg" width="240" alt="File Management - Case Study: Linux Inode Structure" />

</details>

---

## 🗺️ Scope

This repository covers the full spectrum of fundamental Operating System concepts, in this order:

| # | Chapter | Depth |
|---|---|---|
| 1 | Introduction & System Foundations | Von Neumann architecture, user/kernel mode, OS design philosophy |
| 2 | Process Management | Process-as-ADT, PCB, schedulers, dispatcher, context switching |
| 3 | CPU Scheduling | FCFS, SJF, SRTF, HRRN, LRTF, Priority, Round Robin, Multilevel Queue — with numericals |
| 4 | Process Synchronization | Software/hardware/OS-based mechanisms, classical problems, concurrency models |
| 5 | Deadlocks | Coffman conditions, Resource Allocation Graphs, all four handling strategies |
| 6 | Memory Management | Address binding, linking, paging, segmentation, virtual memory, thrashing |
| 7 | File Management | Disk structure, allocation methods, ext4 & Linux inode case studies |

Each section is developed with detailed explanations, diagrams, and hand-solved numerical problems — not just definitions.

---

## 🧩 Conceptual Coverage

<details>
<summary><b>Click to expand the full chapter-by-chapter breakdown</b></summary>

### 1. Introduction & Background

- What an Operating System really is (beyond definitions)
- Hardware components and system interaction
- Von Neumann Architecture
- Goals and design philosophy of OS
- Types of systems: Uniprogramming vs. Multiprogramming
- User Mode vs. Kernel Mode
- Mode switching and protection mechanisms

### 2. Process Management

- Process abstraction in depth
- Process from a developer's perspective — modeled as an **Abstract Data Type (ADT)**:
  - Definition
  - Representation / Implementation
  - Operations / Methods
  - Attributes / Properties
- Process states and transitions (with detailed diagrams)
- State transition and queueing models
- Process Control Block (PCB) structure and role
- Schedulers: long-term (job), short-term (CPU), medium-term (swapping)
- Dispatcher and context switching

### 3. CPU Scheduling

- Scheduling objectives and performance metrics
- Algorithms implemented and analyzed: FCFS · SJF (preemptive & non-preemptive) · SRTF · burst-time prediction (static vs. dynamic) · HRRN · LRTF · Priority Scheduling · Round Robin · Multilevel Queue Scheduling
- Numerical problem-solving for each algorithm
- Trade-offs: throughput, turnaround time, response time

### 4. Process Synchronization

A deeply explored section covering both theory and mechanisms:

- Independent vs. Cooperating Processes
- Inter-Process Communication (IPC)
- The synchronization problem and why it's necessary
- Conditions for correct synchronization

**Software-based techniques:** Lock variables · Strict alternation · Peterson's Solution · Dekker's Algorithm
**Hardware-based techniques:** Test-and-Set (TSL) · Swap · Compare-and-Swap · LL/SC
**OS-based techniques:** Sleep & Wakeup · Semaphores

**Classical problems:** Producer–Consumer · Reader–Writer · Dining Philosophers

**Concurrency concepts:** Sequential vs. concurrent execution · PARBEGIN/PAREND (COBEGIN/COEND) · process graphs and transformations · Fork and Join models

### 5. Deadlocks

- Coffman Conditions (all four necessary conditions)
- Resource Allocation Graph (RAG)
- Deadlock handling strategies: Prevention · Avoidance · Detection · Recovery · Ignorance (Ostrich approach)

### 6. Memory Management

One of the most detailed sections in the notes:

- CPU–Memory interaction, linear memory model, byte-addressability
- Address binding: compile-time · load-time · execution-time
- Linking: static vs. dynamic
- **Contiguous allocation:** overlays · fixed partitions · variable partitions
- **Non-contiguous allocation:** paging (simple, multilevel, TLB, physical address cache, hashed paging) · segmentation
- **Virtual memory:** demand paging · page replacement algorithms · reference strings · thrashing and its control strategies

### 7. File Management

- Disk structure (physical and logical) and the boot process
- File vs. Directory — a deep comparison
- Directory structures
- File system implementation, allocation methods, free space management, disk scheduling
- **Case studies:** Linux inode structure · ext4 file system

</details>

---

## 📂 Access the Notes

> 📌 **Tip:** open in full screen for best readability.

| Chapter | Link |
|---|---|
| Introduction & Background | [Open PDF](https://drive.google.com/file/d/1vat5ZCSkFStOPTCmRVmgBYPoIDQEji3y/view?usp=sharing) |
| Process Management | [Open PDF](https://drive.google.com/file/d/1SFQJXRQHW8y3lg5t9Ol_7GbkFGe_mPE2/view?usp=sharing) |
| CPU Scheduling | [Open PDF](https://drive.google.com/file/d/1X4UTFSjoGcDyTKbwXPCMDVdmyXMWjvs2/view?usp=sharing) |
| Process Synchronization | [Open PDF](https://drive.google.com/file/d/13Ey1ZN9RDb8TlUxQEMmD6oHm62Z7WgRZ/view?usp=sharing) |
| Deadlock | [Open PDF](https://drive.google.com/file/d/103FiO_v7nVY0MFG5fgK7wQpsEQLcGKj-/view?usp=sharing) |
| Memory Management | [Open PDF](https://drive.google.com/file/d/1PUaVj4aranNXbzCEeg2Zb79qGCuEQTNm/view?usp=sharing) |
| File Management | [Open PDF](https://drive.google.com/file/d/1LzSpb53Sqz13tXDkk2mKzIX4jF2OiMrJ/view?usp=sharing) |
| **Complete Notes** | [Open PDF](https://drive.google.com/file/d/1HHS-uK46RtWdXde-Y2vJ29iYz8UwuW2z/view?usp=sharing) |

---

## 🎓 Who this is for

- **CS/IT students** currently taking an Operating Systems course, looking for notes that explain *why* a mechanism exists, not just its definition
- **Interview prep** — OS concepts (scheduling, synchronization, memory, deadlocks) are recurring systems-design and CS-fundamentals interview topics
- **Self-learners** building systems-level intuition before moving into kernel programming, systems programming, or infrastructure engineering
- Anyone who wants a **revision reference** that's fast to scan but doesn't sacrifice depth

---

## ✍️ Nature of the Notes

- Handwritten and diagram-heavy — built for a way of thinking, not a slide deck
- Focused on **understanding, not memorization**
- Structured to explain **why** things work, not just **how**
- Doubles as both a first-pass learning resource and a fast revision guide

---

## 💬 Acknowledgement

I would like to express my sincere gratitude to my teacher, **Kshitij Sharma**.

If I have to credit one person for my understanding of Operating Systems, it would be him. His teaching played a central role in shaping my clarity on this subject.

---

## ⚖️ License

This project is licensed under the **MIT License** — see [LICENSE](LICENSE) for details.

---

## 📬 Contact

[📧 official.ahmadrandhawa@gmail.com](mailto:official.ahmadrandhawa@gmail.com) · [LinkedIn](https://www.linkedin.com/in/ahmad-hussain-randhawa/) · [GitHub](https://github.com/AhmadHussainRandhawa)

> *"If you have any questions or want to collaborate on something, feel free to email me without any hesitation — I might be a little busy sometimes, but I'll definitely reply."*

---

<div align="center">

⭐ **If these notes helped you understand OS concepts more clearly, a star helps others find them too.**

</div>