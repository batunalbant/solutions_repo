# Problem 1
# Investigating the Range as a Function of the Angle of Projection

## Introduction

Projectile motion is a fundamental concept in physics, widely applicable in fields ranging from sports to aerospace engineering. While the basic principles may seem straightforward, the mathematical relationships governing the motion provide deep insights into how variables interact. This study aims to analyze how the range of a projectile depends on its angle of projection and explore the theoretical and computational models associated with it.

---

## Motivation

Projectile motion, while seemingly simple, provides a rich framework for exploring fundamental principles of physics. This problem requires analyzing how the range of a projectile depends on its angle of projection. The governing equations involve both linear and quadratic relationships, offering a blend of accessibility and depth.

Several free parameters, such as initial velocity, gravitational acceleration, and launch height, influence the trajectory. These variations allow us to explore real-world applications, from sports to rocket science.

---

## Theoretical Foundation

To analyze projectile motion, we start with Newton's equations of motion. The motion occurs in two independent components: horizontal and vertical.

### Governing Equations:

- **Horizontal Motion:**
  \(x = v_0 \cos(\theta) t\)
- **Vertical Motion:**
  \(y = v_0 \sin(\theta) t - \frac{1}{2} g t^2\)
- **Time of Flight:**
  \(t_f = \frac{2 v_0 \sin(\theta)}{g}\)
- **Range:**
  \(R = \frac{v_0^2 \sin(2\theta)}{g}\)

### Derivation of Time of Flight

**The time of flight is determined by solving for the time when the projectile returns to the ground \(y = 0\):**

$$
0 = v_0 \sin(\theta) t - \frac{1}{2} g t^2
$$

**Factorizing:**

$$
 t \left( v_0 \sin(\theta) - \frac{1}{2} g t \right) = 0
$$

**Solving for \(t\):**

$$
 t = 0 \quad \text{or} \quad t = \frac{2 v_0 \sin(\theta)}{g}
$$

**The non-trivial solution is taken as the total time of flight.**

### Derivation of Range

Using the time of flight in the horizontal displacement equation:

$$
 R = v_0 \cos(\theta) \times \frac{2 v_0 \sin(\theta)}{g}
$$

Using the trigonometric identity \(2 \sin(\theta) \cos(\theta) = \sin(2\theta)\), we get:

$$
 R = \frac{v_0^2 \sin(2\theta)}{g}
$$

---
### Results & Discussion

From the numerical simulations and visualizations, we can draw the following conclusions:

- The projectile's range is maximized at **45°**, confirming the theoretical prediction.

- Increasing the initial velocity significantly increases the range, as expected from the quadratic dependence on .

- The Isocontour map clearly shows that small angles result in shorter trajectories, while very high angles also limit range due to vertical motion dominating over horizontal displacement.

- The **heatmap** provides a direct way to determine optimal launch conditions for achieving maximum range in practical scenarios.

- These results validate the theoretical framework and emphasize the importance of choosing the right launch parameters based on specific applications.


---

### Limitations

While the model provides valuable insights into projectile motion, some limitations must be considered:

- Air Resistance is Ignored: The model assumes a vacuum, meaning drag forces are not accounted for. In real-world applications, air resistance significantly affects both range and trajectory.

- Constant Gravitational Field: The model assumes a uniform gravitational field, which is a reasonable assumption for short-range projectiles but becomes inaccurate for high-altitude launches or planetary-scale motions.

- Flat Terrain: The analysis does not account for uneven ground or launch/landing height differences, which are crucial in many practical applications (e.g., artillery, sports, aerospace).

- Future refinements could include computational fluid dynamics (CFD) models for drag effects and adjustments for varying gravitational conditions in extraterrestrial applications.


---

## Implementation

To better visualize projectile motion, we implement a Python simulation that generates plots of the range as a function of angle. Additionally, we compute the full trajectory of the projectile to examine the path it follows.

```python
import numpy as np
import matplotlib.pyplot as plt

def projectile_range(v0, g=9.81):
    angles = np.linspace(0, 90, 100)
    ranges = (v0**2 * np.sin(2 * np.radians(angles))) / g
    return angles, ranges

def projectile_trajectory(v0, theta, g=9.81, t_max=2):
    t = np.linspace(0, t_max, num=100)
    x = v0 * np.cos(np.radians(theta)) * t
    y = v0 * np.sin(np.radians(theta)) * t - 0.5 * g * t**2
    return x, y

# Example with v0 = 10 m/s
angles, ranges = projectile_range(10)
plt.figure(figsize=(10, 5))

# Range Plot
plt.subplot(1, 2, 1)
plt.plot(angles, ranges)
plt.xlabel('Angle (degrees)')
plt.ylabel('Range (m)')
plt.title('Projectile Range vs. Angle')
plt.grid()

# Trajectory Plot for a Specific Angle
theta_example = 45
x, y = projectile_trajectory(10, theta_example)
plt.subplot(1, 2, 2)
plt.plot(x, y)
plt.xlabel('Horizontal Distance (m)')
plt.ylabel('Vertical Distance (m)')
plt.title(f'Projectile Trajectory for {theta_example} Degrees')
plt.grid()

plt.tight_layout()
plt.show()
```
![alt text](image-1.png)


This implementation allows for both range analysis across different launch angles and a visualization of the projectile’s full motion for a chosen angle. The trajectory plot helps in understanding how the projectile moves through the air, while the range plot provides insights into how angle selection impacts overall displacement.


## Isocontour Map for Range Analysis

 

```python
# Isocontour
import numpy as np
import matplotlib.pyplot as plt


v0_values = np.linspace(5, 50, 50)  
angles = np.linspace(0, 90, 50)  
g = 9.81  


def compute_range(v0, theta, g=9.81):
    return (v0**2 * np.sin(2 * np.radians(theta))) / g


range_matrix = np.zeros((len(v0_values), len(angles)))

for i, v0 in enumerate(v0_values):
    for j, theta in enumerate(angles):
        range_matrix[i, j] = compute_range(v0, theta, g)


plt.figure(figsize=(10, 6))
contour = plt.contourf(angles, v0_values, range_matrix, cmap='plasma', levels=20)
cbar = plt.colorbar(contour)
cbar.set_label('Range (m)')

plt.xlabel('Launch Angle (degrees)')
plt.ylabel('Initial Velocity (m/s)')
plt.title('Projectile Range Heatmap (Velocity vs. Angle)')
plt.grid(True)


plt.show()
```
![alt text](image-2.png)

The following heatmap represents the projectile range for different initial velocities and launch angles. This visualization helps in understanding the optimal conditions for maximizing range.


## Deliverables

- A **Markdown document** with equations and explanations.
- **Python script** for simulations, including range calculations and trajectory plots.
- **Graphs** illustrating range vs. angle and projectile trajectory.
- A discussion on **model limitations**, including air resistance effects.

---

## Hints and Resources

- **Start from first principles** and derive key equations.
- **Use numerical simulations** to extend beyond analytical solutions.
- **Apply concepts to real-world systems**, including sports, engineering, and astrophysics.
- **Experiment with different initial velocities and launch angles** to observe variations in projectile motion.



