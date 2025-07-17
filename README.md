# Triple-LED-Control-with-Pushbuttons
This project uses an Arduino Uno to control three LEDs using three separate pushbuttons. Each button turns on its corresponding LED when pressed. The project demonstrates how to read digital inputs and control digital outputs using Arduino, making it a great beginner-friendly electronics and programming exercise.
🎯 Objectives:
Learn how to wire and read pushbuttons with Arduino.
Control multiple LEDs using digital output pins.
Practice breadboard wiring and organizing circuits.
Understand how conditional logic in Arduino code translates to real hardware behavior.
🧰 Components Used:
Component	Quantity
Arduino Uno	1
LEDs (any color)	3
Pushbuttons	3
220Ω Resistors	3
10kΩ Resistors	3
Breadboard	1
Jumper Wires	Several
🔌 Wiring Explanation:
Each LED’s anode (long leg) connects to an Arduino digital pin (13, 12, 11), and the cathode (short leg) goes through a 220Ω resistor to GND.
Each pushbutton is connected between 5V and one of the Arduino input pins (2, 3, 4).
A 10kΩ pull-down resistor connects each input pin to GND, ensuring the input is LOW when the button is not pressed.
When a button is pressed, the input pin reads HIGH, and the corresponding LED lights up.
💻 Arduino Code:
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
🖼️ Circuit Diagram:
(Attach the latest breadboard wiring image you used above)
✅ Result:
Each time a pushbutton is pressed, the corresponding LED lights up. Releasing the button turns the LED off. This shows the basic interaction between hardware and software in embedded systems using Arduino.

🌟 Ideas for Improvement:
Make the LED stay on for a few seconds even after releasing the button.
Add sound using a buzzer when buttons are pressed.
Display button status on an LCD screen or serial monitor.
