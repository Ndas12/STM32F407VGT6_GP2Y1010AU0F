# STM32F407VGT6 + GP2Y1010AU0F Dust Sensor Interface

![image](https://github.com/user-attachments/assets/620250a1-22c6-41b0-a846-8af20e391dea)

This project showcases how to interface the GP2Y1010AU0F optical dust sensor with the STM32F407VGT6 microcontroller to measure dust density (µg/m³) and monitor the sensor output voltage in real-time. The sensor's analog output is read via ADC1, and its internal LED is driven using GPIO pin PB10 for precise sampling control.

# 📌 Features

Interfacing GP2Y1010AU0F dust sensor using ADC1 and GPIO

**Measures:**

Output voltage (V)

Dust concentration (µg/m³)

# 🛠️ Hardware Setup

MCU: STM32F407VGT6 (Discovery board or custom board)

**Sensor:** Sharp GP2Y1010AU0F Dust Sensor

**Wiring:**

Sensor LED → PB10 (Digital Output)

Sensor analog output (Vo) → ADC1 input pin 

V-LED → GND via capacitor

LED-GND → GND

S-GND → GND

Vcc → 5v

NOTE: Connect current limiting resistor between V-LED and Vcc.

# 🧠 Sensor Sampling Logic

1. Turn on LED (PB10 = HIGH) for ~280µs

2. Wait 280µs

3. Read analog output via ADC1

4. Turn off LED

5. Wait 9.68ms (sensor sampling period is ~10ms)

6. Repeat

