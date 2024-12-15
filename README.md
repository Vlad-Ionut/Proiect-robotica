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

![image](https://github.com/user-attachments/assets/ae9355f5-ef04-45c6-9416-e8d3b978ce9e)

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
![image](https://github.com/user-attachments/assets/c182949e-57e1-4736-9aeb-545906e2387b) ![image](https://github.com/user-attachments/assets/eb10eb80-29c8-4ee4-8a65-9101f4d190e1)




