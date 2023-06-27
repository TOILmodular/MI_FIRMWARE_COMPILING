# Compiling Procedure for Mutable Instruments Eurorack Module Firmware
## Introduction
This repository is meant to help anyone who would like to build their own Mutable Instruments Eurorack module clones, but does not know how to create .hex files out of the open-source firmware.

Émilie Gillet (Mutable Instruments) provides details about how to install and use virtual machine tools for the procedure. 
But from my own experience, being not really an IT nerd, it was difficult to follow that procedure only with the provided information.

So I found a different way to create .hex files for any of the available modules (except Beads, for which the source code is not published), which I want to share here. The procedure of how to program the microprocessor with the created .hex file is described in my other repositories and in YouTube videos (links in the README files of the module repositorie, e.g. Plaits).

The goal of this repository is to provide enough information, so that anyone without any specific knowledge or prerequisit can follow and execute the procedure.

## Step 1: Get the MI Source Code
