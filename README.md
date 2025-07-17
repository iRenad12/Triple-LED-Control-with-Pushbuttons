# 🔌 Controlling 3 LEDs with 3 Pushbuttons using Arduino

## 📄 Description
This Arduino project demonstrates how to control three individual LEDs using three pushbuttons. Each pushbutton is wired to turn on a specific LED when pressed. It’s a beginner-friendly project to understand how digital inputs and outputs work in Arduino.

---

## 🎯 Objectives
- Read input from multiple pushbuttons.
- Control multiple digital outputs (LEDs).
- Practice breadboard circuit design.
- Strengthen understanding of conditional logic in embedded systems.

---

## 🧰 Components Used

| Component        | Quantity |
|------------------|----------|
| Arduino Uno      | 1        |
| LED              | 3        |
| Pushbutton       | 3        |
| 220Ω Resistor    | 3        |
| 10kΩ Resistor    | 3        |
| Breadboard       | 1        |
| Jumper Wires     | Several  |

---

## 🔌 Wiring Guide

### LEDs:
- Each LED **anode (+)** goes to a digital pin on Arduino (13, 12, 11).
- Each **cathode (−)** connects to GND through a 220Ω resistor.

### Pushbuttons:
- One side of each button goes to **+5V**.
- The other side connects to Arduino digital pin (2, 3, 4) **and** to GND through a **10kΩ pull-down resistor**.

---

## 💻 Arduino Code

```cpp
const int buttonPins[3] = {2, 3, 4};     // Pushbuttons
const int ledPins[3] = {13, 12, 11};     // LEDs
int buttonStates[3] = {0, 0, 0};         // State of each button

void setup() {
  for (int i = 0; i < 3; i++) {
    pinMode(buttonPins[i], INPUT);
    pinMode(ledPins[i], OUTPUT);
  }
}

void loop() {
  for (int i = 0; i < 3; i++) {
    buttonStates[i] = digitalRead(buttonPins[i]);
    digitalWrite(ledPins[i], buttonStates[i]);
  }
}
