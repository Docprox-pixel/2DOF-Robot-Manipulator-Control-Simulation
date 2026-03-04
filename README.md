# 2DOF Robot Manipulator Control Simulation

This project compares two approaches for simulating and controlling a robotic manipulator:

• **MATLAB dynamic model simulation**  
• **Simscape Multibody physics-based simulation**

The objective is to evaluate **trajectory tracking performance, control effort, and disturbance robustness**.


# Robot Dynamics

The motion of a robotic manipulator can be described by the standard nonlinear dynamic equation:

M(q) q̈ + C(q, q̇) q̇ + G(q) = τ

Where:

q → joint position vector  
q̇ → joint velocity  
q̈ → joint acceleration  

M(q) → Mass (inertia) matrix  
C(q,q̇) → Coriolis and centrifugal terms  
G(q) → Gravity torque vector  
τ → Applied joint torque


# Control Strategy

A **Computed Torque Controller with PID feedback** is implemented.

Control law:

τ = M(q)[ q̈_d + K_d(q̇_d − q̇) + K_p(q_d − q) + K_i ∫(q_d − q)dt ] + C(q,q̇) + G(q)

Where:

q_d → desired joint position  
q̇_d → desired joint velocity  
q̈_d → desired joint acceleration  

K_p → proportional gain  
K_d → derivative gain  
K_i → integral gain  

This control strategy compensates for nonlinear robot dynamics and allows stable trajectory tracking.


# Disturbance Modeling

To test controller robustness, an external disturbance torque is introduced:

τ_total = τ + τ_disturbance

Where:

τ_disturbance = [0.5 sin(0.5t), 0.3 cos(0.5t)]

This evaluates the system's ability to reject disturbances.


# Simulation Results

Tracking performance (RMSE):

Joint 1: 0.059 rad  
Joint 2: 0.119 rad

The controller maintains stable trajectory tracking even under disturbance torque.

# Workflow

GrabCAD CAD Model  
→ SolidWorks Assembly  
→ URDF Export  
→ MATLAB Robotics Toolbox  
→ Simscape Multibody Simulation  
→ Control System Validation
