# 🚗 ESP32 Bluetooth Car

Control your car using an **ESP32** and **Bluetooth** from a smartphone app.  
This project demonstrates how to use the `BluetoothSerial` library to send commands for motor movement.

---

## 📌 Requirements
- ESP32 Development Board  
- L298N Motor Driver Module  
- 2–4 DC Motors  
- Battery Pack (7.4V–12V depending on motor specs)  
- Jumper Wires  
- Smartphone with a Bluetooth terminal app  

---

## ⚡ Circuit Diagram

### ESP32 ↔️ L298N Motor Driver Connections

| ESP32 Pin | L298N Input | Description         |
|-----------|-------------|---------------------|
| GPIO16    | IN1         | Motor A direction 1 |
| GPIO17    | IN2         | Motor A direction 2 |
| GPIO18    | IN3         | Motor B direction 1 |
| GPIO19    | IN4         | Motor B direction 2 |
| 5V        | VCC         | Module power supply |
| GND       | GND         | Common ground       |

🔗 **Reference Diagram:** [ESP32 with L298N Motor Driver](https://randomnerdtutorials.com/esp32-dc-motor-l298n-driver/)

---

## 📚 Libraries

- **BluetoothSerial** → already included in the ESP32 Arduino core  
- **Arduino Core for ESP32**  

👉 Install ESP32 Board Package in Arduino IDE:  
1. Open **File > Preferences**  
2. Add the following URL in *Additional Board Manager URLs*:  
