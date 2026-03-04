# 2DOF Robot Manipulator Control Simulation

This project compares two simulation approaches for a robotic manipulator:

• MATLAB dynamic model simulation  
• Simscape Multibody physics simulation  

The goal is to evaluate trajectory tracking performance and control robustness under external disturbances.

---

## Robot Structure

Base → Link1 → Link2 → Payload

Joints:
- Joint 1 (Revolute)
- Joint 2 (Revolute)

---

## Control Strategy

- PID control
- Computed torque control
- Gravity compensation
- External disturbance rejection

---

## Results

Tracking performance:

Joint 1 RMSE: 0.059 rad  
Joint 2 RMSE: 0.119 rad

Both simulation approaches demonstrate stable tracking performance.

---

## Workflow

GrabCAD CAD Model  
→ SolidWorks Assembly  
→ URDF Export  
→ MATLAB Robotics Toolbox  
→ Simscape Multibody  
→ Control System Simulation
