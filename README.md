# Pixel_War 1.1.1.032123_Alpha
In this game, players control a giant pixel warrior that moves around, fighting weaker warriors to grow bigger and stronger. The objective is survival for as long as possible while avoiding being beaten. As the player's warrior grows, it becomes larger, attracting the attention of larger, more dangerous predators. The game is fast-paced and addictive, constantly challenging players to adapt their strategy and survive against increasingly difficult odds.

Note: To demonstrate the functionality in CPUlator, the character are adjusted in a pixel shape to better perform in a limited performance online CPU. Fully functioned character drawing can only display properly on DE1-Soc 

⚠️注意：因为CPUlator性能限制，只能使用像素正方形来模拟真正的游戏角色，全显示的游戏角色只能在DE1-Soc FPGA开发板上完美运行

<img width="1547" alt="截屏2023-03-29 04 23 20" src="https://user-images.githubusercontent.com/105031962/228472663-8a8b6230-857d-4a63-adea-32ff669050e6.png">

## Table of Content
- Game Rules
- Game Algorithm & Tech
- About FPGA(DE1-Soc)
- About CPUlator


## Game Rules
In this game, the program will be based on FPGA board(DE1-Soc) using ARM processor. The program will read input from KEYs and PS/2 Keyboard to control the movement of the character. The gamer will have to fight(Contact) with other warriors and beat them to grow larger in size. The longer that user survive, the higher score he or she will get.

## Game Algorithm & Tech
This games implemented mutiple algorithm and technologies to build a fun & challenging game;
In draw/calculating curve line route, the developer implemnted the Bresenham Line algorithm in this project to calculate the best character movement path drawing method at different resolutions.

## About FPGA(DE1-Soc)
"FPGA stands for Field Programmable Gate Array, which is an integrated circuit that can be programmed and reprogrammed by the user after manufacturing. The DE1-SoC is a specific type of FPGA board designed by Terasic that integrates a wide range of features and components, including a Cyclone V FPGA chip from Intel, a HPS (Hard Processor System) based on an ARM Cortex-A9 dual-core processor, various types of memory, audio and video interfaces, and many other peripherals."

## About CPUlator
CPUlator is a computer software program that simulates the behavior of a Central Processing Unit (CPU) and provides a platform for testing and debugging code that runs on the CPU. It is designed to be a simple, lightweight, and easy-to-use tool that allows users to quickly prototype and test code for different CPU architectures.








