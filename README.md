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

## **Block Diagram**

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

## **Interaction Mode**

1. The Arduino receives commands to rotate the servo motor to a specific angle.  
2. The ultrasonic sensor measures distances to obstacles at each angle.  
3. The data is transmitted via the serial port to a PC.  
4. A dedicated program processes and displays the data as a radar simulation.  

---

## **Parts List**

- **Arduino UNO/Mega** (1 unit)  
- **Ultrasonic Sensor HC-SR04** (1 unit)  
- **Servo Motor SG90 or MG995** (1 unit)  
- **Breadboard and connecting wires**  
- **USB Cable** for PC connection  

### **Hardware Requirements**
- Arduino UNO/Mega  
- Ultrasonic Sensor HC-SR04  
- Servo Motor SG90  
- Breadboard and connecting wires  
- USB Cable

---

## **Block Diagram**

![image](https://github.com/user-attachments/assets/ae9355f5-ef04-45c6-9416-e8d3b978ce9e)

---

## **Electrical Diagram**
![image](https://github.com/user-attachments/assets/c182949e-57e1-4736-9aeb-545906e2387b) ![image](https://github.com/user-attachments/assets/fbcb0a94-abb1-4b90-a70e-36d7810b407b)




