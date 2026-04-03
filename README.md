# 🚗 Autonomous Robotic Navigation System in Unity

> **Sensor-Based Autonomous Car Navigation with Obstacle Avoidance**  
> Built in Unity using C# | Raycast Sensors | WheelCollider Physics

[![Unity](https://img.shields.io/badge/Unity-2022+-black.svg)](https://unity.com)
[![Language](https://img.shields.io/badge/Language-C%23-purple.svg)](https://docs.microsoft.com/en-us/dotnet/csharp/)
[![Status](https://img.shields.io/badge/Status-Completed-brightgreen.svg)]()

---

## 🎬 Demo

▶️ **[Watch the full autonomous run on YouTube](https://youtu.be/2VZP29PA1Jk)**

> The robot navigates the entire track using only sensor feedback — no pre-programmed path, no waypoints.

---

## 🎯 Project Overview

This project implements a fully autonomous robotic car in Unity that navigates a complex track using **raycast-based sensors**, completing the course successfully without any errors or manual intervention.

The robot uses **7 directional sensors** to perceive its environment in real time — detecting lane boundaries, obstacles, and the end of the track — and makes continuous steering and acceleration decisions based on sensor feedback.

**Key achievement:** The robot completed the full track successfully, with smooth path-following, stable speed control, and reliable obstacle avoidance — all driven purely by sensor logic, no pre-programmed path.

---

## 🧠 How It Works

The robot makes all decisions in real time using sensor input — there is no predefined path or waypoint system.

```
Sensors (7 Raycasts)
        │
        ├── Front sensor (FRS)             → Detects end of road
        ├── Left sensors (L1S, L2S, L3S)  → Lane boundary + obstacle detection
        └── Right sensors (R1S, R2S, R3S) → Lane boundary + obstacle detection
        │
        ▼
Decision Logic (FixedUpdate loop)
        │
        ├── StayOnLane()             → Steer left/right to stay within road boundaries
        ├── AvoidObstacles()         → Steer away from detected obstacles
        ├── AdjustCarAcceleration()  → Maintain target speed (~4 m/s)
        └── EndOfTrack()             → Apply full brakes when road ends
        │
        ▼
WheelCollider Physics
        │
        └── 4-wheel drive with independent steer + motor + brake torque
```

---

## ⚙️ Core Features

- **7-sensor raycast array** — front, left (×3), right (×3) covering different angles and distances
- **Lane-keeping logic** — robot stays centred by reading both left and right road boundaries simultaneously
- **Obstacle avoidance** — short-range side sensors trigger immediate steering correction
- **Dynamic speed control** — motor torque adjusts continuously to maintain a stable velocity
- **End-of-track detection** — front sensor + counter logic triggers full braking when the road ends
- **4-wheel drive physics** — all wheels powered via Unity WheelCollider for realistic movement
- **Real-time tyre sync** — wheel mesh transforms update every frame to match physics colliders

---

## 📐 Sensor Configuration

| Sensor | Direction | Purpose |
|---|---|---|
| FRS (Front) | Forward + slight down | Road ahead detection, end-of-track |
| L1S / R1S | ±23° horizontal | Short-range obstacle avoidance |
| L2S / R2S | ±25° + 25° vertical | Short-range lane boundary |
| L3S / R3S | ±55° horizontal + 14° vertical | Wide-angle lane boundary |
| ORS | Downward (100° tilt) | Orientation reference sensor |

---

## 🏁 Results

- ✅ Completed full track with no errors
- ✅ Smooth steering — no oscillation or erratic behaviour
- ✅ Stable speed maintained throughout (~4 m/s)
- ✅ Obstacles successfully avoided
- ✅ Clean stop at end of track
- 🎬 [Full video proof available on YouTube](https://youtu.be/2VZP29PA1Jk)

---

## 🛠️ Tech Stack

- **Engine:** Unity 2022+
- **Language:** C#
- **Physics:** Unity WheelCollider, Rigidbody
- **Sensing:** Physics.Raycast with layer masking
- **Layers used:** `Road`, `Obs` (obstacles)

---

## 📁 Repository Structure

```
Autonomous-Robotic-Navigation-System-in-Unity/
│
├── Assets/
│   ├── Scripts/
│   │   └── RobotController.cs    # Main navigation controller
│   ├── Scenes/                   # Unity scene with track + robot
│   └── Prefabs/                  # Robot and environment prefabs
│
├── README.md
└── ProjectSettings/
```

---

## 🚀 Getting Started

### Prerequisites
- Unity 2022 or later
- No external packages required — built entirely with Unity's built-in physics

### Run the Project
1. Clone the repository
2. Open in Unity Hub
3. Open the main scene from `Assets/Scenes/`
4. Press **Play** — the robot navigates autonomously

---

## 🔮 Future Work

- Implement **ML-Agents** to replace rule-based logic with a trained RL policy
- Add **dynamic obstacles** that move during the run
- Extend to **multi-robot** scenarios with collision avoidance between agents
- Port navigation logic to a **ROS2 + Gazebo** environment for real-world transfer

---

## 👤 Author

**Bharadwaj Rachuri**  
MSc Artificial Intelligence and Robotics, University of Hertfordshire  
📧 bharadwaj.r.career@gmail.com  
🔗 [LinkedIn](https://linkedin.com/in/bharadwajrachuri) | [GitHub](https://github.com/br23aay)

---

## 📜 License

This project is licensed under the MIT License.
