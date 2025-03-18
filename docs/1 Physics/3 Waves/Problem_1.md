# Problem 1

# Interference Patterns on a water surface

## Introduction

Wave interference is a fundamental phenomenon in physics, occurring when two or more waves overlap and interact with each other, producing regions of amplified or diminished displacement. This interaction is particularly visible in waves on a water surface, where ripples generated from different sources meet, forming distinctive and visually captivating interference patterns.

In this detailed analysis, we will explore and examine the complex interference patterns formed by multiple coherent point sources arranged at the vertices of a regular polygon. Each source generates circular waves of identical amplitude, frequency, and wavelength, ensuring a structured and predictable pattern of interference. Through careful observation and simulation, we aim to deepen our understanding of wave superposition, identify distinct regions of constructive and destructive interference, and visually represent these fascinating interactions.

We will rigorously describe the wave propagation process using the single disturbance equation, meticulously applying the superposition principle. The results will be presented through comprehensive graphical simulations, providing clarity on how wave interactions develop and evolve dynamically on water surfaces.

## Motivation

Studying wave interference patterns is essential because of their broad applications and their significance in understanding fundamental wave behaviors. Important applications of wave interference include:

- **Engineering and Structural Design**: Engineers utilize interference pattern studies to construct robust maritime structures such as harbors, piers, and protective coastal barriers designed to resist the impacts of waves.
- **Environmental Science and Oceanography**: Insight into wave interactions assists scientists in predicting and mitigating coastal erosion, improving forecasts of ocean currents and wave-related natural events.
- **Educational and Pedagogical Tools**: Demonstrative interference experiments visually illustrate complex physical principles, enriching educational experiences and facilitating a deeper intuitive understanding of physics.
- **Technological Innovations**: Interference concepts form the foundation of various advanced technologies, including radar systems, sonar mapping, optical interferometry, and precision measurement instruments.

Thorough investigation and simulation of these wave patterns can enable significant advancements in controlling and utilizing wave-related phenomena across numerous scientific, educational, and technological domains.

### 1. Selection of a Regular Polygon

Begin by selecting a regular polygon, such as an equilateral triangle, square, pentagon, or hexagon, to strategically position wave sources for optimal interference pattern analysis. The choice of polygon influences the resultant wave pattern due to symmetry and spatial distribution of sources.

### 2. Positioning the Sources

Accurately position coherent wave sources at each vertex of the selected regular polygon, ensuring each source acts as the origin for circular waves emanating uniformly outward. The distance between sources directly affects interference zones, dictating how constructive and destructive interference regions are distributed.

### 3. Wave Equations

Wave propagation from each source located at coordinates \((x_0, y_0)\) is mathematically represented by the single disturbance equation:

$$
\eta(x, y, t) = \frac{A}{\sqrt{r}} \cos(kr - \omega t + \phi)
$$

To break this down further:
- The term \( A/\sqrt{r} \) represents the amplitude reduction due to the radial spreading of the wave energy, based on the inverse square root law.
- The argument of the cosine function, \( kr - \omega t + \phi \), defines the phase of the wave at any given point, where each component contributes uniquely:
  - The wave number \( k = \frac{2\pi}{\lambda} \) determines the spatial periodicity of the wave.
  - The angular frequency \( \omega = 2\pi f \) dictates the oscillatory motion in time.
  - The phase term \( \phi \) accounts for the initial displacement of the wave, which can shift the interference patterns.
- The radial distance \( r = \sqrt{(x - x_0)^2 + (y - y_0)^2} \) follows directly from the Euclidean distance formula, defining how far a point \((x,y)\) is from a source at \((x_0,y_0)\).

### 4. Superposition of Waves

To accurately describe the total wave displacement at a given point \((x,y)\), we employ the principle of superposition, summing the individual contributions from all sources:

$$
\eta_{\text{sum}}(x,y,t) = \sum_{i=1}^{N} \frac{A}{\sqrt{r_i}} \cos(k r_i - \omega t + \phi_i)
$$

Where:
- \( N \) is the number of sources.
- \( r_i = \sqrt{(x - x_i)^2 + (y - y_i)^2} \) represents the Euclidean distance from the \( i \)th source.
- Each source may have a different initial phase \( \phi_i \), though coherence is maintained across sources in this analysis.

This summation models the cumulative wave effect at each spatial point, determining the amplitude variations due to constructive and destructive interference.

### 5. Analysis of Interference Patterns

Interference patterns emerge based on the phase difference between waves arriving at a given location. Constructive interference amplifies the wave, while destructive interference diminishes it.

- **Constructive Interference:** When two waves reinforce each other, the resultant amplitude is maximized. This condition is satisfied when:
  
 $$
  k (r_i - r_j) = m 2\pi, \quad m \in \mathbb{Z}
 $$
  
  Meaning the path difference \( r_i - r_j \) must be an integer multiple of the wavelength.

- **Destructive Interference:** When two waves cancel each other out, the resultant amplitude approaches zero. This occurs when:
  
  $$
  k (r_i - r_j) = (2m + 1) \pi, \quad m \in \mathbb{Z}
  $$
  
  Here, the path difference corresponds to an odd multiple of half the wavelength.

To further quantify interference, we define the **intensity** \( I \) of the resultant wave as proportional to the square of the amplitude:

$$
I = A_{	ext{eff}}^2 = \left( \sum_{i=1}^{N} \frac{A}{\sqrt{r_i}} \cos(k r_i - \omega t + \phi_i) \right)^2
$$

This allows us to mathematically compute how energy is distributed across the interference pattern.

---

<details>
  <summary>Phyton codes.</summary>

```python
import numpy as np
import matplotlib.pyplot as plt

# Define the number of sides for the regular polygon (e.g., square has 4 sides)
polygon_sides = 4  
radius = 5  # Radius of the polygon where the wave sources are positioned

# Calculate the coordinates of the polygon's vertices
theta = np.linspace(0, 2*np.pi, polygon_sides, endpoint=False)
x_sources = radius * np.cos(theta)
y_sources = radius * np.sin(theta)

# Create the figure and axis for plotting
fig, ax = plt.subplots(figsize=(6,6))
ax.scatter(x_sources, y_sources, color='red', s=100, label="Wave Sources")  # Mark wave sources

# Draw the polygon edges by connecting the vertices
x_polygon = np.append(x_sources, x_sources[0])  # Close the polygon
y_polygon = np.append(y_sources, y_sources[0])
ax.plot(x_polygon, y_polygon, 'b-', linestyle="dashed", label="Polygon Edges")  # Dashed blue line for the polygon

# Customize axis settings
ax.set_xlabel("X Coordinate")
ax.set_ylabel("Y Coordinate")
ax.set_title("Wave Sources Positioned on a Regular Polygon")
ax.axhline(0, color='black', linewidth=0.5)  # X-axis reference line
ax.axvline(0, color='black', linewidth=0.5)  # Y-axis reference line
ax.legend()
ax.set_aspect('equal')  # Keep the aspect ratio equal to avoid distortion

# Display the grid for better readability
plt.grid(True, linestyle="--", alpha=0.6)
plt.show()

```
</details>

![alt text](image.png)

### **Wave Sources Positioned on a Regular Polygon**  

This visualization represents the placement of wave sources at the vertices of a regular polygon, which serves as the foundation for understanding wave interference. The structured positioning of sources determines the resultant wave patterns due to symmetry and spatial distribution.

---

### **Mathematical Representation of Source Placement**  

A regular polygon with \( N \) sides is defined by evenly spacing the wave sources along a circular boundary of radius \( R \). The coordinates of each wave source are calculated using:

\[
x_i = R \cos \left( \frac{2\pi i}{N} \right), \quad y_i = R \sin \left( \frac{2\pi i}{N} \right), \quad \text{for } i = 0,1,2, \dots, N-1
\]

where:  
- \( x_i, y_i \) are the Cartesian coordinates of the \( i \)-th source,  
- \( R \) is the distance from the center to each vertex,  
- \( N \) is the number of sides of the polygon (or number of sources),  
- \( i \) represents each source indexed from 0 to \( N-1 \),  
- The angle \( \theta_i = \frac{2\pi i}{N} \) ensures equal angular spacing.

The sources are placed symmetrically, forming a geometric structure that significantly influences how wavefronts interact.

---

### **Graphical Representation**  

- **Red Dots (\(\bullet\))**: Represent the **wave sources**, which are evenly spaced along the polygon's boundary.  
- **Dashed Blue Lines (\(\cdots\))**: Indicate the **edges of the polygon**, illustrating the underlying geometric structure.  
- **Cartesian Axes (X, Y)**: Provide a spatial reference for understanding wave propagation directions.

The polygonal structure ensures that interference patterns exhibit a high degree of symmetry, enabling a detailed mathematical analysis of constructive and destructive interference.

---

### **Adjustable Parameters in the Model**  

1. **Number of Wave Sources (\( N \))**  
   - Determines the complexity of the resulting wave pattern.  
   - Increasing \( N \) leads to more intricate interference effects.

2. **Polygon Radius (\( R \))**  
   - Defines the spatial scale of the system.  
   - Larger \( R \) values spread out the wave sources, affecting interference zones.

3. **Wave Properties (To be applied in the next step)**  
   - Wave amplitude \( A \), wavelength \( \lambda \), and phase \( \phi \) will directly influence the interference effects in later simulations.

---

### **Importance of this Configuration**  

This structured positioning of wave sources forms the **basis for simulating wave superposition**. The geometric arrangement determines the locations where constructive and destructive interference occur. 

By understanding how wave sources are placed, we can accurately predict **wavefront interactions** and analyze **interference patterns** mathematically.

---

<details>
  <summary>Phyton codes.</summary>

```python
import numpy as np
import matplotlib.pyplot as plt

# Define parameters for wave propagation
source_position = (0, 0)  # Central wave source at origin
grid_size = 100  # Resolution of the grid
x_range = np.linspace(-10, 10, grid_size)
y_range = np.linspace(-10, 10, grid_size)
X, Y = np.meshgrid(x_range, y_range)

# Calculate radial distance from the source
r = np.sqrt((X - source_position[0])**2 + (Y - source_position[1])**2)

# Define wave properties
wavelength = 2  # Wavelength (lambda)
k = 2 * np.pi / wavelength  # Wave number
wave_amplitude = np.cos(k * r)  # Wavefront pattern

# Plot the wavefronts
fig, ax = plt.subplots(figsize=(6,6))
contour = ax.contourf(X, Y, wave_amplitude, levels=50, cmap="viridis")

# Mark the source location
ax.scatter(*source_position, color='red', s=100, label="Wave Source")

# Axis settings
ax.set_xlabel("X Coordinate")
ax.set_ylabel("Y Coordinate")
ax.set_title("Wave Propagation from a Single Source")
ax.axhline(0, color='black', linewidth=0.5)
ax.axvline(0, color='black', linewidth=0.5)
ax.legend()
plt.colorbar(contour, label="Wave Amplitude")

# Display the figure
plt.show()

```
</details>

![alt text](image-1.png)

### **Wave Propagation from a Single Source**

This visualization illustrates the propagation of circular waves emitted from a **single point source**. This is the fundamental basis for understanding how individual wavefronts interact before superposition occurs with multiple sources.

---

### **Mathematical Representation of Wave Propagation**

A single wave originating from a point source located at \( (x_0, y_0) \) spreads outward in circular patterns. The wave function at any position \( (x, y) \) at time \( t \) can be described as:

\[
\eta(x, y, t) = A \cos(k r - \omega t + \phi)
\]

where:  
- \( \eta(x,y,t) \) is the wave displacement at position \( (x,y) \) and time \( t \),  
- \( A \) is the **wave amplitude**,  
- \( k = \frac{2\pi}{\lambda} \) is the **wave number**, defined in terms of the wavelength \( \lambda \),  
- \( \omega = 2\pi f \) is the **angular frequency**, related to the wave frequency \( f \),  
- \( r \) is the **radial distance** from the source, given by:

\[
r = \sqrt{(x - x_0)^2 + (y - y_0)^2}
\]

- \( \phi \) is the **initial phase**, which determines the starting state of the wave.

This equation captures the essence of a **monochromatic wave**, which oscillates periodically in both space and time.

---

### **Graphical Interpretation**  

- **Color Contours**: Represent the varying wave amplitude across space.  
  - **Bright regions** indicate wave crests (positive amplitude).  
  - **Dark regions** indicate wave troughs (negative amplitude).  
  - The oscillatory nature is due to the cosine function governing the wave behavior.

- **Wavefronts**:  
  - Concentric rings represent **equal-phase wavefronts**, meaning all points on a given ring oscillate in phase.
  - The spacing between wavefronts corresponds to the **wavelength \( \lambda \)**.

- **Wave Source (\(\bullet\))**:  
  - The red dot marks the **central wave source**, from which the waves originate.

---

### **Wavefront Properties and Parameters**  

1. **Wavelength (\(\lambda\))**  
   - Controls the distance between successive wave crests.
   - Smaller \( \lambda \) values lead to more tightly packed wavefronts.

2. **Wave Number (\( k \))**  
   - Defines how rapidly the wave oscillates in space.
   - Given by \( k = \frac{2\pi}{\lambda} \), larger \( k \) values result in denser wavefronts.

3. **Amplitude (\( A \))**  
   - Represents the height of the wave peaks.
   - Affects the intensity of wave interference in future simulations.

4. **Radial Distance (\( r \))**  
   - Defines how the wave propagates outward symmetrically.
   - Directly affects the phase and amplitude at each spatial point.

---

### **Physical Significance**  

This representation is essential for understanding:
- **Fundamental wave behavior**, which applies to water waves, sound waves, and electromagnetic waves.
- **Interference effects**, since the combination of multiple waves is governed by the same fundamental principles.
- **Wave energy distribution**, showing how amplitude diminishes as waves spread radially outward.

By analyzing single-source wave propagation, we can now move forward to examining **wave interference patterns resulting from multiple sources**.

 
 
