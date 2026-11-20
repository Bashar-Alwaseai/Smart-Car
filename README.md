# Smart-Car

The Smart Car project is a manually designed intelligent vehicle that combines mechanical design, electronics, and programming. It can be controlled through a smartphone and uses an ultrasonic sensor to detect obstacles and automatically change direction to avoid collisions, demonstrating practical skills in automation and mechatronics engineering.

---

##  Overview
The car is a four-wheel-drive robot built around an Arduino board and a motor driver shield. It works in two layers: the user can drive it manually from a smartphone over Bluetooth, while an ultrasonic sensor mounted on a servo continuously monitors the path ahead and steers the car away from obstacles on its own.

##  Features
- **Smartphone control:** drive the car over Bluetooth using single-character commands.
- **Autonomous obstacle avoidance:** detects obstacles within 12 cm, stops, and backs up slightly.
- **Smart direction choice:** scans both sides using a servo-mounted ultrasonic sensor, compares the free distance, and turns toward the side with more space.
- **Four-wheel drive:** four DC motors driven independently, turning by skid steering (left and right sides run in opposite directions).
- **Voice control support:** voice-command handling is included in the code and can be enabled.

##  Hardware

| Component | Details |
|---|---|
| Microcontroller | Arduino [Uno / Mega] |
| Motor driver | Adafruit-style Motor Shield (AFMotor library) |
| Motors | 4 × DC gear motors (M1 to M4) |
| Distance sensor | Ultrasonic sensor (Trig: A1, Echo: A0) |
| Servo motor | Rotates the sensor (signal pin 10) |
| Wireless module | Bluetooth module [HC-05 / HC-06] |
| Power | [Battery type and voltage] |
| Chassis | [Custom-designed chassis details] |

##  How It Works
1. The ultrasonic sensor measures the distance ahead on every program cycle.
2. If the distance is greater than **12 cm**, the car moves forward.
3. If an obstacle is detected, the car stops and reverses briefly.
4. The servo turns the sensor to the **left** and then the **right** to measure free space on each side.
5. The car turns toward the side with the **larger distance** and then continues moving.
6. At the same time, Bluetooth commands from the phone are read and executed.

##  Bluetooth Commands

The app sends one character at 9600 baud:

| Command | Action |
|---|---|
| `F` | Move forward |
| `B` | Move backward |
| `L` | Turn left |
| `R` | Turn right |
| `S` | Stop |

Any Bluetooth serial controller app that sends these characters can be used.

##  Software

- **Language:** C++ (Arduino)
- **Libraries:** `Servo.h`, `AFMotor.h` (Adafruit Motor Shield library)
- **Main sketch:** `Ropot_._Car.ino`
- **Precompiled firmware:** `.hex` files for Arduino Mega and standard boards are included for direct upload.

##  Getting Started

1. Install the **Arduino IDE** and the **Adafruit Motor Shield (AFMotor)** library.
2. Open `Ropot_._Car.ino` and select your board and port.
3. Upload the sketch (or flash the matching `.hex` file).
4. Pair the Bluetooth module with your phone and send the commands above.

> ⚠️ Disconnect the Bluetooth module's RX/TX pins while uploading, since it shares the board's serial port.

##  Repository Structure

```
├── Photo/                       # Project photos
├── Presentation/                # Project presentation
├── Project Ropot . Car.pdf      # Full project report
├── Ropot_._Car.ino              # Main Arduino source code
├── Ropot_._Car.ino.*.hex        # Precompiled firmware files
└── README.md
```

##  Skills Demonstrated

- Mechanical design and robot assembly
- Embedded programming with Arduino (C++)
- Sensor integration and servo control
- Wireless communication (Bluetooth)
- Autonomous decision-making logic

