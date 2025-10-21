# Bluetooth Controlled Car
<img width="1170" height="654" alt="image" src="https://github.com/user-attachments/assets/52f49c9d-f3d3-4da4-adc7-33d4598ef8c5" />

A remote-controlled car project using Arduino Uno, L298N motor driver, and HC-05 Bluetooth module. The car can be controlled wirelessly in real-time via a mobile app with Bluetooth connectivity.

## 📋 Project Overview

This project demonstrates wireless control of a robotic car using Bluetooth communication. The Arduino receives commands from a mobile device through the HC-05 Bluetooth module and controls the car's movements using the L298N motor driver.

## ✨ Features

- **Real-time Bluetooth control** via mobile app
- **Multiple movement directions**: Forward, Backward, Left, Right, and diagonal movements
- **Variable speed control** (adjustable in code)
- **Responsive motor control** using L298N H-Bridge driver
- **Simple command protocol** for easy mobile app integration

## 🔧 Hardware Requirements

- **Arduino Uno** (or compatible board)
- **L298N Motor Driver Module**
- **HC-05 Bluetooth Module**
- **DC Motors** (2x or 4x depending on configuration)
- **Robot Car Chassis**
- **Power Supply** (recommended: 7-12V battery pack)
- **Jumper Wires**
- **Breadboard** (optional)

## 📐 Circuit Diagram

### Pin Connections

#### HC-05 Bluetooth Module
- **TX** → Arduino Pin 4
- **RX** → Arduino Pin 3
- **VCC** → 5V
- **GND** → GND

#### L298N Motor Driver
- **ENA** → Arduino Pin 5 (PWM)
- **IN1** → Arduino Pin 6
- **IN2** → Arduino Pin 7
- **IN3** → Arduino Pin 8
- **IN4** → Arduino Pin 9
- **ENB** → Arduino Pin 10 (PWM)
- **12V** → Battery Positive
- **GND** → Battery Negative & Arduino GND
- **5V** → (Optional) Can power Arduino if jumper is on

#### Motors
- **Motor A** → OUT1 & OUT2 (L298N)
- **Motor B** → OUT3 & OUT4 (L298N)

## 🚀 Getting Started

### Prerequisites

- [Arduino IDE](https://www.arduino.cc/en/software) or [PlatformIO](https://platformio.org/)
- Bluetooth terminal app on your mobile device (e.g., "Bluetooth RC Controller", "Arduino Bluetooth Controller")

### Installation

1. **Clone this repository:**
   ```bash
   git clone https://github.com/yourusername/BluetoothControlledCar.git
   cd BluetoothControlledCar
   ```

2. **Using PlatformIO (recommended):**
   ```bash
   pio run --target upload
   ```

3. **Using Arduino IDE:**
   - Open `src/main.cpp` in Arduino IDE
   - Select **Tools → Board → Arduino Uno**
   - Select the correct **Port**
   - Click **Upload**

### Pairing the HC-05 Module

1. Power on the Arduino and HC-05 module
2. On your mobile device, enable Bluetooth
3. Search for devices (default name: "HC-05")
4. Pair with PIN: **1234** or **0000** (default)

## 🎮 Control Commands

The car responds to the following character commands sent via Bluetooth:

| Command | Action |
|---------|--------|
| `F` | Move Forward |
| `B` | Move Backward |
| `L` | Turn Left |
| `R` | Turn Right |
| `G` | Forward Left (diagonal) |
| `I` | Forward Right (diagonal) |
| `H` | Backward Left (diagonal) |
| `J` | Backward Right (diagonal) |
| `S` | Stop |

## 📱 Mobile App Recommendations

- **Bluetooth RC Controller** (Android)
- **Arduino Bluetooth Controller** (Android/iOS)
- **DaBLE** (Android)

Make sure to configure the app to send the correct command characters listed above.

## ⚙️ Configuration

### Adjusting Speed

To change the car's speed, modify the `Speed` variable in `main.cpp`:

```cpp
int Speed = 150; // Range: 0-255 (0 = stop, 255 = max speed)
```

### Customizing Pin Assignments

If you need to change pin connections, update the following in `main.cpp`:

```cpp
SoftwareSerial HC05 (4, 3); // TX, RX
int ENA = 5;
int IN1 = 6;
int IN2 = 7;
int IN3 = 8;
int IN4 = 9;
int ENB = 10;
```

## 🛠️ Troubleshooting

### Car doesn't move
- Check all wire connections
- Verify battery has sufficient charge (>7V)
- Ensure motors are properly connected to L298N outputs

### Bluetooth won't connect
- Check HC-05 power LED is blinking
- Verify TX/RX connections (TX → RX, RX → TX)
- Try default pairing codes: 1234 or 0000

### Erratic movement
- Check for loose connections
- Verify ground is common between Arduino and L298N
- Ensure adequate power supply for motors

## 📝 Code Structure

```
BluetoothControlledCar/
├── src/
│   └── main.cpp          # Main Arduino code
├── include/              # Header files (if any)
├── lib/                  # Custom libraries
├── test/                 # Test files
├── platformio.ini        # PlatformIO configuration
└── README.md            # This file
```

## 🎯 Future Improvements

- [ ] Add speed control via mobile app
- [ ] Implement obstacle detection with ultrasonic sensors
- [ ] Add automatic mode with pre-programmed routes
- [ ] Integrate line-following capability
- [ ] Create custom mobile application

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/yourusername/BluetoothControlledCar/issues).

## 👨‍💻 Author

**Your Name**
- GitHub: [@yourusername](https://github.com/yourusername)

## 📸 Demo

<!-- Add photos or video of your project here -->

## 🙏 Acknowledgments

- Arduino community for excellent documentation
- L298N and HC-05 module manufacturers for detailed datasheets

---

⭐ If you found this project helpful, please consider giving it a star!
