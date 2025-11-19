# My projects on GitHub

This document is primarily intended for potential employers and anyone who wants to quickly understand what I do as a developer.

On GitHub I publish my open tools, utilities, and experimental projects that reflect my technical interests outside of my main job.

## **TL;DR:**

* 12+ open-source projects
* specialization: C/C++, systems programming, build systems, OpenGL
* developing a modular 2D game engine (~18k LOC)
* created reusable CMake infrastructure for multiple projects
* wrote a Unicode library with almost 100% test coverage
* developed automation tools for complex C/C++ environments

## Table of contents

* [Key libraries and tools](#key-libraries-and-tools)

  * [libuc](#libuc) — library for working with strings in Unicode encodings
  * [cmake_barebones](#cmake_barebones) — reusable CMake library for build configuration
  * [vgazer](#vgazer) — tool for deploying environments and dependencies for C/C++ projects
* [Test assignments](#test-assignments)

  * [gallery](#gallery) — simple Qt application for viewing images
  * [match3](#match3) — console Match-3 game in Lua
  * [slot_machine](#slot_machine) — slot-machine game prototype in C++
  * [angles](#angles) — “Checkers”-style board game with an AI opponent and OpenGL rendering
  * [test_task_for_radiofid](#test_task_for_radiofid) — demonstration of systems programming in Linux
  * [test_task_for_dsp_labs_bot](#test_task_for_dsp_labs_bot) — Telegram bot with image and voice-message processing
* [Experiments and learning projects](#experiments-and-learning-projects)

  * [samples](#samples) — collection of experimental subprojects and samples
  * [ebnf_ini](#ebnf_ini) — grammar parsing based on EBNF notation
  * [steroids](#steroids) — 2D game engine with modular architecture

---

## Key libraries and tools

### libuc

**Repository:** [https://github.com/edomin/libuc](https://github.com/edomin/libuc)
**Category:** Core library

**🛠 Tech stack:** C, GNU Make, CMocka, CMake, Doxygen
**👤 Role:** Author and sole developer

**📘 Short description**
Utility library for working with strings in UTF-8, UCS-2, and UCS-4 (UTF-32) encodings, and for converting strings between these encodings.

**Why:** simplifies working with Unicode strings in C projects where heavy dependencies are not an option, but you still need reliable text handling and predictable memory usage.

**⭐ Highlights / What I’m proud of**

* Almost full test coverage of the code
* Comprehensive documentation for the public library API

**🔍 Technical details**
Optimized for easy integration, does not require dynamic memory, minimal dependencies.

**📦 Usage in other projects**
Used in projects for preparing UTF-8 text for rendering with bitmap/PNG fonts.

**📝 Project status**
Finished; can be used as a utility library when needed.

**📏 Size / scope**

* Code + headers: 4 files, ~430 lines of code
* Unit tests: 26 files, ~1150 lines of code

**🎓 What I learned / takeaways**

* String conversion between different encodings
* Supporting code that compiles with different compilers (gcc, clang, mingw, tcc)
* Writing unit tests using the CMocka framework
* Writing and generating documentation with Doxygen
* Writing changelogs in accordance with the “Keep a Changelog” convention

---

### cmake_barebones

**Repository:** [https://github.com/Survival-SDK/cmake_barebones](https://github.com/Survival-SDK/cmake_barebones)
**Category:** Core library

**🛠 Tech stack:** CMake
**👤 Role:** Author and sole developer

**📘 Short description**
CMake library that collects the CMake build logic I used to copy manually from project to project.

**Why:** allows quickly setting up a consistent and strict build system in new C/C++ projects without copy-pasting logic from older repositories.

**⭐ Highlights / What I’m proud of**

* Custom build types: `Coverage` (build with coverage instrumentation), `Lint` (project checks with clang-tidy), and `IWYU` (checks with Include-What-You-Use)
* Compiler flags, header, library, and C type property checks with a focus on readable configure logs (similar in spirit to GNU Autotools configure logs)
* Detection of all available `-W` (warning) flags supported by the compiler, grouped by category, with the ability to enable all warnings in a category with a single command

**🔍 Technical details**
No external dependencies; easy to add to a new project.

**📦 Usage in other projects**
Migrated almost all of my CMake-based projects to use this library. Now build logic improvements are usually made in `cmake_barebones` instead of each project separately.

**📝 Project status**
Actively used and maintained.

**📏 Size / scope**

* ~25 files
* ~2600 lines of CMake code

**🎓 What I learned / takeaways**

* Writing a reusable CMake library
* Deeper understanding of how the CMake build system works

---

### vgazer

**Repository:** [https://github.com/Survival-SDK/vgazer](https://github.com/Survival-SDK/vgazer)
**Category:** Core tool

**🛠 Tech stack:** Python 3, Docker
**👤 Role:** Author and sole developer

**📘 Short description**
Tool for fast deployment of environments required to build C and C++ projects with many external dependencies.

**Why:** reduces routine when preparing environments for C/C++ projects with a large number of dependencies and lowers the risk of “it works on my machine”.

**⭐ Highlights / What I’m proud of**

* Finding and installing up-to-date versions of tools and libraries into an isolated environment

**🔍 Technical details**
The project comes in two forms:

* a library for embedding into other software (it can be used to implement a custom package manager, for example);
* a CLI tool for deploying tools and libraries into an isolated environment.

**📦 Usage in other projects**
Used in projects that require many dependencies to build.

**📝 Project status**
Actively used / maintained; remains experimental in terms of further development.

**📏 Size / scope**

* ~93 files
* ~6500 lines of Python

**🎓 What I learned / takeaways**

* Web scraping using `requests` and `BeautifulSoup`
* Writing scripts for automatic installation and deployment of tools and libraries in Linux environments
* Practical experience in automating the setup of complex environments

---

## Test assignments

### gallery

**Repository:** [https://github.com/edomin/gallery](https://github.com/edomin/gallery)
**Category:** Take-home assignment

**🛠 Tech stack:** Qt 5, CMake
**👤 Role:** Author and sole developer

**📘 Short description**
Take-home assignment for an employer: image viewer application with the ability to switch between files in a directory and adjust image brightness.

**⭐ Highlights / What I’m proud of**

* Small, neat application that solves the task with a minimal amount of code

**🔍 Technical details**
Simple desktop application built with Qt.

**🧪 Assignment details**

* The task was to implement an image viewer in Qt with the ability to switch to the previous/next image in a directory and adjust brightness
* The assignment was completed under tight time constraints

**📝 Project status**
Finished; not developed further after completing the assignment.

**📏 Size / scope**

* 7 files
* ~190 lines of C++/Qt code

**🎓 What I learned / takeaways**

* Working with graphics and image processing in Qt

---

### match3

**Repository:** [https://github.com/edomin/match3](https://github.com/edomin/match3)
**Category:** Take-home assignment

**🛠 Tech stack:** Lua
**👤 Role:** Author and sole developer

**📘 Short description**
Take-home assignment: console Match-3 game with text command input.

**⭐ Highlights / What I’m proud of**

* Implemented an alternative representation of the game board using colored characters, going beyond the minimal requirements of the assignment

**🔍 Technical details**
Cross-platform console application with no external dependencies.

**🧪 Assignment details**

* The task was to write a console Match-3 game in Lua with control via string command input
* Implementation took no more than two days
* As an enhancement, I used ASCII escape sequences to color the pieces, making the game more visually pleasant

**📝 Project status**
Finished; not developed further after completing the assignment.

**📏 Size / scope**

* 15 files
* ~615 lines of Lua code

**🎓 What I learned / takeaways**

* Working with ASCII escape sequences for colored console output

---

### slot_machine

**Repository:** [https://github.com/edomin/slot_machine](https://github.com/edomin/slot_machine)
**Category:** Take-home assignment

**🛠 Tech stack:** C++, CMake, miniaudio, tigr
**👤 Role:** Author and sole developer

**📘 Short description**
Take-home assignment: slot-machine game prototype with graphics and realistic reel simulation.

**⭐ Highlights / What I’m proud of**

* Learned and used the `miniaudio` library for sound playback and added sound effects, even though this wasn’t required by the assignment

**🔍 Technical details**
Lightweight graphical application using minimal third-party libraries.

**🧪 Assignment details**

* The task was to implement a slot-machine game with graphics and a correct simulation of spinning reels
* The work took 4 days
* As an improvement, I added sound via `miniaudio`, even though it was not part of the requirements

**📝 Project status**
Finished; not developed further after completing the assignment.

**📏 Size / scope**

* 49 files
* ~980 lines of C++ code

**🎓 What I learned / takeaways**

* Using the `miniaudio` library for sound playback
* Received detailed code review during the interview, which helped to see the project through the eyes of more experienced developers

---

### angles

**Repository:** [https://github.com/edomin/angles](https://github.com/edomin/angles)
**Category:** Take-home assignment

**🛠 Tech stack:** C++, CMake, OpenGL, GLFW, GLEW, GIMP (exporting images to C arrays)
**👤 Role:** Author and sole developer

**📘 Short description**
Take-home assignment: implementation of a “Checkers”-style board game (“Corners”) with an AI opponent and OpenGL graphics.

**⭐ Highlights / What I’m proud of**

* Developed a lightweight OpenGL renderer with batching, optimized for interactive graphics
* Fully working AI opponent

**🔍 Technical details**
Custom OpenGL renderer, minimal reliance on external tools, manual control over graphics.

**🧪 Assignment details**

* The task was to implement the board game “Corners” with a working AI opponent
* There were restrictions on graphics libraries/frameworks: only hge, SDL2, or OpenGL were allowed
* Implementation took 11 days
* To simplify resource loading, I used GIMP’s ability to export images as C arrays, which removed the need to write a custom image loader

**📝 Project status**
Finished; not developed further after completing the assignment.

**📏 Size / scope**

* 70 files
* ~2500 lines of C++ code

**🎓 What I learned / takeaways**

* Working with modern C++
* Implementing a simple OpenGL renderer
* Using the “state machine” pattern
* Implementing a basic AI
* Practical use of GIMP for exporting images to C arrays and working with them in code

---

### test_task_for_radiofid

**Repository:** [https://github.com/edomin/test_task_for_radiofid](https://github.com/edomin/test_task_for_radiofid)
**Category:** Take-home assignment

**🛠 Tech stack:** C, GNU Make, Linux
**👤 Role:** Author and sole developer

**📘 Short description**
Take-home assignment to demonstrate Linux programming skills: working with system calls, syslog, sockets, pipes, and threads.

**⭐ Highlights / What I’m proud of**

* Met all assignment requirements cleanly without unnecessary complexity

**🔍 Technical details**
No external dependencies; direct use of Linux system APIs.

**🧪 Assignment details**

* The task description is documented in detail in the repository README
* Two days were allocated for implementation

**📝 Project status**
Finished; not developed further after completing the assignment.

**📏 Size / scope**

* 4 files
* ~250 lines of C code

**🎓 What I learned / takeaways**

* Systematized and clearly demonstrated my existing Linux programming skills

---

### test_task_for_dsp_labs_bot

**Repository:** [https://github.com/edomin/test_task_for_dsp_labs_bot](https://github.com/edomin/test_task_for_dsp_labs_bot)
**Category:** Take-home assignment

**🛠 Tech stack:** Python 3; libraries: `telebot`, `face_recognition`
**👤 Role:** Author and sole developer

**📘 Short description**
Take-home assignment: Telegram bot that tracks and saves images with faces and voice messages from a chat, and then exports accumulated data on command.

**⭐ Highlights / What I’m proud of**

* Implemented a working Telegram bot with media content processing

**🔍 Technical details**
Direct use of libraries for working with the Telegram API and face recognition.

**🧪 Assignment details**

* The task was to implement a bot that saves all incoming images containing faces and all voice messages, and then exports the saved data on command
* The assignment was done under tight deadlines

**📝 Project status**
Finished; not developed further after completing the assignment.

**📏 Size / scope**

* 11 files
* ~180 lines of code

**🎓 What I learned / takeaways**

* Writing a simple Telegram bot in Python
* Setting up and purchasing hosting
* Deploying the bot to a server

---

## Experiments and learning projects

### samples

**Repository:** [https://github.com/edomin/samples](https://github.com/edomin/samples)
**Category:** Experiment

**🛠 Tech stack:** C, awk, inih, ketopt, libsir, xmempool
**👤 Role:** Author and sole developer

**📘 Short description**
Collection of small experimental subprojects and samples, grouped in a single repository.

**⭐ Highlights / What I’m proud of**

* Implemented a working critical error handler with stack trace output

**🔍 Technical details**
Several independent subprojects combined in one repository.

**📝 Project status**
Experimental; updated when new ideas appear.

**🎓 What I learned / takeaways**

* Deepened experience with the C tooling ecosystem (INI parsing, command-line option parsing, logging, memory pools)
* Implemented a critical error handler with stack trace generation, improving program diagnosability
* Used awk and helper utilities in non-trivial scenarios

---

### ebnf_ini

**Repository:** [https://github.com/edomin/ebnf_ini](https://github.com/edomin/ebnf_ini)
**Category:** Experiment

**🛠 Tech stack:** C
**👤 Role:** Author and sole developer

**📘 Short description**
Experiment in implementing parsing of certain grammar constructs described in EBNF notation.

**Why:** to explore parser construction based on formally described grammars and to improve my skills in syntax analysis.

**⭐ Highlights / What I’m proud of**

* Practical implementation of a parser that processes text based on an EBNF grammar

**🔍 Technical details**
Small project focused on grammar parsing and validating the approach.

**📝 Project status**
Experimental; not developed further after the initial implementation.

**📏 Size / scope**

* Code: 6 files, ~520 lines
* Tests: 1 file, ~480 lines

**🎓 What I learned / takeaways**

* Describing grammars using EBNF notation
* Implementing parsing for grammars defined in EBNF

---

### steroids

**Repository:** [https://github.com/Survival-SDK/steroids](https://github.com/Survival-SDK/steroids)
**Category:** Experiment

**🛠 Tech stack:** C, GNU Make, CMake, Docker, distrobox, XLib, OpenGL, EGL, linear algebra, libpng, stb_image, inih
**👤 Role:** Author and sole developer

**📘 Short description**
2D game engine with modular architecture written in C.

**Why:** used as a platform for experiments with engine architecture, plugin systems, and low-level graphics, as well as a framework for prototyping games (including Ludum Dare entries).

**⭐ Highlights / What I’m proud of**

* Hand-written OpenGL renderer
* Window and OpenGL context creation via EGL and XLib without high-level libraries
* Custom object-oriented model implemented in C
* Plugin-based modular architecture

**🔍 Technical details**
Modular (plugin-based) architecture, low-level work with graphics and windowing.

**📦 Usage in other projects**
Used once in a Ludum Dare hackathon; generally remains an experimental platform.

**📝 Project status**
Maintained; remains an experimental game engine.

**📏 Size / scope**

* 214 files
* ~18,300 lines of C code

**🎓 What I learned / takeaways**

* Building modular applications based on plugins
* Creating windows and OpenGL contexts without high-level libraries
* Implementing 2D vector and matrix arithmetic
* Applying object-oriented approaches in C
* Binding C functions to Lua via LuaJIT FFI
* Creating Lua modules in C
* Using distrobox to run graphical applications in an isolated environment

---

I’m primarily interested in roles related to systems programming in C/C++, tooling development, build infrastructure, or low-level graphics.
