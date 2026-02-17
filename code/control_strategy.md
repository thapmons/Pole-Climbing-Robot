# Control Strategy

The robot uses a **Finite State Machine (FSM)** to coordinate vertical motion and automated obstacle avoidance. The system transitions between states based on manual joystick input and real-time sensor feedback from the upper and lower arms.

## Flowchart Diagram
![Flowchart](Flowchart_Diagram.png)
## System States

### Core Navigation
* **Idle:** Default waiting state.
* **Enable User Command Interface:** Active polling for joystick input.
* **Climb Up / Climb Down:** Directional movement triggered by joystick vertical axis.

### Obstacle Avoidance Sequence
When an obstacle is detected on the leading arm, the FSM enters a recovery sequence:
* **Load Bearing:** The trailing arm (opposite the obstacle) locks to hold the robot's weight.
* **Release and Reposition (Arm A):** The leading arm detaches and moves past the obstacle.
* **Re-grip Pole (Arm A):** The leading arm secures its position.
* **Release and Reposition (Arm B):** The trailing arm follows to reset the climbing gait.
* **Stabilization:** Both arms grip the pole to ensure a secure hold.

---

## Control Logic Flow



The system follows a specific decision-making hierarchy:

1.  **Input Check:** Is the joystick Up or Down?
    * *If No:* Return to **Idle**.
2.  **Obstacle Check:** Is a sensor triggered on the leading arm?
    * *If No:* Proceed to **Both arms grip pole** and **End**.
    * *If Yes:* Initiate the 5-step avoidance sequence.
3.  **Safety Lock:** The trailing arm must hold the load before the leading arm is released.

## State Transitions

| Event | Current State | Next State |
| :--- | :--- | :--- |
| System Boot | Start | Idle |
| Joystick Up | Command Interface | Climb Up |
| Joystick Down | Command Interface | Climb Down |
| Sensor Triggered | Climb (Up/Down) | Arm Repositioning |
| Path Clear | Climb (Up/Down) | Stabilization |
| Sequence Complete | Stabilization | End |

