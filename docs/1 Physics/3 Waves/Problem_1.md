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

## Deliverables

- A thoroughly detailed Markdown document accompanied by a Python script or Jupyter notebook containing all simulation implementations.
- An extensive analytical explanation of the observed interference patterns specific to the chosen polygon, emphasizing and clearly illustrating the underlying principles of wave superposition.
- Comprehensive graphical visualizations and dynamic animations demonstrating explicitly marked regions of constructive and destructive interference across the water surface.

