# Problem 1

**Investigating the Range as a Function of the Angle of Projection**

import numpy as np
import matplotlib.pyplot as plt

# Constants
g = 9.81  # Gravity (m/s²)
v0 = 20   # Initial velocity (m/s)

# Angle values (0° to 90°)
angles = np.linspace(0, 90, 100)  # Degrees
radians = np.radians(angles)  # Convert to radians

# Compute range for each angle
ranges = (v0**2 * np.sin(2 * radians)) / g

# Plotting
plt.figure(figsize=(8, 5))
plt.plot(angles, ranges, label=f'Initial Speed v₀ = {v0} m/s', color='b')
plt.xlabel('Launch Angle (°)')
plt.ylabel('Range (m)')
plt.title('Projectile Range as a Function of Launch Angle')
plt.axvline(45, linestyle='--', color='r', label='Maximum Range at 45°')
plt.legend()
plt.grid()

# Show the graph
plt.show()


#