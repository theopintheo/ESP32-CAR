#include <BluetoothSerial.h>
#include <Arduino.h>

// Motor control pins
const int motorPin1 = 16;
const int motorPin2 = 17;
const int motorPin3 = 18;
const int motorPin4 = 19;

// Create a BluetoothSerial object
BluetoothSerial SerialBT;

void setup() {
  // Set motor pins as outputs
  pinMode(motorPin1, OUTPUT);
  pinMode(motorPin2, OUTPUT);
  pinMode(motorPin3, OUTPUT);
  pinMode(motorPin4, OUTPUT);

  // Start Bluetooth communication
  SerialBT.begin("ESP32_Car");
  Serial.begin(9600);
}

void loop() {
  if (SerialBT.available()) {
    char command = SerialBT.read();
    controlCar(command);
  }
}

void controlCar(char command) {
  switch (command) {
    case 'F': // Forward
      digitalWrite(motorPin1, HIGH);
      digitalWrite(motorPin2, LOW);
      digitalWrite(motorPin3, HIGH);
      digitalWrite(motorPin4, LOW);
      break;
    case 'B': // Backward
      digitalWrite(motorPin1, LOW);
      digitalWrite(motorPin2, HIGH);
      digitalWrite(motorPin3, LOW);
      digitalWrite(motorPin4, HIGH);
      break;
    case 'L': // Left
      digitalWrite(motorPin1, LOW);
      digitalWrite(motorPin2, HIGH);
      digitalWrite(motorPin3, HIGH);
      digitalWrite(motorPin4, LOW);
      break;
    case 'R': // Right
      digitalWrite(motorPin1, HIGH);
      digitalWrite(motorPin2, LOW);
      digitalWrite(motorPin3, LOW);
      digitalWrite(motorPin4, HIGH);
      break;
    case 'S': // Stop
      digitalWrite(motorPin1, LOW);
      digitalWrite(motorPin2, LOW);
      digitalWrite(motorPin3, LOW);
      digitalWrite(motorPin4, LOW);
      break;
  }
}
