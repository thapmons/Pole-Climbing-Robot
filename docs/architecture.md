# System Architecture

The robot consists of two gripping arms with motorized wheels designed to clamp onto cylindrical poles.

Each arm operates independently but is coordinated using a state-machine-based control logic.

Obstacle traversal sequence:
1. Lower arm maintains grip.
2. Upper arm releases and passes obstacle.
3. Upper arm re-grips pole.
4. Lower arm releases and passes obstacle.
5. Both arms re-engage for stable climbing.
