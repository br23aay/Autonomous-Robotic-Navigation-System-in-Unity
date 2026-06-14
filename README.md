<div align="center">

<img src="https://capsule-render.netlify.app/api?type=waving&color=0:0d1117,50:1a1a2e,100:16213e&height=220&section=header&text=Autonomous%20Robotic%20Navigation&fontSize=36&fontColor=58a6ff&animation=fadeIn&fontAlignY=38&desc=Unity%20%7C%20C%23%20%7C%20Raycast%20Sensors%20%7C%20WheelCollider%20Physics&descAlignY=58&descSize=18&descColor=8b949e" width="100%"/>

<a href="https://git.io/typing-svg">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=22&pause=1000&color=58A6FF&center=true&vCenter=true&width=700&lines=Sensor-Driven+Autonomous+Car+%F0%9F%9A%97;7+Raycast+Sensors+%7C+Real-Time+Control;Obstacle+Avoidance+%7C+Lane+Keeping;Score%3A+100+%2F+100+%F0%9F%A5%87" alt="Typing SVG" />
</a>

<br><br>

[![Unity](https://img.shields.io/badge/Unity-2022%2B-black?style=for-the-badge&logo=unity&logoColor=white)](https://unity.com)
[![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=csharp&logoColor=white)](https://docs.microsoft.com/en-us/dotnet/csharp/)
[![Score](https://img.shields.io/badge/Score-100%2F100-brightgreen?style=for-the-badge&logo=checkmarx&logoColor=white)](.)
[![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge&logo=opensourceinitiative&logoColor=white)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)](.)

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
> <div align="center">

| Metric | Outcome |
|:---|:---|
| Track Completion | ✅ Full track, zero errors |
| Steering Behaviour | ✅ Smooth — no oscillation or erratic movement |
| Speed Control | ✅ Stable throughout (~4 m/s) |
| Obstacle Avoidance | ✅ All obstacles successfully avoided |
| Track Stop | ✅ Clean full brake at end of road |
| **Final Score** | 🥇 **100 / 100** |

</div>

---

## 🧠 System Architecture

```
Sensors (7 Raycasts)
│
├── FRS  (Front)           → Detects end of road
├── L1S / R1S  (±23° H)   → Short-range obstacle avoidance
├── L2S / R2S  (±25° V)   → Short-range lane boundary
└── L3S / R3S  (±55° H)   → Wide-angle lane boundary
│
▼
Decision Logic  (FixedUpdate loop)
│
├── StayOnLane()            → Steer left/right to stay on road
├── AvoidObstacles()        → Immediate correction on obstacle detection
├── AdjustCarAcceleration() → Continuous torque control (~4 m/s)
└── EndOfTrack()            → Full brake when road ends
│
▼
WheelCollider Physics
└── 4-wheel drive — independent steer + motor + brake per wheel
```

---

## ⚙️ Core Features

<div align="center">

| Feature | Description |
|:---|:---|
| 🎯 **7-Sensor Raycast Array** | Front, left (×3), right (×3) covering distinct angles & distances |
| 🛣️ **Lane-Keeping Logic** | Stays centred by reading both left and right road boundaries |
| 🚧 **Obstacle Avoidance** | Short-range side sensors trigger immediate steering correction |
| ⚡ **Dynamic Speed Control** | Motor torque adjusts continuously to maintain stable velocity |
| 🛑 **End-of-Track Detection** | Front sensor + counter triggers full braking when road ends |
| 🔧 **4-Wheel Drive Physics** | All wheels powered via Unity WheelCollider |
| 🔄 **Real-Time Tyre Sync** | Wheel mesh transforms update every frame |

</div>

---

## 📐 Sensor Configuration

<div align="center">

| Sensor | Direction | Purpose |
|:---:|:---:|:---|
| **FRS** | Forward + slight down | Road-ahead detection, end-of-track |
| **L1S / R1S** | ±23° horizontal | Short-range obstacle avoidance |
| **L2S / R2S** | ±25° + 25° vertical | Short-range lane boundary |
| **L3S / R3S** | ±55° horizontal + 14° vertical | Wide-angle lane boundary |
| **ORS** | Downward (100° tilt) | Orientation reference sensor |

</div>

---

## 🛠️ Tech Stack

<div align="center">

![Unity](https://img.shields.io/badge/Unity-100000?style=for-the-badge&logo=unity&logoColor=white)
![C#](https://img.shields.io/badge/C%23-239120?style=for-the-badge&logo=csharp&logoColor=white)
![Visual Studio](https://img.shields.io/badge/Visual_Studio-5C2D91?style=for-the-badge&logo=visual%20studio&logoColor=white)
![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)

</div>

---

## 📁 Repository Structure

```
Autonomous-Robotic-Navigation-System-in-Unity/
│
├── Assets/
│   ├── Scripts/
│   │   └── RobotController.cs     # Main navigation controller
│   ├── Scenes/                    # Unity scene with track + robot
│   └── Prefabs/                   # Robot and environment prefabs
│
├── README.md
└── ProjectSettings/
```

---

## 🚀 Getting Started

**Prerequisites:** Unity 2022+ — no external packages required.

```bash
git clone https://github.com/br23aay/Autonomous-Robotic-Navigation-System-in-Unity.git
# Open in Unity Hub → Open main scene → Press Play
```

---

## 🔮 Future Work

- [ ] **ML-Agents** — replace rule-based logic with a trained RL policy
- [ ] - [ ] **Dynamic obstacles** that move during the run
- [ ] - [ ] **Multi-robot scenarios** with inter-agent collision avoidance
- [ ] - [ ] **ROS2 + Gazebo** port for real-world transfer

- [ ] ---

- [ ] ## 👤 Author

- [ ] <div align="center">

<img src="https://capsule-render.netlify.app/api?type=soft&color=0:1a1a2e,100:16213e&height=120&section=header&text=Bharadwaj%20Rachuri&fontSize=28&fontColor=58a6ff&animation=twinkling&desc=MSc%20Artificial%20Intelligence%20%26%20Robotics%20%E2%80%94%20University%20of%20Hertfordshire&descColor=8b949e&descSize=14&descAlignY=72" width="80%"/>

<br><br>

[![Email](https://img.shields.io/badge/Email-bharadwaj.r.career%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white)](mailto:bharadwaj.r.career@gmail.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com)
[![GitHub](https://img.shields.io/badge/GitHub-br23aay-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/br23aay)

</div>

---

## 📜 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

<div align="center">

<img src="https://capsule-render.netlify.app/api?type=waving&color=0:16213e,50:1a1a2e,100:0d1117&height=120&section=footer&text=%E2%AD%90%20Star%20this%20repo%20if%20you%20found%20it%20useful!&fontSize=18&fontColor=58a6ff&animation=twinkling&fontAlignY=65" width="100%"/>

</div>
