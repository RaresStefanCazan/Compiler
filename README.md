# Compiler Project

This project implements a compiler using Lex for lexical analysis, Bison for parsing, and C++ for additional functionality (such as identifier management). It is designed to demonstrate how to build a basic compiler using these classic tools.


## Prerequisites

Make sure you have the following installed on your system:
- **Flex** – For lexical analysis.
- **Bison** – For parser generation.
- **G++/GCC** – To compile the generated and C++ source files.
- **Bash** – To run the provided shell script.

## Building the Compiler

A build script (`compile.sh`) is provided to automate the compilation process. The script takes a single argument which represents the prefix of your grammar files.

For example, if you want to compile the `expr` grammar, run:

```bash
./compile.sh expr
```

This script will:

- Remove any previously generated files (such as `lex.yy.c`, `expr.tab.c`, and `expr.tab.h`).
- Run Bison on the corresponding `expr.y` file to generate the parser.
- Run Flex on the corresponding `expr.l` file to generate the lexical analyzer.
- Compile the generated C files using `g++` and produce an executable named `expr`.

You can repeat the process for other grammars (e.g., `limbaj`) by running:

```bash
./compile.sh limbaj
```

## Running the Compiler

After building, you can run the generated executable with your test input. For example:

```bash
./expr < tests/in.txt
