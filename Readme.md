# Simon Game on STM32

A memory game built using the STM32F103 microcontroller where players replicate an LED sequence to progress through levels. The game offers interactive gameplay, fun animations, and sequences for success or failure.

## Features

- **Knight Rider Animation**: A dynamic LED pattern runs when the game is idle.
- **Interactive Gameplay**:
  - Replicate randomly generated LED sequences.
  - Levels increase in difficulty as more LEDs are added to the sequence.
- **Failure Sequence**: If the player fails:
  - LEDs blink a specific pattern.
  - The reached level is displayed in binary using the LEDs.
- **Winning Sequence**: Completing all levels triggers a celebratory blinking of all LEDs.
- **Customizable Game**: Easily modify levels, timings, or sequences in the code.

## Hardware Requirements

- **STM32F103 Nucleo Board**
- **4 LEDs**:  
  - **LED1** connected to PA0  
  - **LED2** connected to PA1  
  - **LED3** connected to PA4  
  - **LED4** connected to PB0  
- **4 Push Buttons**:  
  - **Black** connected to PB4  
  - **Red** connected to PB6  
  - **Green** connected to PB8  
  - **Blue** connected to PB9  
- Resistors:
  - 270-ohm for each LED anode.
  - 10k-ohm pull-up resistors for each button.
- **Breadboard and Jumper Wires**
- **Micro-USB Cable**

## Software Requirements

- **Keil uVision** for coding and programming the STM32 board.
- **STM32CubeProgrammer** (optional) for flashing firmware.
- **C Compiler** for STM32 development.

## Game Flow

1. **Idle State**:
   - LEDs perform a Knight Rider sequence.
   - Press the any one of four button to start the game.

2. **Gameplay**:
   - Watch the LED sequence.
   - Press buttons to replicate the pattern:
     - **PB4 (Black)** → LED on PA0 (LED1)
     - **PB6 (Red)** → LED on PA1 (LED2)
     - **PB8 (Green)** → LED on PA4 (LED3)
     - **PB9 (Blue)** → LED on PB0 (LED4)
   - Progress through 10 levels by successfully repeating sequences.

3. **Failure**:
   - Wrong button or timeout triggers:
     - LEDs blink a failure pattern.
     - The score (level reached) is displayed in binary on the LEDs.

4. **Winning**:
   - Complete all 10 levels:
     - All LEDs blink together 4 times.
     - Game resets to idle state.
