# **Arduino Radar for Object Detection**

## **Project Description**
This project is a radar system that uses an HC-SR04 ultrasonic sensor and an SG90 servo motor to scan the environment and detect obstacles within a specified angular range. The collected data is displayed on a graphical interface on a PC, providing a visual simulation of a real radar system.

### **Features**
- Obstacle detection within a range of up to 4 meters.  
- Angular scanning between 0° and 180°.  
- Real-time display on the PC graphical interface.  

## **Project Goal**
This project was created to explore the integration of hardware (Arduino, sensors, servo motors) with software (Arduino code and PC graphical interface). It is useful for education, autonomous robot development, and understanding the basic principles of proximity sensors, as well as learning fundamental principles of electronics, programming, and sensor applications in practical scenarios.

# **Initial Idea**

The project started with the idea of creating a simple yet intuitive system to demonstrate the use of distance sensors in an interactive way.

## **Usefulness**

This project can be utilized for:  
- **Educational Applications**: A practical example for understanding sensors, servo motors, and microcontrollers.  
- **Prototypes**: A foundation for obstacle detection systems in robots or other autonomous devices.  

---

## **Interaction Mode**

1. The Arduino receives commands to rotate the servo motor to a specific angle.  
2. The ultrasonic sensor measures distances to obstacles at each angle.  
3. The data is transmitted via the serial port to a PC.  
4. A dedicated program processes and displays the data as a radar simulation.  

---

## **Bill of Materials (BOM)**

| **No.** | **Component**              | **Description**                              | **Quantity** | **Link/Source**                                             | **Datasheet**                          |
|---------|-----------------------------|----------------------------------------------|--------------|-------------------------------------------------------------|----------------------------------------|
| 1       | Arduino UNO/Mega           | Microcontroller for general control          | 1            | [Arduino UNO](https://store.arduino.cc/products/arduino-uno-rev3) | [Datasheet](https://content.arduino.cc/assets/UNO-TH_Rev3e_sch.pdf) |
| 2       | Ultrasonic Sensor HC-SR04  | Measures distance to obstacles               | 1            | [HC-SR04](https://www.sparkfun.com/products/15569)          | [Datasheet](https://cdn.sparkfun.com/datasheets/Sensors/Proximity/HCSR04.pdf) |
| 3       | Servo Motor SG90           | Allows rotation of the ultrasonic sensor     | 1            | [SG90](https://www.towerpro.com.sg/sg90-mini-servo/)        | [Datasheet](https://datasheetspdf.com/pdf-file/1078956/TowerPro/SG90/1) |
| 4       | Breadboard                 | Board for temporary connections              | 1            | [Breadboard](https://www.sparkfun.com/products/12002)       | N/A                                    |
| 5       | Jumper Wires               | Wires for connecting hardware modules        | 10           | [Jumper Wires](https://www.sparkfun.com/products/12471)     | N/A                                    |
| 6       | USB Cable                  | Connects Arduino to PC                       | 1            | [USB Cable](https://www.sparkfun.com/products/512)          | N/A                                    |

 
---
# **Detailed Description of Hardware Functionality**

This section provides an in-depth explanation of the hardware components, their connections to the microcontroller, and their functional roles in the project. It also covers communication interfaces, power consumption calculations, and other relevant specifications.

---

## **Hardware Components Used**

1. **Arduino UNO/Mega**
   - **Functionality**: Acts as the central microcontroller responsible for controlling the ultrasonic sensor and servo motor. It processes data from the sensor and communicates with the PC via a serial interface.
   - **Specifications**:
     - 16 MHz clock speed.
     - Operates at 5V.
     - Input/output pins: 14 digital (6 PWM), 6 analog.
     - Serial communication: UART (USB connection to PC).

2. **Ultrasonic Sensor (HC-SR04)**  
   - **Functionality**: Measures the distance to obstacles using ultrasonic waves and sends the measured value to the Arduino for processing.  
   - **Specifications**:
     - Voltage: 5V.
     - Measurement range: 2 cm to 4 m.
     - Accuracy: ±3 mm.
     - Communication: Trigger (input) and Echo (output) pins connected to Arduino digital pins.  
   - **Connection to Arduino**:
     - `Trigger` pin → Arduino digital pin (configured as output).
     - `Echo` pin → Arduino digital pin (configured as input).

3. **Servo Motor (SG90 or MG995)**  
   - **Functionality**: Rotates the ultrasonic sensor within a range of angles (0°–180°) to scan the environment.  
   - **Specifications**:
     - Operating voltage: 4.8V–6V.
     - Torque (SG90): 1.8 kg·cm at 4.8V.
     - Communication: Controlled by a PWM signal from Arduino.  
   - **Connection to Arduino**:
     - Control pin → Arduino PWM pin.
     - Powered by the 5V output pin on Arduino or an external power source.

4. **Breadboard and Jumper Wires**  
   - **Functionality**: Used for temporary connections and to establish electrical circuits between components.  

5. **Power Supply**  
   - **Functionality**: Supplies the required voltage and current to the entire system.  
   - **Power Source**: Arduino is powered via USB from the PC, which also powers the HC-SR04 and SG90.  

---

## **Hardware Communication Interfaces**

1. **Ultrasonic Sensor Communication**  
   - **Protocol**: Simple trigger-echo communication.
     - Arduino sends a 10 µs pulse to the `Trigger` pin.
     - The sensor emits ultrasonic waves and receives their reflection.
     - The `Echo` pin produces a pulse proportional to the distance.
   - **Data Processing**:
     - The time duration of the `Echo` signal is measured using Arduino’s `pulseIn()` function.
     - Distance calculation formula:  
       \[
       \text{Distance (cm)} = \frac{\text{Time (µs)} \times 0.0343}{2}
       \]

2. **Servo Motor Communication**  
   - **Protocol**: PWM (Pulse Width Modulation).
     - Arduino generates a PWM signal on a digital pin to set the rotation angle.
     - PWM pulse width range:
       - 1 ms → 0°.
       - 2 ms → 180°.

3. **PC Communication**  
   - **Protocol**: UART (Universal Asynchronous Receiver-Transmitter) via USB.
     - Baud Rate: 9600 bps.
     - Data transmitted: Distance measurements and servo angle.

---

## **Power Consumption Calculations**

| **Component**       | **Voltage (V)** | **Current (A)** | **Power (W)**       |
|----------------------|------------------|------------------|---------------------|
| Arduino UNO          | 5               | 0.05            | 0.25               |
| Ultrasonic Sensor    | 5               | 0.015           | 0.075              |
| Servo Motor (SG90)   | 5               | ~0.15 (peak 1A) | 0.75 (peak 5W)     |

- **Total Power Consumption** (excluding peak currents):  
  \[
  P_{\text{total}} = 0.25 + 0.075 + 0.75 = 1.075 \, \text{W}
  \]

- **Power Source**: The system is powered through USB (5V, 500mA), which is sufficient under normal conditions. If prolonged servo operation occurs, an external power source for the servo motor may be required to prevent overloading the Arduino’s 5V rail.

---

## **Relevant Considerations**

1. **Heat Dissipation**: 
   - No significant heating issues are expected due to the low power consumption. However, prolonged servo operation at high torque may cause slight heating.

2. **External Power Source (if required)**:  
   - In case of higher power requirements (e.g., for more powerful servo motors), an external 5V power source should be used, with a common ground connection to the Arduino.

3. **Component Protection**:
   - **Decoupling Capacitors**: Recommended for stabilizing the power supply to the servo motor and sensor.
   - **Diodes**: Used for back EMF protection in the servo motor.

4. **Accuracy of Measurements**:
   - Distance readings may vary due to environmental factors like air temperature or obstacles with non-reflective surfaces. Adjustments to the distance calculation formula may be necessary for precise applications.

---

## **Pin  Table**

| **Component**         | **Pin Name**   | **Arduino Pin** | **Purpose**                                                   |
|------------------------|----------------|-----------------|---------------------------------------------------------------|
| **Ultrasonic Sensor**  | Trigger        | Digital Pin 9   | Sends a HIGH pulse to initiate ultrasonic wave transmission.  |
|                        | Echo           | Digital Pin 8   | Reads pulse duration to measure distance.                     |
| **Servo Motor**        | Control        | Digital Pin 10  | Receives PWM signal to control rotation angle.                |
| **PC Communication**   | Serial TX/RX   | USB Port        | Sends and receives data for visualization and control.        |
| **Power**              | VCC            | 5V              | Powers all components.                                        |
|                        | GND            | GND             | Shared ground connection for all components.                  |

---

## **Block Diagram**
![image](https://github.com/user-attachments/assets/fb5defc9-37cc-4f69-8c4b-0f6baf6098d2)


- **Arduino UNO**  
  - **Role**: General control of the sensor and servo motor.  

- **Ultrasonic Sensor (HC-SR04)**  
  - **Role**: Measures distances to obstacles.  

- **Servo Motor**  
  - **Role**: Rotates the ultrasonic sensor within an angular range.  

- **PC (Graphical Interface)**  
  - **Role**: Receives data via the serial port and displays a real-time radar simulation.  

- **Hardware Connections**  
  - Wires for power supply and communication between modules.  

---

## **Electrical Diagram**

![image](https://github.com/user-attachments/assets/e8ca37f2-e9c5-48bb-b996-1aadacefc2ae)

![image](https://github.com/user-attachments/assets/101306ff-2984-4790-b7bb-b6940fd8597a)

---
# Current Stage of Software Implementation
The project is fully operational. The ultrasonic sensor, mounted on a servo motor, detects nearby objects, and the collected data is transmitted via serial communication to a graphical interface developed in Processing. The interface displays an animated radar, indicating the angle and distance of detected objects.

## Motivation for Library Choices
- **Servo.h (Arduino):** Used for controlling the servo motor, ensuring precise rotation for environmental scanning.  
- **Processing Serial Library:** Facilitates efficient data transmission between Arduino and the graphical application.  
- **Processing Core Libraries:** Utilized for:
  - Drawing the radar.
  - Displaying real-time data.
  - Creating an appealing and informative visual interface.

## Novelty Element
The innovative aspect of the project lies in integrating a hardware system with an interactive graphical interface, offering an intuitive and clear visual experience for object monitoring. The system is compact, user-friendly, and replicable in real-world applications such as autonomous robots or safety systems.

## Justification of Laboratory Functionalities
The project leverages knowledge and technologies studied in the laboratory sessions:
- **USART (Lab 1):** Serial communication between Arduino and Processing for data transmission.  
- **PWM (Lab 3):** Precise control of the servo motor's position.  
- **ADC (Lab 4):** Conversion of analog data from the ultrasonic sensor.  
- **Timers and Interrupts (Lab 2):** Synchronization of servo motor rotation and sensor measurements.

## Project Structure
### Hardware
- **Ultrasonic Sensor:** Measures distances to objects.  
- **Servo Motor:** Rotates the sensor to scan a 180° range.  
- **LEDs:** Signal system status based on detected objects.

### Software
- **Arduino:** Processes and transmits data to the graphical interface.  
- **Processing:** Displays an animated radar and relevant distance and angle information.

### Validation
- Hardware and software testing to ensure accurate distance measurement and correct graphical interface display.  
- Performance testing for real-time system response.

## Video Demonstration
https://youtube.com/shorts/tGNQFAKVoc8?si=f6cZL8q8jK7RBZGX

## System Calibration
- **Servo Motor:**  
  - Rotation limits adjusted to prevent wear and ensure complete scanning.  
- **Ultrasonic Sensor:**  
  - Tested at various distances to correct measurement errors.  
- **Graphical Interface:**  
  - Graphic proportions calibrated to accurately reflect real-world distances.

## Optimizations Implemented
- **Performance:**  
  - Optimized servo motor rotation delays for faster response.  
- **Accuracy:**  
  - Applied a smoothing algorithm to eliminate fluctuations in sensor data.  
- **Visual Design:**  
  - Enhanced radar clarity and data display for improved readability.

---

## Bibliografie
1. [Arduino UNO Datasheet](https://www.arduino.cc/en/Main/ArduinoBoardUno)  
2. [HC-SR04 Ultrasonic Sensor Datasheet](https://cdn.sparkfun.com/datasheets/Sensors/Proximity/HCSR04.pdf)  
3. [SG90 Servo Motor Datasheet](https://www.towerpro.com.sg/index.php?route=product/product&product_id=83)  
4. [Processing Language Reference](https://processing.org/reference/)  
5. [Tutorial privind comunicarea serială Arduino-PC](https://www.arduino.cc/en/Tutorial/LibraryExamples/SerialEvent)  
6. [Algoritmi de netezire pentru date senzor](https://www.sciencedirect.com/science/article/pii/S0031320318300127)  
7. [Documentație oficială Arduino Servo Library](https://www.arduino.cc/reference/en/libraries/servo)
8. (https://www.udemy.com/course/arduino-build-arduino-practical-projects/?couponCode=24T1MT11625BROW)
9. (https://www.youtube.com/watch?v=Tr0MF8FU_60)






