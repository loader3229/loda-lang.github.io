---
layout: page
title: Installation
permalink: /install/
nav_order: 2
---

The LODA command-line tool lets you explore, evaluate, and mine programs for integer sequences. It’s available for Linux, macOS, and Windows. Follow the instructions below to get started on your platform.

> **Tip:** If you only want to contribute compute power for program mining, you can join the [LODA project on BOINC](https://boinc.loda-lang.org/loda/) and skip manual installation.

## 🚀 Quick Install (Linux & macOS)

Make sure you have [git](https://git-scm.com/) installed. Then run this command in your terminal:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/loda-lang/loda-cpp/main/install.sh)"
```

This will download and install the latest LODA release and set up your environment.

## 🪟 Windows Installation

1. Install [Git for Windows](https://git-scm.com/download/win).
2. Open the **Git CMD** app from your Start menu.
3. Run these commands:

```
md "%USERPROFILE%\loda\bin"
cd "%USERPROFILE%\loda\bin"
curl -fsSLo loda.exe https://github.com/loda-lang/loda-cpp/releases/latest/download/loda-windows.exe
loda setup
```

This will download the LODA executable and guide you through the initial setup.

## 🏁 Getting Started

Try evaluating a classic sequence! For example, to compute the Fibonacci numbers:

```bash
loda eval A000045
```

To start mining for new or better programs:

```bash
loda mine         # Single core
loda mine -p      # Multi-core (parallel)
```

For a full list of commands and options, run `loda --help` or see below:

```
Usage: loda <command> <options>

Commands:
  eval      <program>  Evaluate an integer sequence program (see -t,-b,-s)
  check     <program>  Verify correctness of an integer sequence program (see -b)
  mine                 Mine programs for integer sequences (see -i,-p,-P,-H)
  submit  <file> [id]  Submit an integer sequence program to the central repository
  export    <program>  Export a program and print the result (see -o,-t)
  optimize  <program>  Optimize a program and print the result
  minimize  <program>  Minimize a program and print the result (see -t)
  profile   <program>  Measure program evaluation time (see -t)
  fold <program> <id>  Fold a subprogram given by ID into a seq-operation
  unfold    <program>  Unfold the first seq-operation of a program
  mutate    <program>  Mutate a program to mine for integer sequences
  setup                Run interactive setup to configure LODA
  update               Update integer sequence and program data
  upgrade              Check for and install the latest LODA version

Targets:
  <file>               Path to a LODA file (file extension: *.asm)
  <id>                 ID of an integer sequence (example: A000045)
  <program>            Either an <file> or an <id>

Options:
  -t <number>          Number of sequence terms (default: 8)
  -b                   Print result in the OEIS b-file format
  -o <string>          Export format (formula,loda,pari,range)
  -d                   Export with dependencies to other programs
  -s                   Evaluate program and return number of execution steps
  -c <number>          Maximum number of execution steps (no limit: -1)
  -m <number>          Maximum number of used memory cells (no limit: -1)
  -z <number>          Maximum evaluation time in seconds (no limit: -1)
  -l <string>          Log level (values: debug,info,warn,error,alert)
  -i <string>          Name of miner configuration from miners.json
  -p                   Parallel mining using default number of instances
  -P <number>          Parallel mining using custom number of instances
  -H <number>          Number of mining hours (default: unlimited)
```

## 🔄 Upgrading & Setup

To upgrade to the latest version, run:

```bash
loda upgrade
```

To reconfigure your installation at any time, run:

```bash
loda setup
```

## ❓ Need Help?

- See the [LODA documentation](/spec) for language details.
- Visit the [LODA Discord](https://loda-lang.org/discord) for help and discussion.
- Report issues or contribute improvements on [GitHub](https://github.com/loda-lang/loda-cpp).

Happy mining and exploring integer sequences with LODA!
