# Gesture_controlled_mobile_robotic_arm
Developed and devised a 6DOF Rover and Robotic Arm, powered by the Jetson Nano. The Ardupilot platform was utilized to manage their movements and actions. Additionally, a Gesture Recognition Model was trained using Python libraries like OpenCV, TensorFlow, and Mediapipe, and seamlessly integrated into the functionality of the Robotic Arm.

## Comprehensive Project Overview: Gesture-Controlled Mobile Robotic Arm

This document outlines the complete project for a mobile robotic arm controlled by hand gestures captured through a device camera. It integrates various components to achieve this functionality:

**1. Gesture Recognition System:**

* **Technology:** Leverages OpenCV, a computer vision library, and a pre-trained model from the `hand-gesture-recognition-using-mediapipe` repository.
* **Functionality:**
    * Captures hand movements from the camera feed.
    * Employs MediaPipe for hand landmark detection.
    * Classifies hand gestures based on detected keypoints using a Multi-Layer Perceptron (MLP) model.  
    * (Optional) Can be extended to incorporate more advanced machine learning models (e.g., CNNs) for potentially improved accuracy.
* **Model Training:**
    * The provided model is trained on hand keypoint data for various gestures (configurable).
    * Users can add or modify training data to recognize additional gestures.
    * Jupyter Notebooks guide users through the training process for both hand sign and finger gesture recognition.

**2. Command Routing based on Hand Laterality:**

* The application differentiates between right and left hand gestures to control separate functionalities:
    * **Right Hand Gestures:** Control the rover (mobile platform) through commands sent using DroneKit-Python.
    * **Left Hand Gestures:** Control the movements of the 6 DOF robotic arm using SMBus communication.

**3. Rover Control System:**

* **Rover Programming:**
    * Mission Planner, a software tool for drone flight planning, is used to **simulate** the rover's movements.
* **Command Interface:**
    * DroneKit-Python, a library for interfacing with drones and other autonomous vehicles, is used to send movement commands to the **simulated** rover based on recognized hand gestures.

**4. Robotic Arm Design and Control:**

* **Rover Design:**
    * The physical structure of the rover is designed to accommodate all necessary components, including the camera for gesture recognition and the connection to the Jetson Nano.
* **6 DOF Robotic Arm Construction:**
    * A 6-Degrees-of-Freedom (DOF) robotic arm is built to provide the necessary range of motion for various tasks.
* **Robotic Arm Programming:**
    * SMBus, a communication protocol for interfacing devices, is employed to program and control the servo motors of the robotic arm. This allows for precise movement of the arm at specific angles based on the interpreted hand gestures.

**5. Overall System Integration:**

1. The gesture recognition application running on the Jetson Nano captures hand movements through the camera.
2. The model analyzes the hand keypoints and classifies the gesture.
3. Based on hand laterality (right or left) and the recognized gesture, the system sends control commands:
    * Right hand gestures: Commands are sent via DroneKit-Python to control the **simulated** rover.
    * Left hand gestures: Commands are sent via SMBus to control the robotic arm movements.

