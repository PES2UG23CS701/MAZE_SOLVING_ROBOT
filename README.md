# 🧭 Maze Solving Robot using ROS2 (A* Algorithm)

## 📌 Overview

This project implements a **maze-solving robot simulation** using **ROS2 (Humble)** and **Gazebo**.
The robot navigates through a maze using the **A* (A-star) path planning algorithm** and visualizes its movement in **RViz**.

---

## 🎯 Objectives

* Implement path planning using A* algorithm
* Simulate robot movement in Gazebo
* Visualize robot path, map, and sensors in RViz
* Demonstrate autonomous navigation in a maze environment

---

## 🧠 Concept

The system works in two main parts:

1. **Path Planning (A*)**

   * Computes shortest path from start to goal
   * Uses predefined grid (`maze.py`)

2. **Robot Control**

   * Publishes velocity commands (`/cmd_vel`)
   * Moves robot along computed path

---

## 🏗️ System Architecture

* **ROS2 Node** → `maze_solver`
* **Algorithm** → A* (A-star)
* **Simulator** → Gazebo
* **Visualization** → RViz
* **Robot** → TurtleBot3 (Burger)

---

## 📁 Project Structure

```
maze_ws/
 ├── src/
 │   └── maze_solver/
 │       ├── maze_solver/
 │       │   ├── solver.py
 │       │   ├── astar.py
 │       │   ├── maze.py
 │       │   └── __init__.py
 │       ├── package.xml
 │       └── setup.py
 ├── build/
 ├── install/
 └── log/
```

---

## ⚙️ Requirements

* Ubuntu 22.04 (WSL2 supported)
* ROS2 Humble
* Gazebo
* RViz2
* TurtleBot3 packages

---

## 📦 Installation

```bash
sudo apt update
sudo apt install ros-humble-desktop
sudo apt install ros-humble-turtlebot3*
```

---

## 🚀 How to Run

### 1️⃣ Open Terminal 1 — Launch Gazebo

```bash
source /opt/ros/humble/setup.bash
export TURTLEBOT3_MODEL=burger
ros2 launch turtlebot3_gazebo turtlebot3_world.launch.py
```

---

### 2️⃣ Terminal 2 — Run SLAM

```bash
source /opt/ros/humble/setup.bash
ros2 launch slam_toolbox online_async_launch.py
```

---

### 3️⃣ Terminal 3 — Run Maze Solver

```bash
cd ~/maze_ws
colcon build
source install/setup.bash
ros2 run maze_solver solver
```

---

### 4️⃣ Terminal 4 — Open RViz

```bash
rviz2
```

👉 Set **Fixed Frame = map**

---

## 📡 Topics Used

* `/cmd_vel` → robot movement
* `/scan` → LiDAR data
* `/map` → occupancy grid
* `/path` → planned path
* `/odom` → odometry

---

## 📊 Output

* Robot moves inside maze
* Path is visualized in RViz
* LiDAR detects obstacles
* Map is generated using SLAM

---

## ⚠️ Limitations

* Uses **predefined maze grid** (not real-time mapping)
* No dynamic obstacle avoidance
* Movement is basic (no PID control)

---

## 🔮 Future Improvements

* Real-time maze solving using sensors
* Obstacle avoidance algorithm
* PID-based smooth control
* Integration with Nav2 stack

---

## 🎓 Conclusion

This project demonstrates:

* Path planning using A*
* ROS2 node communication
* Robot simulation in Gazebo
* Visualization in RViz

It provides a strong foundation for advanced robotics and autonomous navigation systems.

---

## 👨‍💻 Author

**Vishal Metre**

---

## 📜 License

This project is for academic and educational purposes.
