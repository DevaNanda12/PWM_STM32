# STM32 PWM LED Fade Demo

## Description
This project demonstrates a simple LED brightness fading effect using PWM (Pulse Width Modulation) on an STM32F4 microcontroller. The PWM signal is generated using TIM2 on channel 1. The duty cycle of the PWM signal gradually increases and decreases in a loop, causing an LED connected to the PWM output pin to smoothly fade in and out.

## Features
- PWM signal generation using TIM2, Channel 1
- Gradual increase and decrease of PWM duty cycle
- LED fade effect using GPIO controlled via hardware timer
- HAL-based STM32 firmware

## Target Hardware
- STM32 Nucleo-F446RE or compatible STM32F4 board

## Peripherals Used
- **TIM2**: Configured for PWM output
- **GPIOA Pin 0 (PA0)** or the pin connected to TIM2_CH1: Outputs the PWM signal to drive an LED

## Project Structure
- `main.c`: Contains system initialization, PWM setup, and main logic loop for LED fading
- `tim.c`: Initializes TIM2 in PWM mode
- `gpio.c`: Initializes GPIO used by TIM2 and the LED
- `main.h`, `tim.h`, `gpio.h`: Header files for configuration and function declarations

## How It Works
1. The system clock is initialized to use HSI.
2. TIM2 is initialized in PWM mode with a period of 255.
3. PWM is started on TIM2 Channel 1.
4. A loop runs indefinitely where:
   - PWM duty cycle is increased from 0 to 255
   - Then decreased from 255 to 0
   - Each change is followed by a short delay for smooth fading

## Build & Flash
1. Open the project in STM32CubeIDE or any compatible toolchain.
2. Connect the STM32 board via ST-Link.
3. Compile and flash the project.
4. Observe the LED connected to the PWM pin fading in and out.

## Notes
- Make sure to connect the LED with an appropriate current-limiting resistor.
- Ensure that TIM2_CH1 is mapped to the correct pin on your board.
- You may modify the delay and step size for faster or slower fade effects.

## Author
Deva Nanda S

