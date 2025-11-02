# Autonomous Navigation Robot - ROS2

Multi-environment autonomous mobile robot with real-time SLAM and intelligent navigation.

## 🎥 Demo: House Environment Navigation

![House Navigation](media/house/house_navigation.gif)

*Autonomous navigation through complex residential environment with dynamic obstacle avoidance*

## 🎯 Overview
Autonomous mobile robot navigation system featuring real-time SLAM mapping, path planning, and obstacle avoidance. Built with ROS2 Humble and tested in complex indoor environments.

## ✨ Key Features
- **🗺️ Real-time SLAM** - Simultaneous Localization and Mapping
- **🎯 Autonomous Navigation** - Goal-based navigation with Nav2
- **🏠 Multi-Room Navigation** - Complex indoor environment traversal
- **🚧 Dynamic Obstacle Avoidance** - Real-time collision prevention
- **📊 Visualization** - RViz monitoring and path visualization
- **💻 Python Integration** - Programmatic control interface

## 🛠️ Technology Stack

- **ROS2 Humble** - Robot middleware framework
- **Nav2** - Navigation and path planning
- **SLAM Toolbox** - Mapping and localization
- **Gazebo 11** - 3D physics simulation
- **Python 3** - Scripting and control
- **Ubuntu 22.04** - Development platform

## 🚀 Installation

### Prerequisites
```bash
# Ubuntu 22.04 with ROS2 Humble
sudo apt update
sudo apt install ros-humble-desktop
```

### Setup
```bash
# Install dependencies
sudo apt install ros-humble-navigation2 \
                 ros-humble-nav2-bringup \
                 ros-humble-slam-toolbox \
                 ros-humble-turtlebot3-gazebo \
                 ros-humble-turtlebot3-navigation2

# Configure environment
echo "export TURTLEBOT3_MODEL=burger" >> ~/.bashrc
source ~/.bashrc

# Clone repository
cd ~/ros2_ws/src
git clone https://github.com/Mansi-Gagaliya/autonomous-navigation-ros2.git
cd ~/ros2_ws
colcon build
source install/setup.bash
```

## 📖 Usage

### Launch Simulation
```bash
# Terminal 1: Start house environment
ros2 launch turtlebot3_gazebo turtlebot3_house.launch.py
```

### Start Navigation
```bash
# Terminal 2: Launch navigation stack
ros2 launch turtlebot3_navigation2 navigation2.launch.py \
    use_sim_time:=True \
    map:=$(pwd)/maps/house/house_map.yaml
```

### Navigate Autonomously
1. **Set Initial Pose** - Click "2D Pose Estimate" in RViz
2. **Send Goal** - Click "Nav2 Goal" to select destination
3. **Monitor** - Watch robot navigate autonomously!

### Build Custom Maps
```bash
# Start SLAM for mapping
ros2 launch slam_toolbox online_async_launch.py

# Manual control for exploration
ros2 run turtlebot3_teleop teleop_keyboard

# Save map
ros2 run nav2_map_server map_saver_cli -f my_map
```

## 🎓 Skills Demonstrated

**Robotics:**
- SLAM algorithms and implementation
- Path planning (A*, DWA)
- Sensor fusion (LIDAR, odometry, IMU)
- Coordinate transformations (TF)

**Software Engineering:**
- ROS2 architecture (nodes, topics, services)
- Python development
- Git version control
- Documentation

**Navigation:**
- Costmap generation
- Global and local planners
- Dynamic replanning
- Obstacle detection

## 📊 Performance

| Metric | Value |
|--------|-------|
| Navigation Success Rate | 95%+ |
| Map Building Time | ~3 min |
| Path Planning Speed | <0.5s |
| Obstacle Detection Range | 3.5m |

## 🔮 Future Work
- Multi-robot coordination
- 3D navigation capabilities
- Machine learning integration
- Real hardware deployment
- Custom environment creation

## 📁 Project Structure
```
autonomous-navigation-ros2/
├── media/
│   └── house/
│       ├── house_navigation.gif
│       └── house_navigation.mp4
├── maps/
│   └── house/
│       ├── house_map.yaml
│       └── house_map.pgm
├── src/
├── launch/
└── README.md
```

## 🤝 Development
Developed in collaboration with [Fakhar Bashar](https://github.com/Fakhar-Bashar)

## 📧 Contact

**Mansi Gagaliya**  
Robotics Software Engineer

- 🔗 GitHub: [@Mansi-Gagaliya](https://github.com/Mansi-Gagaliya)
- 💼 LinkedIn: https://www.linkedin.com/in/mansi-gagaliya-33883617a/
- 📧 Email: mansigagaliya24@gmail.com
- 📍 Location: Kaiserslautern, Germany
- 🎯 **Open to robotics opportunities in Germany**

## 📝 License
MIT License

---

### ⭐ Star this repository if you find it helpful!

**Tags:** `ros2` `robotics` `slam` `navigation` `autonomous-systems` `python` `gazebo` `mobile-robotics`
