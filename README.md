# Autonomous Behavior for BlueROV Underwater Vehicle

## Project Overview

This project focuses on developing autonomous behavior for the BlueROV underwater vehicle. The main goals include maintaining a fixed heading, detecting obstacles, halting at a safe distance, and navigating around obstacles to continue forward motion. The approach integrates various control systems and sensors to achieve these objectives.

## Key Components

1. **Trajectory-Following PID Controller**: Manages depth control to ensure the ROV maintains a consistent depth.
2. **P Controller**: Handles heading and yaw control to keep the ROV on a stable course.
3. **Ping Sonar Echosounder**: Detects obstacles in the ROV's path.
4. **Inertial Measurement Unit (IMU)**: Provides precise measurements of the ROV’s orientation.

## Finite State Machine (FSM) Overview

The BlueROV operates based on a Finite State Machine (FSM) with the following states:

1. **Descent**: The ROV descends to a specified depth using a PID controller for depth control.
2. **Forward**: The ROV moves forward while maintaining a constant heading and monitoring distance to obstacles.
3. **Stop**: The ROV halts when it detects an obstacle within a predefined distance.
4. **Search Left**: The ROV turns left to find a clear path if an obstacle is detected.

## Detailed State Descriptions

### 1. Descent
In the descent phase, the ROV aims to achieve and maintain a specific depth. This involves:
- Using a PID controller to manage vertical movement.
- Implementing algorithms to handle the heave speed and depth control.

### 2. Forward
During the forward phase, the ROV:
- Maintains a constant speed and heading.
- Utilizes the IMU for yaw control to keep a stable heading.
- Monitors the distance to obstacles using the ping sonar, ensuring it does not approach too closely.

### 3. Stop
When an obstacle is detected within a critical distance:
- The ROV stops moving forward.
- It prepares to find an alternative route by transitioning to the search phase.

### 4. Search Left
In the search phase:
- The ROV turns left to explore potential paths around the obstacle.
- It checks the new path for obstacles and either resumes forward movement or continues searching if the path is obstructed.

## Results

- **Depth Control**: Effective depth maintenance was achieved using PID control, providing a stable depth of 0.5 meters.
- **Obstacle Detection and Navigation**: The system successfully detected obstacles and adjusted the ROV's path to navigate around them.
- **Heading Stability**: The P-controller ensured the ROV maintained a steady heading during forward motion.

## Files Included

- **Code**: Python scripts for implementing the BlueROV’s control algorithms.
- **Bag Files**: Sensor data logs capturing the ROV’s operational data.
- **Video**: Demonstrations of the ROV’s autonomous behavior and navigation capabilities.

## Contact

For additional information or questions regarding this project, please reach out to the project team:
- **Abhimanyu Bhowmik**
- **Sergei Chashnikov**
- **Madhushree Sannigrahi**
- **Tayyab Tahir**
- **Ishfaq Bhat**

**Supervisors**:  
Associate Prof. Cédric Anthierens  
Vincent Hugel (COSMER, University of Toulon)
