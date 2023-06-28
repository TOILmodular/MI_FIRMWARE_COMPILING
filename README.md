# Compiling Procedure for Mutable Instruments Eurorack Module Firmware
## Introduction
This repository is meant to help anyone who would like to build their own Mutable Instruments Eurorack module clones, but does not know how to create .hex files out of the open-source firmware.

NOTE! This procedure has been tested and used for MAC OS only. I cannot guarantee, if there is any issue or difference, when trying it with a Windows or Linux OS system.

Émilie Gillet (Mutable Instruments) provides details about how to install and use virtual machine tools for the procedure. 
But from my own experience, being not really an IT nerd, it was difficult to follow that procedure only with the provided information.

So I found a different way to create .hex files for any of the available modules (except Beads, for which the source code is not published), which I want to share here. The procedure of how to program the microprocessor with the created .hex file is described in my other repositories and in YouTube videos (links in the README files of the module repositorie, e.g. Plaits).

The goal of this repository is to provide enough information, so that anyone without any specific knowledge or prerequisit can follow and execute the procedure.

Steps 1-3 only have to be executed once, while steps 4-xxx need to be performed for each individual module.

## Step 1: Get the MI Source Code
1. Navigate to the original [source code](https://github.com/pichenettes/eurorack) for all modules.
2. Download the zipped code by selecting "Download ZIP" from the drop-down list of the the "Code" button.
3. Unzip the data in a local folder of your choice.
4. There are several subfolders in the original code, which are only links to different folders, e.g. folder "stmlib @ e3bd7c9". You will find that those folders are empty in your locally downloaded files. Navigate to those folders separately and download the content of those folders.
5. Unzip the data in to the corresponding folders of your previously downloaded folder struture.

## Step 2: Get the required ARM compilation code
1. Download the zipped code given in this repository by selecting "Download ZIP" from the drop-down list of the the "Code" button.
2. Unzip the data in a local folder of your choice.

## Step 3: Adjust the MI Makefile with the Local ARM Tool Path
1. In the ARM compilation code, navigate to the folder ARM/stmlib.
2. Open file "makefile.inc" with a standard text editor. (TextEdit)
3. Search for the line "TOOLCHAIN_PATH ?= /usr/local/arm/". (first line after the header comments)
4. Change the line by replacing the path with the one of your local folder "ARM". Do not forget to put a "/" at the end. (E.g. "TOOLCHAIN_PATH ?= /Users/John/ARM/")

## Step 4: Adjust the Individual Module Makefiles with the Local ARM Tool Path
1. Navigate to the source code folder for an specific module.
2. Open the file "makefile" in a standard text editor.
3. Search for the line "TOOLCHAIN_PATH ?= /usr/local/arm/".
4. Change the line by replacing the path with the one of your local folder "ARM". Do not forget to put a "/" at the end. (E.g. "TOOLCHAIN_PATH ?= /Users/John/ARM/")
5. Navigate further to the folder "bootloader" of that module.
6. Repeat steps 4-3 and 4-4.
7. You might not always find the line with the tool chain path in the makefiles for each module. In some cases, it is not specified. Then the file does not have to be changed.
