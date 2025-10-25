# STM32 PWM Signal Generation using TIM2 (STM32F446RE)

This project demonstrates **PWM (Pulse Width Modulation)** signal generation using **Timer 2, Channel 1** on an STM32F446RE microcontroller.

---

## 🔧 Hardware Setup
- **MCU:** STM32F446RE (Nucleo Board)
- **PWM Output Pin:** PA0 (TIM2_CH1)
- **Clock Source:** HSI (16 MHz internal clock)
- **Prescaler:** 15
- **ARR (Auto-Reload Register):** 1000
- **Initial Duty Cycle:** 50% (Pulse = 500)

---

## 🧠 Functionality
- Configures **TIM2** for PWM mode.
- Starts PWM generation on **Channel 1**.
- Inside the infinite loop:
  - Duty cycle increases by 100 each cycle.
  - When it reaches 1000, it resets to 100.
  - Smoothly changes LED brightness or motor speed every 500 ms.

---

## ⚙️ Timer Settings Explained
| Parameter | Value | Description |
|------------|--------|-------------|
| Prescaler  | 15 | Divides 16 MHz / 16 = 1 MHz timer clock |
| Period (ARR) | 1000 | Sets PWM frequency = 1 kHz |
| Pulse (CCR1) | Variable (100–1000) | Controls duty cycle (10%–100%) |

**PWM Frequency:**
\[
f_{PWM} = \frac{f_{timer}}{(ARR + 1)} = \frac{1\,MHz}{1001} \approx 1\,kHz
\]

---

## 📂 Key Files
- `main.c` → PWM configuration and dynamic duty cycle logic.
- `main.h` → Core header and declarations.
- `.ioc` → STM32CubeMX project configuration.

---

## 🧰 Tools Used
- **STM32CubeIDE**
- **STM32CubeMX**
- **HAL Drivers**
- **C Language (C99)**

---

## 📸 Output
A PWM waveform at PA0 with a frequency of ~1 kHz and a duty cycle that increases gradually between 10% and 100%.
