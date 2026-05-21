---
title: MPU6050 Arduino Guide
nav_order: 1
description: Learn how to connect MPU6050 to Arduino Uno and Nano using working code examples, wiring diagrams, calibration tips, and GitHub downloads.
---

# MPU6050 Arduino Guide: Code, Wiring & GitHub

Learn how to connect the MPU6050 sensor to Arduino Uno or Nano, read accelerometer and gyroscope values, and start building motion-controlled projects.

The MPU6050 is one of the most popular motion sensors for Arduino projects because it combines:

- 3-axis accelerometer
- 3-axis gyroscope
- Temperature sensor
- I2C communication

This guide includes:
- Wiring diagram
- Arduino code example
- Library installation
- Troubleshooting tips
- GitHub source code

---

# What is the MPU6050?

The MPU6050 is a 6-axis motion tracking sensor commonly used in:

- Self-balancing robots
- Gesture control systems
- Drones
- Arduino games
- Tilt sensors
- Motion tracking projects

It communicates with Arduino using the I2C protocol.

---

# Required Hardware

| Component | Link |
|---|---|
| MPU6050 Sensor | [Recommended MPU6050 Module](https://YOUR-AFFILIATE-LINK.com) |
| Arduino Uno | [Compatible Arduino Uno Board](https://YOUR-AFFILIATE-LINK.com) |
| Arduino Nano | [Arduino Nano for Compact Projects](https://YOUR-AFFILIATE-LINK.com) |
| SSD1306 OLED Display | [OLED Display Used in This Project](https://YOUR-AFFILIATE-LINK.com) |
| Jumper Wires | [Male to Female Jumper Wires](https://YOUR-AFFILIATE-LINK.com) |
| Breadboard | [Breadboard for Arduino Projects](https://YOUR-AFFILIATE-LINK.com) |

---

# Components Used in This Build

This MPU6050 Arduino project was tested using the following components:

- [MPU6050 Sensor Module](https://YOUR-AFFILIATE-LINK.com)
- [Arduino Uno R3](https://YOUR-AFFILIATE-LINK.com)
- [SSD1306 I2C OLED Display](https://YOUR-AFFILIATE-LINK.com)

These components are beginner-friendly and work well for motion tracking projects, gesture control systems, and Arduino games.

---

# MPU6050 Arduino Wiring

## Arduino Uno / Nano Connections

| MPU6050 Pin | Arduino Uno/Nano |
|---|---|
| VCC | 5V |
| GND | GND |
| SDA | A4 |
| SCL | A5 |

---

# Wiring Notes

- SDA is the I2C data pin
- SCL is the I2C clock pin
- Most MPU6050 modules support 3.3V and 5V
- Default I2C address is `0x68`

---

# Install the MPU6050 Library

Open Arduino IDE and install:

## Required Libraries

1. Wire library (already included)
2. MPU6050 library

### Arduino IDE Steps

1. Open Arduino IDE
2. Go to:

    Sketch → Include Library → Manage Libraries

3. Search:

    MPU6050

4. Install a compatible library

---

# MPU6050 Arduino Code Example

The following example reads accelerometer and gyroscope data from the MPU6050 sensor.

    #include <Wire.h>
    #include <MPU6050.h>

    MPU6050 mpu;

    void setup() {
      Serial.begin(115200);
      Wire.begin();

      mpu.initialize();

      if (mpu.testConnection()) {
        Serial.println("MPU6050 connected successfully");
      } else {
        Serial.println("MPU6050 connection failed");
      }
    }

    void loop() {
      int16_t ax, ay, az;
      int16_t gx, gy, gz;

      mpu.getMotion6(&ax, &ay, &az, &gx, &gy, &gz);

      Serial.print("Accel X: ");
      Serial.print(ax);

      Serial.print(" | Accel Y: ");
      Serial.print(ay);

      Serial.print(" | Accel Z: ");
      Serial.print(az);

      Serial.print(" | Gyro X: ");
      Serial.print(gx);

      Serial.print(" | Gyro Y: ");
      Serial.print(gy);

      Serial.print(" | Gyro Z: ");
      Serial.println(gz);

      delay(500);
    }

---

# How the Code Works

## Wire.begin()

Starts I2C communication between Arduino and MPU6050.

## mpu.initialize()

Initializes the sensor.

## getMotion6()

Reads:
- Accelerometer X/Y/Z
- Gyroscope X/Y/Z

---

# Serial Monitor Output

Example:

    Accel X: -120 | Accel Y: 340 | Accel Z: 16384 | Gyro X: 12 | Gyro Y: -8 | Gyro Z: 3

---

# MPU6050 Calibration

Small sensor drift is normal.

For more accurate readings:
- Keep the sensor still during startup
- Use calibration offsets
- Avoid unstable power supplies

You can also create advanced motion tracking projects using:

- [ESP32 Development Boards](https://YOUR-AFFILIATE-LINK.com)
- [Portable Battery Modules](https://YOUR-AFFILIATE-LINK.com)
- [Larger OLED Displays](https://YOUR-AFFILIATE-LINK.com)

---

# Common Problems

## MPU6050 Not Detected

Possible causes:
- Wrong wiring
- Incorrect I2C address
- Loose connections

---

## Upload Failed

Try:
- Selecting the correct COM port
- Pressing RESET on Arduino
- Changing USB cable

---

## Random Values

Possible causes:
- Bad jumper wires
- No common ground
- Electrical noise

---

# MPU6050 Arduino Projects

You can use MPU6050 for:

- Snake games
- Gesture control
- Self-balancing robots
- Camera stabilization
- Motion detection
- Drone projects

---

# Recommended Starter Kits

If you are starting with Arduino and sensors, these kits are useful:

- [Arduino Starter Kit with Sensors](https://YOUR-AFFILIATE-LINK.com)
- [ESP32 Development Board Kit](https://YOUR-AFFILIATE-LINK.com)
- [Electronics Breadboard Kit](https://YOUR-AFFILIATE-LINK.com)

---

# GitHub Source Code

The complete MPU6050 Arduino code is available in this repository.

You can also expand this project using:

- [ESP32 Boards for Wireless Projects](https://YOUR-AFFILIATE-LINK.com)
- [Larger OLED Displays](https://YOUR-AFFILIATE-LINK.com)
- [Battery Modules for Portable Builds](https://YOUR-AFFILIATE-LINK.com)

---

# Related Tutorials

- [MPU6050 Calibration Guide](mpu6050-calibration.md)
- [ESP32 MPU6050 Tutorial](esp32-mpu6050.md)
- [SSD1306 OLED Guide](ssd1306-oled-guide.md)
- [I2C Scanner Tutorial](i2c-scanner.md)

---

# Conclusion

The MPU6050 is one of the best beginner-friendly motion sensors for Arduino projects.

With just a few wires and simple code, you can build:
- Motion-controlled games
- Tilt systems
- Robotics projects
- Gesture interfaces

The combination of Arduino + MPU6050 remains one of the most popular setups for DIY electronics and embedded projects.
