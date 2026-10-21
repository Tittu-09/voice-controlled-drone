
<div align="center">

# Voice-Controlled Autonomous Drone
### Data-Driven System Identification Using SINDy and DMDc

**PX4 SITL · Gazebo · MAVSDK · Vosk · Python**

A simulation-based drone research project combining voice-controlled flight, autonomous navigation, flight telemetry analysis, and data-driven modeling of quadrotor dynamics.

</div>

---

## Overview

This project explores voice-controlled autonomous drone operation and data-driven system identification using a simulated quadrotor. Built on PX4 Software-in-the-Loop (SITL) and Gazebo, the system allows users to issue flight commands through speech while collecting telemetry data for analyzing drone dynamics.

The project integrates offline speech recognition, flight-control communication, telemetry logging, and mathematical modeling. Two system identification techniques—Sparse Identification of Nonlinear Dynamics (SINDy) and Dynamic Mode Decomposition with control (DMDc)—are used to estimate the drone's behavior from recorded flight data without directly using its underlying equations of motion.

## Key Features

- **Voice-Controlled Flight:** Execute flight commands using offline speech recognition with Vosk.
- **PX4 Integration:** Control a simulated quadrotor through PX4 SITL and MAVSDK.
- **3D Simulation:** Simulate drone flight and environmental interactions in Gazebo.
- **Navigation Commands:** Support takeoff, landing, directional movement, and saved waypoints.
- **Flight Data Logging:** Collect attitude, velocity, position, and inertial telemetry.
- **SINDy Modeling:** Identify candidate nonlinear dynamics using sparse regression.
- **DMDc Modeling:** Estimate a linear state-space model from state and control data.
- **Model Validation:** Compare identified model predictions against recorded trajectories.

## System Architecture

```text
           Voice Input
                |
                v
      Vosk Speech Recognition
                |
                v
       voice_control.py
                |
              MAVSDK
                |
                v
            PX4 SITL
                |
                v
       Gazebo Quadrotor
                |
                v
        Flight Telemetry
                |
                v
          data_logger.py
                |
                v
          Flight Dataset
                |
          +-----+-----+
          |           |
          v           v
       SINDy         DMDc
          |           |
          v           v
     Nonlinear      Linear
       Model         Model
```

## Technology Stack

| Technology | Purpose |
|---|---|
| Python | Application logic and data analysis |
| PX4 SITL | Software-based flight controller |
| Gazebo | Physics-based drone simulation |
| MAVSDK | Flight-control and telemetry interface |
| Vosk | Offline speech recognition |
| SINDy | Sparse nonlinear dynamics identification |
| DMDc | Linear system identification with control |
| NumPy / Pandas | Numerical computing and data processing |
| pyulog | PX4 flight-log conversion and analysis |
| QGroundControl | Flight monitoring and visualization |

## Project Structure

```text
project/
├── voice_control.py
├── data_logger.py
├── fit_sindy.py
├── fit_dmdc.py
├── flight_data.csv
└── README.md
```

*Adjust the structure to match the files actually present in your repository.*

## Getting Started

### Prerequisites

- Windows with WSL2 and Ubuntu, or a compatible Linux environment
- PX4 Autopilot source code
- Gazebo-compatible PX4 simulation setup
- Python 3 and pip
- QGroundControl (optional for visualization and manual override)
- Microphone access for voice commands

### 1. Start the PX4 simulation

From the PX4-Autopilot directory:

```bash
HEADLESS=1 make px4_sitl gz_x500
```

At the PX4 shell prompt, configure the additional MAVLink connection if required by your setup:

```text
mavlink start -u 14535 -o 14530 -r 4000 -t 127.0.0.1
```

### 2. Start the telemetry logger

In a separate terminal, navigate to your project directory and run:

```bash
python3 data_logger.py
```

### 3. Start voice control

Open another terminal and execute:

```bash
python3 voice_control.py
```

Ensure the required Python dependencies and Vosk speech model are installed and configured.

### 4. Identify the drone dynamics

After completing a flight and stopping the logger, run the relevant analysis script:

```bash
python3 fit_sindy.py
```

For DMDc, run the corresponding script if it exists in your repository.

## Mathematical Methods

### Sparse Identification of Nonlinear Dynamics (SINDy)

SINDy uses a library of candidate functions and sparse regression to identify a compact representation of nonlinear system dynamics from observed data.

### Dynamic Mode Decomposition with Control (DMDc)

DMDc estimates a linear state-space model:

\[
x_{k+1}=Ax_k+Bu_k
\]

where \(x_k\) represents the system state and \(u_k\) represents the control input.

### Model Evaluation

The identified models can be evaluated by comparing predicted states with recorded flight trajectories. Model accuracy depends on data quality, flight excitation, and the selected model structure.

## Applications

- Autonomous drone research
- Voice-controlled robotics
- Flight dynamics analysis
- Data-driven system identification
- Simulation-based control engineering
- Model validation and trajectory analysis

## Limitations

- The system operates in simulation and does not directly control a physical drone.
- Identification accuracy depends on sufficiently varied and reliable flight data.
- Linear DMDc models may be less accurate during large-angle maneuvers.
- Some maneuvers and telemetry topics depend on the PX4 build and available interfaces.
- Voice recognition performance depends on microphone quality and environmental noise.

## Future Enhancements

- Improved flight-data preprocessing and synchronization
- Terrain-aware navigation and artificial elevation models
- B-spline trajectory generation and smooth path planning
- Closed-loop validation of identified models
- Improved nonlinear modeling and autonomous control

## Safety Notice

This project is intended for simulation, academic research, and educational purposes. Test changes in a controlled simulation before considering any physical drone implementation.

## Author

**Project:** Voice-Controlled Autonomous Drone with Data-Driven System Identification

**Focus Areas:** Autonomous Systems · Robotics · Flight Dynamics · System Identification

