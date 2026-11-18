# 🪖 Smart Guardian IoT Helmet
### IoT-Based Smart Helmet for Accident Detection and Real-Time Emergency Alert System

An intelligent IoT-based helmet designed to detect potential motorcycle accidents using multiple sensor inputs and automatically alert emergency contacts with the rider's GPS location.

The system aims to reduce emergency response time when a rider is unconscious or unable to request help after an accident.

---

## 📌 Project Overview

The **Smart Guardian IoT Helmet** uses an ESP32-based architecture with accelerometer, gyroscope, and GPS sensors to monitor riding conditions and identify potential accidents.

When an accident is detected, the system activates a buzzer and provides the rider with an opportunity to cancel the emergency alert. If the rider does not respond, an emergency SMS containing the GPS location and Google Maps link is generated.

The project currently includes a MATLAB-based theoretical simulation to validate accident detection logic across different riding scenarios.

## 🎯 Objectives

- Monitor motorcycle speed and location using GPS.
- Detect sudden impacts and acceleration changes.
- Monitor helmet orientation and tilt.
- Distinguish actual accidents from potholes and sudden braking.
- Generate emergency alerts with GPS coordinates.
- Provide a cancellation mechanism to prevent false alarms.
- Reduce the time required to notify emergency contacts.

## 🏗️ System Architecture

```text
       SENSOR INPUTS
             |
     +-------+-------+
     |       |       |
  MPU6050   GPS    Barometer
     |       |       |
     +-------+-------+
             |
           ESP32
             |
     Accident Detection
          Algorithm
             |
      +------+------+
      |             |
    Buzzer      Cancel Button
      |
  Verification
      |
  Emergency Alert
      |
    GSM Module
      |
 Emergency Contact
      |
   GPS Location
   Google Maps Link
```

## 🔧 Hardware Components

| Component | Purpose |
|---|---|
| ESP32 | Main microcontroller |
| MPU6050 | Accelerometer and gyroscope |
| NEO-6M GPS | Speed and location tracking |
| SIM800L / SIM7600 | Emergency SMS communication |
| Buzzer | Rider warning system |
| Push Button | Cancel false emergency alerts |
| Li-ion Battery | Power supply |
| TP4056 | Battery charging and protection |
| BMP280 | Barometric altitude measurement |
| Helmet | Physical mounting platform |

## ⚙️ Working Methodology

The system follows a multi-sensor accident detection approach.

**1. Sensor Monitoring**

The system continuously monitors:
- Acceleration and impact.
- Helmet orientation and tilt.
- Motorcycle speed.
- GPS coordinates.
- Altitude variations.

**2. Accident Detection**

The detection algorithm evaluates three primary conditions:

| Parameter | Default Threshold |
|---|---|
| Impact acceleration | 4 g |
| Helmet tilt | 45° |
| Sudden speed reduction | 15 km/h |

An accident is classified as a possible accident when all three conditions are satisfied.

**3. Emergency Verification**

- The buzzer is activated.
- The rider receives a 15-second cancellation window.
- If the rider presses the cancel button, the alert is stopped.
- If there is no response, the emergency alert process begins.

**4. Emergency Notification**

The system retrieves GPS coordinates and generates an emergency message containing a Google Maps location link.

## 🧠 Accident Detection Scenarios

The system is designed to distinguish between normal riding events and actual accidents.

| Scenario | Impact | Tilt | Speed Drop | Expected Result |
|---|---|---|---|---|
| Normal Riding | No | No | No | Safe |
| Pothole | High | No | Small | Rejected |
| Sudden Braking | Low | No | High | Rejected |
| Helmet Drop | High | High | None | Rejected |
| Actual Accident | High | High | High | Alert |

## 💻 MATLAB Simulation

The first development phase implements a theoretical simulation using MATLAB.

**Simulation Features:**
- Three independent riding scenarios.
- Simulated GPS speed measurements.
- Accelerometer data generation.
- Gyroscope-based orientation monitoring.
- Barometric altitude variations.
- Multi-sensor accident detection.
- Emergency alert generation.
- GPS coordinate simulation.
- Google Maps link generation.
- Real-time sensor graphs and scenario comparisons.

### Simulation Configuration

| Parameter | Value |
|---|---|
| Sampling Frequency | 10 Hz |
| Simulation Duration | 60 seconds |
| Impact Threshold | 3.0 g |
| Speed Drop Threshold | 20 km/h |
| Tilt Threshold | 60° |
| Minimum Conditions | 2 out of 3 |
| Warning Time | 20 seconds |

**Note:** The MATLAB simulation currently uses illustrative sensor data and simulated GPS coordinates. It does not communicate with physical hardware or send actual SMS messages.

## 📊 Project Development Phases

**Phase 1 – MATLAB Simulation (Current)**

- Develop accident detection logic.
- Simulate sensor readings.
- Test normal riding, pothole, braking, and accident scenarios.
- Generate graphs and simulation reports.

**Phase 2 – Hardware Implementation**

- Integrate ESP32 with MPU6050 and GPS.
- Connect GSM communication module.
- Implement buzzer and cancellation button.
- Integrate rechargeable power supply.

**Phase 3 – Testing and Optimization**

- Perform controlled testing.
- Calibrate sensor thresholds.
- Minimize false-positive detections.
- Evaluate emergency alert reliability.

## 🚀 Future Scope

- Machine learning-based accident classification.
- Real-time mobile application.
- Cloud-based rider monitoring.
- Live GPS tracking.
- Automatic voice calls to emergency contacts.
- Hospital and emergency service integration.
- Improved detection using real-world riding datasets.

## ⚠️ Limitations

- Current MATLAB implementation is a theoretical simulation.
- GPS accuracy depends on satellite availability.
- GSM communication requires network coverage.
- Sensor thresholds require real-world calibration.
- Synthetic simulation results cannot establish real-world accident detection accuracy.

## 🛠️ Technologies Used

- MATLAB – Simulation and visualization.
- ESP32 – Embedded system controller.
- MPU6050 – Motion sensing.
- NEO-6M GPS – Location tracking.
- SIM800L / SIM7600 – GSM communication.
- C/C++ – Embedded firmware (planned implementation).
- Python – Dataset generation and machine learning (planned implementation).

## 👨‍💻 Project Team

**Divyanshu Raj Nirala**  
**Sachin Singh Rajawat**

M.Tech – Artificial Intelligence and Data Science  
National Institute of Technology Delhi (NIT Delhi)

## 📄 Project Status

<kbd>Phase 1 – MATLAB Simulation</kbd>

The theoretical simulation has been developed to evaluate multi-sensor accident detection under different riding conditions. Hardware integration and real-world testing are planned as subsequent development phases.

---

⭐ If you find this project interesting, consider giving the repository a star!

**Smart Guardian IoT Helmet – Making Every Ride Safer.**
