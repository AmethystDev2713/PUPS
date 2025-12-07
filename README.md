# PUPS
## People’s Universal Programming Standard
Created on 12/6/2025 at 8:00 PM UTC.

Copyright (c) 2025 AmethystDev2713. All rights reserved. Pending licensing.

# What is this?
Programming languages used today are great, but there is one small problem I've taken note of: they're only useable on the most common platforms, for the most part, as in Windows, Mac, and Linux, along with some unique cases like the CC65 project which includes a compiler for C to 6502 assembly, and some C to Z80 assembly programs out there.

Why is this a problem? With more and more hobbyists creating their own computers, whether a proof of concept 4-Bit or something actually useable like the [Astro-8 by Sam Astro](https://github.com/sam-astro/Astro8-Computer), they find themselves having to program in assembly. If you don't want to program in assembly, you can do what Astro did and make your own higher level language for your project, or you can use PUPS.

PUPS is aimed at being a language designed to be simple, powerful, and most importantly, universally targetable, meaning it can be compiled for literally any platform out there. Give it your assembly and translation steps once, and compile from then on (as long as you save the necessary files).

# Goals for version 1
- Create a fully useable and functional programming language, based off of JavaScript syntax
- Be compiled using a macro assembler style web app, as that's the easiest type of compiler/assembler to make
- Have the ability to load and use multiple "compiler profiles", which are a set of files telling the compiler what set of instructions from your project's assembly language translate to every type of instruction in PUPS
- Include some built in compiler profiles for common hobbyist platforms.
- Provide a simple virtual machine for testing PUPS, especially useful if you don't have a custom project available but are still curious about using PUPS.

## Built in compiler profiles
This will be updated as the software is developed. Currently planned are the following:
- PUPS Virtual Machine (PVM)
- 6502 (You must provide STDIO)
- 65C02 (You must provide STDIO)
- Ben Eater's 6502 Computer

## How to set up a compiler profile
This will be updated as the software is developed. For now, be ready to provide these:
- Macro list (all PUPS instructions are provided via a template, you fill in the assembly for each instruction)
- STDIO (Your kernel or BIOS, or whatever code file, in assembly or PUPS, that contains I/O functions for your project. Again, templates will be provided, don't forget to put a return from subroutine or equivalent assembly at the end of your fill in! You strictly only need to define the functions you plan to use in your code, but can be a good excersize to fill in everything)
- Compilation Configuraton (A JSON file with settings for integer size, value being number of bits; start of RAM zones by address and their size in bytes; start of ROM address and size)

## PVM Details
This will be updated as the software is developed.

This will be a simple emulator, starting off with being able to execute compiled code like any computer or VM, and provide simple but comfortably useable I/O interfaces, like a keyboard input register, screen output register, and the screen itself, If you are developing for the PVM, you will not need to set up a compiler profile, as that is built in.