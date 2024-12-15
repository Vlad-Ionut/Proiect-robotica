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




