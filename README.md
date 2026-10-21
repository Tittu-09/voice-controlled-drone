# voice-controlled-drone
Voice-Controlled Drone Simulation with Obstacle Avoidance Using PyBullet  The project aims to develop a voice-controlled drone simulation using Python and PyBullet, enabling users to control a virtual drone through spoken commands in a three-dimensional environment. The main objective is to simplify drone operation and demonstrate navigation.

# Voice-Controlled Drone Simulation with Obstacle Avoidance Using PyBullet

## Overview

This project implements a voice-controlled drone simulation using Python and PyBullet. It enables users to control a virtual quadcopter through spoken commands in a three-dimensional simulated environment.

The system integrates speech recognition, drone movement control, physics-based simulation, and basic obstacle avoidance to demonstrate interactive drone navigation without requiring physical hardware.

## Objectives

- Develop a voice-based interface for controlling a simulated drone.
- Implement basic drone movements, including takeoff, landing, and directional navigation.
- Create a 3D simulation environment with obstacles.
- Demonstrate basic obstacle avoidance during navigation.
- Provide a foundation for exploring autonomous drone navigation and trajectory planning.

## Key Features

- **Voice Control:** Control the drone using recognized speech commands.
- **3D Simulation:** Visualize drone movements in a PyBullet environment.
- **Drone Movement:** Support takeoff, forward, backward, left, right, up, down, rotation, and landing.
- **Obstacle Avoidance:** Demonstrate basic obstacle-avoidance functionality.
- **Camera Tracking:** Follow the drone's movements within the simulation.
- **Extensible Architecture:** Allow future improvements in terrain modeling and autonomous navigation.

## Technologies Used

| Technology | Purpose |
|---|---|
| Python | Core programming and control logic |
| PyBullet | Physics simulation and 3D environment |
| SpeechRecognition | Voice command recognition |
| NumPy | Numerical computations, if used |

## Project Structure

```text
Voice-Controlled-Drone/
├── main.py
├── requirements.txt
├── README.md
└── assets/                 # Optional models and resources
```

*Note: Update the filenames and folders above to match your actual project structure.*

## Prerequisites

- Python 3.10 or a compatible Python version
- A computer capable of running a 3D simulation
- A working microphone for voice commands
- Required Python libraries

## Installation

### 1. Clone the repository

```bash
git clone <YOUR_REPOSITORY_URL>
cd <YOUR_PROJECT_FOLDER>
```

### 2. Create a virtual environment

```bash
python -m venv venv
```

### 3. Activate the environment

**Windows:**

```bash
venv\Scripts\activate
```

### 4. Install dependencies

```bash
python -m pip install --upgrade pip
pip install pybullet numpy SpeechRecognition PyAudio
```

## Running the Project

Run the main Python script from the project directory:

```bash
python main.py
```

Replace `main.py` with the actual entry-point filename if it is different.

Once the simulation starts, use the supported voice commands to control the drone. Ensure microphone permissions are enabled on your system.

## Methodology

1. Initialize the PyBullet simulation environment.
2. Create the virtual drone and simulation objects.
3. Capture and process voice commands using speech recognition.
4. Translate recognized commands into drone movement instructions.
5. Update the drone's movement within the simulation.
6. Apply the implemented obstacle-avoidance logic.
7. Visualize the drone's position and movement in real time.

## Future Enhancements

- Digital Elevation Model (DEM)-based artificial terrain generation.
- Interpolation techniques for terrain height estimation.
- B-spline trajectory planning for smoother flight paths.
- Improved collision detection and terrain-aware navigation.
- Advanced autonomous path planning and reinforcement learning.

## Applications

- Drone navigation research and education.
- Voice-controlled robotics.
- Simulation-based testing of control algorithms.
- Autonomous navigation experimentation.
- Robotics and artificial intelligence learning.

## Limitations

The project operates in a simulated environment and does not directly control a physical drone. Obstacle avoidance depends on the implemented logic, and reliable operation in complex environments requires additional testing and development.

## Contributing

Contributions, suggestions, and improvements are welcome. Fork the repository, create a feature branch, and submit a pull request with your proposed changes.

## License

This project is intended for educational and research purposes. Add an appropriate open-source license, such as the MIT License, if you wish to permit reuse and redistribution.

## Author

**Project:** Voice-Controlled Drone Simulation with Obstacle Avoidance Using PyBullet

Developed as an academic project exploring voice interaction, drone control, physics simulation, and navigation.
