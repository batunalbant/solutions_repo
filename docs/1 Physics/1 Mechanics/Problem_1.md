# Problem 1: Investigating the Range as a Function of the Angle of Projection

## Motivation
Projectile motion, while seemingly simple, provides a rich framework for exploring fundamental principles of physics. This problem requires analyzing how the range of a projectile depends on its angle of projection. The governing equations involve both linear and quadratic relationships, offering a blend of accessibility and depth.

Several free parameters, such as initial velocity, gravitational acceleration, and launch height, influence the trajectory. These variations allow us to explore real-world applications, from sports to rocket science.

---

## Theoretical Foundation
To analyze projectile motion, we start with Newton's equations of motion. The motion occurs in two independent components: horizontal and vertical.

### Governing Equations:
- **Horizontal Motion:**
  \[ x = v_0 \cos(\theta) t \]
- **Vertical Motion:**
  \[ y = v_0 \sin(\theta) t - \frac{1}{2} g t^2 \]
- **Time of Flight:**
  \[ t_f = \frac{2 v_0 \sin(\theta)}{g} \]
- **Range:**
  \[ R = \frac{v_0^2 \sin(2\theta)}{g} \]

### Derivation of Time of Flight
The time of flight is determined by solving for the time when the projectile returns to the ground \( y = 0 \):

\[
0 = v_0 \sin(\theta) t - \frac{1}{2} g t^2
\]

Factorizing:

\[
 t \left( v_0 \sin(\theta) - \frac{1}{2} g t \right) = 0
\]

Solving for \( t \):

\[
 t = 0 \quad \text{or} \quad t = \frac{2 v_0 \sin(\theta)}{g}
\]

The non-trivial solution is taken as the total time of flight.

### Derivation of Range
Using the time of flight in the horizontal displacement equation:

\[
 R = v_0 \cos(\theta) \times \frac{2 v_0 \sin(\theta)}{g}
\]

Using the trigonometric identity \( 2 \sin(\theta) \cos(\theta) = \sin(2\theta) \), we get:

\[
 R = \frac{v_0^2 \sin(2\theta)}{g}
\]

---

## Analysis of the Range

### Influence of Initial Conditions:
- **Initial Velocity:** The range increases quadratically with \( v_0 \).
- **Gravity:** A higher gravitational acceleration reduces the range.
- **Launch Angle:** The range follows a symmetric dependence on \( \theta \), peaking at \( 45^\circ \).

### Maximum Range Condition
The maximum range occurs when:

\[
 \sin(2\theta) = 1
\]

which happens at \( 2\theta = 90^\circ \Rightarrow \theta = 45^\circ \).

Thus, the maximum range is given by:

\[
 R_{max} = \frac{v_0^2}{g}
\]

---

## Practical Applications
- **Sports:** Understanding projectile motion aids in optimizing techniques in sports such as soccer, basketball, and golf.
- **Engineering:** Missile trajectory predictions use similar physics principles.
- **Astrophysics:** Calculating escape velocities and planetary motion employs projectile equations.

---

## Implementation
To better visualize projectile motion, we implement a Python simulation that generates plots of the range as a function of angle.

```python
import numpy as np
import matplotlib.pyplot as plt

def projectile_range(v0, g=9.81):
    angles = np.linspace(0, 90, 100)
    ranges = (v0**2 * np.sin(2 * np.radians(angles))) / g
    return angles, ranges

# Example with v0 = 10 m/s
angles, ranges = projectile_range(10)
plt.plot(angles, ranges)
plt.xlabel('Angle (degrees)')
plt.ylabel('Range (m)')
plt.title('Projectile Range vs. Angle')
plt.grid()
plt.show()
```

---

## Deliverables
- A **Markdown document** with equations and explanations.
- **Python script** for simulations.
- **Graphs** illustrating range vs. angle.
- A discussion on **model limitations**, including air resistance effects.

---

## Hints and Resources
- **Start from first principles** and derive key equations.
- **Use numerical simulations** to extend beyond analytical solutions.
- **Apply concepts to real-world systems**, including sports, engineering, and astrophysics.

This structured approach ensures a comprehensive exploration of projectile motion while adhering to the course requirements for proper documentation and presentation.

