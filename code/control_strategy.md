# Control Strategy

The robot uses a finite state machine (FSM) to coordinate arm motion.

States:
- Idle
- Climb
- Obstacle Detection
- Upper Arm Release
- Upper Arm Re-grip
- Lower Arm Release
- Stabilization

State transitions are triggered by sensor feedback and position thresholds.
