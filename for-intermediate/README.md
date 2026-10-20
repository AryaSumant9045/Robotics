# ROS 2 Intermediate — Robotics Learning Resources

> **Goal:** Move beyond ROS 2 basics and build practical skills for autonomous mobile robots and robotic-arm manipulation.
>
> **Level:** Intermediate · **Focus:** Simulation, navigation, SLAM workflows, and manipulation  
> **Cost:** The linked documentation and tutorials are freely accessible. Some simulator/robot hardware examples may require additional setup.

---

## Learning roadmap

Recommended order:

1. **Gazebo simulation** — create and test a robot in a simulated world.
2. **TF2, sensors, and SLAM** — understand frames and build/use a map (see the official ROS 2 tutorials for supporting concepts).
3. **Navigation2 (Nav2)** — configure autonomous navigation using a map, localization, planners, controllers, and behavior trees.
4. **MoveIt 2** — plan and execute motion for a robotic arm.
5. **Build a capstone project** — use simulation first, then transfer concepts to compatible hardware.

> **Version tip:** Keep your ROS 2 distribution, Gazebo integration, and tutorial branch compatible. The links below include Jazzy, Rolling, and Humble resources; do not mix commands/configuration from different distributions without checking compatibility.

---

## 1. Navigation2 (Nav2)

Nav2 is the ROS 2 navigation stack for autonomous mobile robots. It brings together localization, global/local planning, controllers, costmaps, behavior trees, and recovery behaviors.

### Best free resources

- **Official Nav2 documentation (start here):** https://docs.nav2.org/
- **Official getting-started guide and tutorials:** https://docs.nav2.org/rolling/getting_started/
- **ROS 2: Zero to Robot — Chapter 11, Navigation2:** https://pouya-mansournia.github.io/ros2-zero-to-robot/
- **Robotics Back-End — ROS 2 Nav2 tutorial (Humble):** https://roboticsbackend.com/ros2-nav2-tutorial/

### Suggested study order

1. Understand the map, robot footprint, frames, and localization inputs.
2. Learn the role of the global planner, local controller, and costmaps.
3. Configure Nav2 parameters for a known simulated robot.
4. Send navigation goals and observe planning in RViz.
5. Inspect logs and tune parameters when the robot gets stuck or takes an unsafe/inefficient route.

**Practice task:** In simulation, make a mobile robot navigate between three goal poses in a map. Record what changes when you adjust obstacle inflation or controller settings.

---

## 2. Gazebo simulation

Gazebo lets you test robot models, sensors, environments, and robot behavior without requiring physical hardware for every iteration.

### Best free resources

- **Official ROS 2 + Gazebo tutorial:** https://docs.ros.org/en/jazzy/Tutorials/Advanced/Simulators/Gazebo/Simulation-Gazebo.html
- **Gazebo Sim official documentation:** https://gazebosim.org/docs
- **ROS 2: Zero to Robot — Chapter 7, Gazebo:** https://pouya-mansournia.github.io/ros2-zero-to-robot/
- **Articulated Robotics — Gazebo tutorials:** https://articulatedrobotics.xyz/tutorials/ready-for-ros/gazebo

### Suggested study order

1. Launch a world and spawn a robot model.
2. Learn the basics of worlds, models, links, joints, and sensor plugins.
3. Connect simulated sensors and robot interfaces to ROS 2.
4. Visualize sensor topics and TF frames in RViz.
5. Test repeatable scenarios before connecting the robot to Nav2.

**Practice task:** Create or use a small indoor world, spawn a mobile robot, visualize its laser scan, and verify that ROS 2 receives the expected sensor topic.

---

## 3. MoveIt 2 — robotic arms and manipulation

MoveIt 2 provides motion planning, collision checking, robot kinematics integration, and planning/execution interfaces for robotic manipulation.

### Best free resources

- **Official MoveIt 2 documentation:** https://moveit.picknik.ai/main/index.html
- **Humble documentation (for Humble-based projects):** https://moveit.picknik.ai/humble/
- **Quickstart in RViz:** Find “Quickstart in RViz” in the official MoveIt documentation.
- **ROS 2: Zero to Robot — Chapter 13, MoveIt 2:** https://pouya-mansournia.github.io/ros2-zero-to-robot/

### Suggested study order

1. Review the robot's URDF/SRDF description and joint limits.
2. Start the MoveIt configuration in RViz and inspect the planning group.
3. Set a target pose and generate a collision-aware plan.
4. Learn planning-scene objects and collision checking.
5. Understand the difference between planning a trajectory and executing it through a compatible controller.

**Practice task:** Add a simple obstacle to the planning scene and compare a collision-free arm trajectory with the direct path the end effector might otherwise take.

---

## 4. Supporting topics worth learning

These concepts make Nav2, Gazebo, and MoveIt easier to debug:

- **TF2 and coordinate frames:** https://docs.ros.org/en/jazzy/Concepts/Intermediate/About-Tf2.html
- **URDF robot descriptions:** https://docs.ros.org/en/jazzy/Tutorials/Intermediate/URDF/URDF-Main.html
- **ros2_control:** https://control.ros.org/
- **ROS 2 tutorials index:** https://docs.ros.org/en/jazzy/Tutorials.html

Study these when a project requires them; you do not need to master every supporting topic before starting simulation.

---

## Capstone project

### Simulated autonomous robot

Build a small project with these milestones:

- [ ] Launch a robot in Gazebo.
- [ ] Verify sensor topics and coordinate frames.
- [ ] Create or load a map using a compatible SLAM/localization workflow.
- [ ] Configure Nav2 and send goal poses from RViz.
- [ ] Test obstacle avoidance and recovery behaviors.
- [ ] Write a short README with launch commands, dependencies, screenshots, and known limitations.

### Optional manipulation extension

- [ ] Load a robotic-arm model into MoveIt 2.
- [ ] Plan a collision-aware trajectory in RViz.
- [ ] Add an object to the planning scene.
- [ ] Document the planning group, controllers, and simulation setup.

---

## Recommended path in one line

**Gazebo → TF2/URDF and sensors → SLAM and mapping → Nav2 → MoveIt 2 (for arms).**

Use the official docs as the reference when a tutorial's commands or configuration differ from your installed ROS 2 distribution.
