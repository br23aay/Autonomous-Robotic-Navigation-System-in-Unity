<div align="center">

# 🚗 Autonomous Robotic Navigation System in Unity

### Sensor-Driven Autonomous Car | Obstacle Avoidance | Real-Time Control

[![Unity](https://img.shields.io/badge/Unity-2022%2B-black?style=for-the-badge&logo=unity)](https://unity.com)
[![Language](https://img.shields.io/badge/Language-C%23-purple?style=for-the-badge&logo=csharp)](https://docs.microsoft.com/en-us/dotnet/csharp/)
[![Score](https://img.shields.io/badge/Score-100%2F100-brightgreen?style=for-the-badge)](.)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)](LICENSE)

<br>

> 🎬 **[▶ Watch the Full Autonomous Run on YouTube](https://www.youtube.com)**
> >
> >> *The robot navigates the entire track using only sensor feedback — no pre-programmed path, no waypoints.*
> >>
> >> </div>

---

## 📌 Overview

This project implements a **fully autonomous robotic car** in Unity that navigates a complex track using **7 raycast-based sensors** — completing the course with zero errors, no manual intervention, and a **perfect score of 100/100**.

The robot makes all decisions in **real time** based on sensor data: detecting lane boundaries, avoiding obstacles, maintaining speed, and braking cleanly at the end of the track.

> 💡 **Key Highlight:** No pre-programmed path or waypoint system — the robot's behaviour emerges entirely from its sensor-driven control logic.
>
> ---
>
> ## 🏆 Results
>
> | Metric | Outcome |
> |---|---|
> | Track Completion | ✅ Full track, zero errors |
> | Steering Behaviour | ✅ Smooth — no oscillation or erratic movement |
> | Speed Control | ✅ Stable throughout (~4 m/s) |
> | Obstacle Avoidance | ✅ All obstacles successfully avoided |
> | Track Stop | ✅ Clean full brake at end of road |
> | **Final Score** | 🥇 **100 / 100** |
>
> ---
>
> ## 🧠 System Architecture
>
> ```
> Sensors (7 Raycasts)
> │
> ├── FRS  (Front)           → Detects end of road
> ├── L1S / R1S  (±23° H)   → Short-range obstacle avoidance
> ├── L2S / R2S  (±25° V)   → Short-range lane boundary
> └── L3S / R3S  (±55° H)   → Wide-angle lane boundary
> │
> ▼
> Decision Logic  (FixedUpdate loop)
> │
> ├── StayOnLane()           → Steer left/right to stay on road
> ├── AvoidObstacles()       → Immediate correction on obstacle detection
> ├── AdjustCarAcceleration()→ Continuous torque control (~4 m/s)
> └── EndOfTrack()           → Full brake when road ends
> │
> ▼
> WheelCollider Physics
> │
> └── 4-wheel drive — independent steer + motor + brake per wheel
> ```
>
> ---
>
> ## ⚙️ Core Features
>
> - **7-sensor raycast array** — front, left (×3), right (×3) covering distinct angles and distances
> - - **Lane-keeping logic** — robot stays centred by reading both left and right road boundaries simultaneously
>   - - **Obstacle avoidance** — short-range side sensors trigger immediate steering correction
>     - - **Dynamic speed control** — motor torque adjusts continuously to maintain stable velocity
>       - - **End-of-track detection** — front sensor + counter logic triggers full braking when road ends
>         - - **4-wheel drive physics** — all wheels powered via Unity WheelCollider for realistic movement
>           - - **Real-time tyre sync** — wheel mesh transforms update every frame to match physics colliders
>            
>             - ---
>
> ## 📐 Sensor Configuration
>
> | Sensor | Direction | Purpose |
> |---|---|---|
> | **FRS** | Forward + slight down | Road-ahead detection, end-of-track |
> | **L1S / R1S** | ±23° horizontal | Short-range obstacle avoidance |
> | **L2S / R2S** | ±25° + 25° vertical | Short-range lane boundary |
> | **L3S / R3S** | ±55° horizontal + 14° vertical | Wide-angle lane boundary |
> | **ORS** | Downward (100° tilt) | Orientation reference sensor |
>
> ---
>
> ## 🛠️ Tech Stack
>
> | Category | Technology |
> |---|---|
> | **Engine** | Unity 2022+ |
> | **Language** | C# |
> | **Physics** | Unity WheelCollider, Rigidbody |
> | **Sensing** | Physics.Raycast with layer masking |
> | **Layers** | Road, Obs (obstacles) |
>
> ---
>
> ## 📁 Repository Structure
>
> ```
> Autonomous-Robotic-Navigation-System-in-Unity/
> │
> ├── Assets/
> │   ├── Scripts/
> │   │   └── RobotController.cs     # Main navigation controller
> │   ├── Scenes/                    # Unity scene with track + robot
> │   └── Prefabs/                   # Robot and environment prefabs
> │
> ├── README.md
> └── ProjectSettings/
> ```
>
> ---
>
> ## 🚀 Getting Started
>
> ### Prerequisites
> - Unity **2022 or later**
> - - No external packages required — built entirely with Unity's built-in physics
>  
>   - ### Run the Project
>   - ```bash
>     # 1. Clone the repository
>     git clone https://github.com/br23aay/Autonomous-Robotic-Navigation-System-in-Unity.git
>
>     # 2. Open in Unity Hub
>     # 3. Open the main scene from Assets/Scenes/
>     # 4. Press Play — the robot navigates autonomously
>     ```
>
> ---
>
> ## 🔮 Future Work
>
> - [ ] Implement **ML-Agents** to replace rule-based logic with a trained RL policy
> - [ ] - [ ] Add **dynamic obstacles** that move during the run
> - [ ] - [ ] Extend to **multi-robot scenarios** with inter-agent collision avoidance
> - [ ] - [ ] Port navigation logic to **ROS2 + Gazebo** for real-world transfer
>
> - [ ] ---
>
> - [ ] ## 👤 Author
>
> - [ ] <div align="center">

**Bharadwaj Rachuri**
MSc Artificial Intelligence and Robotics — University of Hertfordshire

[![Email](https://img.shields.io/badge/Email-bharadwaj.r.career%40gmail.com-red?style=flat-square&logo=gmail)](mailto:bharadwaj.r.career@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue?style=flat-square&logo=linkedin)](https://linkedin.com)
[![GitHub](https://img.shields.io/badge/GitHub-br23aay-black?style=flat-square&logo=github)](https://github.com/br23aay)

</div>

---

## 📜 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<div align="center">

⭐ If you found this project useful or interesting, consider starring the repo!

</div>
