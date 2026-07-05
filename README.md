# C-Space Collision Detection for a 2-DOF Planar Robotic Arm

A MATLAB implementation of configuration space (C-space) mapping and collision-free path planning for a 2-DOF planar robotic arm. Built as part of coursework in the M.Sc. Automation & Robotics programme at TU Dortmund University.

---

## Problem Statement

Given a 2-DOF planar robotic arm operating in a workspace with obstacles, compute which joint configurations are collision-free, visualise the configuration space, and identify safe paths between configurations — without relying on trial-and-error forward kinematics at runtime.

---

## Approach

1. **Forward Kinematics** — computed the (x, y) position of each arm link end-effector for every discretised joint state (θ₁, θ₂)
2. **C-Space Discretisation** — mapped 10,000 unique joint configurations (100 × 100 grid) using logical indexing across the full joint range
3. **Collision Detection** — checked each configuration against defined obstacle geometries in workspace coordinates
4. **C-Space Visualisation** — generated 2D maps distinguishing free vs. obstacle configurations
5. **Safety Density Maps** — produced 3D workspace plots showing concentration of collision-free regions

---

## Results

| Metric | Value |
|---|---|
| Joint states evaluated | 10,000 |
| Average computation time | **0.56 seconds** |
| Collision detection method | Analytical (no sampling) |
| Visualisation output | 2D C-space map + 3D workspace density |

---

## Tech Stack

| Tool | Purpose |
|---|---|
| MATLAB | Core implementation, forward kinematics, plotting |
| Logical indexing | Efficient batch collision checking |
| 3D surface plots | Workspace safety density visualisation |

---

## How to Run

```matlab
% Clone or download the repository
% Open MATLAB and navigate to the project folder
% Run the main script:
run('cspace_collision_detection.m')
```

**Requirements:** MATLAB R2020b or later (no additional toolboxes required)

---

## Key Concepts Demonstrated

- **Configuration Space theory** — representation of robot states as points in joint space rather than workspace
- **Forward kinematics** — mapping joint angles to end-effector positions
- **Collision checking** — obstacle avoidance at the planning level, not reactive level
- **Path planning foundations** — C-space maps are the basis for planners like A\*, RRT, and PRM

---

## Relevance to Robotics Applications

This project demonstrates core path planning concepts directly applicable to:
- Industrial robot arm motion planning (avoid joint-space collisions before execution)
- Safe trajectory generation for collaborative robots (cobots)
- Foundation knowledge for ROS2 MoveIt2 motion planning pipelines

---

## Author

**Pallawi Kaushik**
M.Sc. Automation & Robotics, TU Dortmund University
[LinkedIn](https://linkedin.com/in/pallawikaushik) · [GitHub](https://github.com/pallawikaushik)

---

## License

MIT License — feel free to use, adapt, and build on this for your own robotics projects.
