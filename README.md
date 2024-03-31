# Hi, I'm Will Wang, this is intro page for Pixel War! 
<p>Software Enginner at <a href="https://www.engineering.utoronto.ca/">University of Toronto</a></br></p>

### A little more about me and the software...  

```javascript
const Pixel_War = {
  name: "Pixel_War",
  code: [C, Python, HTML, CSS],
  tools: [Git, Redux, Docker],
  take_away: "Give it a try"
}
```
# Release Version Pixel_War 1.4.0.050123_Release
The official release of Pixel War is here, bringing the ultimate battle for survival to all players. Experience the full spectrum of combat as your pixel warrior faces the fiercest opponents in newly added survival arenas. This version introduces a polished user interface, optimized performance for seamless gameplay, and the final touches to warrior growth and enemy AI. It's time to test your skills

# Beta Version Pixel_War 1.3.0.042923_Beta
Our beta release comes with significant improvements over the alpha. Enhanced combat behavior makes predators smarter and more challenging, providing a thrilling experience for seasoned players. We've included additional survival arenas for testing, each with its unique obstacles and power-ups. The pixel warrior's growth algorithm has been fine-tuned for a smoother scaling of difficulty. This beta version aims to gather more extensive player feedback and iron out any remaining issues before the final release.

# Alpha Version Pixel_War 1.2.0.042423_Alpha
In this alpha update, we've introduced new challenging elements to enhance the game's core mechanics. Players will find new types of enemies that require different strategies to defeat. We've also implemented preliminary work for new survival arenas that will be fully realized in future updates. This version focuses on refining the balance and collecting player feedback to adjust difficulty curves. Known for its rapid gameplay, we encourage players to explore different tactics to prolong survival.

# Pixel_War 1.1.1.032123_Alpha
In this game, players control a giant pixel warrior that moves around, fighting weaker warriors to grow bigger and stronger. The objective is survival for as long as possible while avoiding being beaten. As the player's warrior grows, it becomes larger, attracting the attention of larger, more dangerous predators. The game is fast-paced and addictive, constantly challenging players to adapt their strategy and survive against increasingly difficult odds.

Note: To demonstrate the functionality in <a href="https://cpulator.01xz.net/">CPUlator</a>, the character are adjusted in a pixel shape to better perform in a limited performance online CPU. Fully functioned character drawing can only display properly on DE1-Soc 

⚠️注意：<a href="https://cpulator.01xz.net/">CPUlator</a>，只能使用像素正方形来模拟真正的游戏角色，全显示的游戏角色只能在DE1-Soc FPGA开发板上完美运行

<img width="1547" alt="截屏2023-03-29 04 23 20" src="https://user-images.githubusercontent.com/105031962/228472663-8a8b6230-857d-4a63-adea-32ff669050e6.png">

## Table of Content
- Game Rules
- Game Algorithm & Tech
- About FPGA(DE1-Soc)
- About <a href="https://cpulator.01xz.net/">CPUlator</a>


## Game Rules
In this game, the program will be based on FPGA board(DE1-Soc) using ARM processor. The program will read input from KEYs and PS/2 Keyboard to control the movement of the character. The gamer will have to fight(Contact) with other warriors and beat them to grow larger in size. The longer that user survive, the higher score he or she will get.

## Game Algorithm & Tech
This games implemented mutiple algorithm and technologies to build a fun & challenging game;
In draw/calculating curve line route, the developer implemnted the Bresenham Line algorithm in this project to calculate the best character movement path drawing method at different resolutions.

## Techs and I/O Devices

- Logic Instructions
- Memory-Mapped Output
- Mapped I/O
- Polling I/O
- A9 Private Timer
- Timer Interrupt Bits and Clearing Interrupt Bits
- Double Buffering
- VGA output

## I/O Device Using:
1. Switches: `SW[1:0]`
2. Push Buttons: `KEY[3:0]`
3. Seven-Segment Displays: `HEX[6:0]`
4. LEDs: `LED[7:0]`
5. A9 Private Timer
6. VGA Output
7. PS/2 Keyboard
8. Audio Output

## About FPGA(DE1-Soc)
"FPGA stands for Field Programmable Gate Array, which is an integrated circuit that can be programmed and reprogrammed by the user after manufacturing. The DE1-SoC is a specific type of FPGA board designed by Terasic that integrates a wide range of features and components, including a Cyclone V FPGA chip from Intel, a HPS (Hard Processor System) based on an ARM Cortex-A9 dual-core processor, various types of memory, audio and video interfaces, and many other peripherals."

## About CPUlator
CPUlator is a computer software program that simulates the behavior of a Central Processing Unit (CPU) and provides a platform for testing and debugging code that runs on the CPU. It is designed to be a simple, lightweight, and easy-to-use tool that allows users to quickly prototype and test code for different CPU architectures.


# Start-Up Procedural

## I. Game Startup

When the game is loaded into the board(or the 因为CPUlator性能限制), the monitor will display the introduction of the game. The user will be required to toggle the SW[0] up and down to start the game's procedural, as Figure shows.<br>

<img width="450" alt="截屏2024-03-31 上午1 57 45" src="https://github.com/Liyourong/Pixel_War_Game/assets/105031962/0b6eeb21-ebcc-4214-a597-2b9862155940">

## II. Instruction Page

This is the introduction page of the game. The user will read the instructions and be required to press "enter" to continue, as Figure shows.

<img width="450" alt="截屏2024-03-31 上午1 58 16" src="https://github.com/Liyourong/Pixel_War_Game/assets/105031962/f56e0f4b-e359-4de2-a168-3e6feff34a17">

## III. Difficulty Selections

Once the user starts the game, the game will require the user to select the difficulties of the game setting. The difficulty setting will affect the countdown of the timer. The greater the difficulties the user selects, the less time they have to play the game. The user could press “E,” “W,” or “Q” to select the difficulties from Hard, Medium, and Easy, as shown in Figure shows.

<img width="450" alt="截屏2024-03-31 上午1 59 59" src="https://github.com/Liyourong/Pixel_War_Game/assets/105031962/793de454-3c5e-47e9-8f2f-f806128872e3">


## IV. Main Game

Once the game starts, a countdown of the game process will display on HEX5[4]. After the countdown started, the user could control the movement of the character by pressing KEY[3] to UP, KEY[2] to Down, KEY[1] to LEFT, and KEY[0] to RIGHT. Once the NPC object is defeated by the main character, there will be a Beep Sound from the Audio output, and the score displaying HEX1[0] will go up, as shown in Figure.

<img width="450" alt="截屏2024-03-31 上午2 00 14" src="https://github.com/Liyourong/Pixel_War_Game/assets/105031962/c97bb2a8-75f8-495d-a022-388f00604dd5">

## V. Game Ending Page

Once the countdown is over, the Game will end with the final points (or “PASSED” if max score) on HEX3[0]. If the user wants to restart the game, they have to press “R” on PS/2 Keyboard and toggle SW[1] to go back to the Game Startup page, as shown in Figure 1.5.

<img width="559" alt="截屏2024-03-31 上午2 01 34" src="https://github.com/Liyourong/Pixel_War_Game/assets/105031962/9497daa8-3059-4f2a-9441-ac8e66e6b6ba">








