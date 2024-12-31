# Robot Arm Control Using MPU6050 and STM32F103C8T6

## Overview
This repository contains the code for controlling a 5-DOF robotic arm using:
- **MPU6050 Driver**: For measuring motion and orientation in real-time.
- **PCA9685 Servo Motor Driver**: For precise control of the robotic arm's joints.
- **STM32F103C8T6 Driver**: The main microcontroller used to process the data from the MPU6050 and control the servo motors accordingly.

The robotic arm is controlled by motion inputs captured by the MPU6050 sensor. The STM32F103C8T6 microcontroller processes this data and drives the servo motors to move the arm as required.

## Features
- Real-time motion capture and orientation tracking using the **MPU6050** sensor.
- Efficient **PCA9685** servo motor control for smooth and precise arm movement.
- Modular driver implementation for easy integration and reusability.
- Well-commented, structured code to ensure ease of understanding and extendability.

## Repository Structure
```
/Robot_Arm_Control
├── /Drivers
│   ├── MPU6050_Driver
│   ├── PCA9685_Driver
│   └── STM32F103C8T6_Driver
├── /Core
│   ├── main.c
│   ├── stm32f1xx_it.c
│   └── system_stm32f1xx.c
├── /Config
│   ├── mpu6050_config.h
│   ├── pca9685_config.h
│   └── stm32f103c8t6_config.h
├── /Docs
│   └── README.md
└── Makefile
```

## Prerequisites
- **Hardware**:
  - **MPU6050** Motion Sensor (for orientation and motion tracking)
  - **PCA9685** 16-channel PWM Servo Driver (to control servos)
  - **Servo Motors** (for the robotic arm movement)
  - **STM32F103C8T6** Microcontroller
  - Power supply for the system
  - Robotic arm setup (physical structure with 5-DOF)
- **Software**:
  - **GCC ARM Toolchain**
  - **STM32CubeIDE** (optional, for debugging and code generation)
  - **OpenOCD** (for flashing firmware onto STM32F103C8T6)

## Installation
1. Clone this repository to your local machine:
   ```bash
   git clone https://github.com/ziadmohamed0/RoboticProjects.git
   cd RoboticProjects
   ```
2. Build the project using the provided `Makefile`:
   ```bash
   make
   ```
3. Flash the firmware to the STM32F103C8T6 using the following command:
   ```bash
   make flash
   ```

## Usage
1. Connect the hardware components:
   - Attach the **MPU6050** to the robotic arm's frame for motion tracking.
   - Connect the **PCA9685** PWM driver to the servo motors that control the arm joints.
   - Wire the **STM32F103C8T6** to both the **MPU6050** and the **PCA9685** using the configuration files.
2. Power on the system to initialize the setup.
3. Move the **MPU6050** sensor to control the movement of the robotic arm. The sensor’s accelerometer and gyroscope data will be used to adjust the servo motors accordingly.

## Code Details
### MPU6050 Driver
- Handles **I2C** communication to read data from the **accelerometer** and **gyroscope**.
- Processes raw sensor data to calculate orientation and motion in real-time, which is used to control the arm’s joints.

### PCA9685 Servo Motor Driver
- Controls the servo motors using **PWM** signals through the **PCA9685** driver.
- Allows customization of servo movement limits and speeds for each joint of the robotic arm.

### STM32F103C8T6 Driver
- Integrates the **MPU6050** sensor and **PCA9685** motor driver.
- Implements the motion control algorithms, which map the sensor data to control the robotic arm's movements based on its orientation.

## License
This project is licensed under the **MIT License**. See the LICENSE file for details.

## Contributing
Contributions are welcome! If you'd like to improve or expand on this project, please fork the repository and submit a pull request. Ensure that your code is well-commented and adheres to the existing code style.

## Contact
For any questions, suggestions, or support, feel free to contact us at:  
**Email**: zizo.alprnc.90@gmail.com

