# Problem 2

# Escape Velocities and Cosmic Velocities

## Introduction

Escape velocity is the minimum speed an object must achieve to break free from a celestial body's gravitational influence without additional propulsion. This concept extends to different cosmic velocities, which dictate orbital and interstellar travel conditions. Understanding these velocities is fundamental in astrophysics, rocketry, and space exploration.

The study of these velocities helps scientists and engineers design space missions, launch satellites, and send probes to other planets and beyond. Without these fundamental concepts, space exploration would not be feasible.

## Motivation

The study of escape and cosmic velocities is essential in:
- Launching satellites into stable orbits around planets, ensuring continuous communication and Earth monitoring.
- Planning interplanetary missions, such as those to Mars and Jupiter, where correct velocity calculations determine mission success.
- Exploring interstellar travel concepts, allowing us to send probes beyond our solar system, such as the Voyager missions.
- Understanding the effects of gravitational fields on motion in space, which influences trajectories of asteroids, comets, and artificial spacecraft.

These principles are directly applied in space missions, from launching satellites into geostationary orbits to propelling spacecraft beyond our solar system.

## Mathematical Derivations and Parameters Affecting These Velocities

### **Mathematical Derivation of First Cosmic Velocity**
The first cosmic velocity is derived by equating the gravitational force acting on an orbiting object with the required centripetal force to maintain a stable circular orbit:
   
   \(
   F_g = F_c
   \)
   
   **where:**

   - \( F_g = \frac{GMm}{R^2} \) **(gravitational force)**

   - \( F_c = \frac{m v^2}{R} \)  **(centripetal force)**

   
   Equating these two expressions:
   
   \(
   \frac{GMm}{R^2} = \frac{m v_1^2}{R}
   \)
   
   Canceling mass \( m \):
   
   \(
   v_1 = \sqrt{\frac{GM}{R}}
   \)
   
   **Factors Affecting First Cosmic Velocity:**
   - **Mass of the Celestial Body (\( M \))**: A higher mass results in a stronger gravitational pull, requiring a higher orbital velocity.
   - **Radius of the Celestial Body (\( R \))**: A larger radius decreases the required orbital velocity as gravitational attraction weakens with distance.

### **Mathematical Derivation of Second Cosmic Velocity**
The escape velocity (\( v_2 \)) is derived by considering the total mechanical energy of an object attempting to escape the gravitational field of a planet. The total energy must be zero for the object to escape indefinitely:
   
   \(
   E_{	ext{total}} = E_k + E_p = 0
   \)
   
   **where:**
   - Kinetic energy: \( E_k = \frac{1}{2} m v_2^2 \)
   
   - Gravitational potential energy: \( E_p = -\frac{GMm}{R} \)
   
   Applying energy conservation:
   
   \(
   \frac{1}{2} m v_2^2 - \frac{GMm}{R} = 0
   \)
   
   Solving for \( v_2 \):
   
   \(
   v_2 = \sqrt{\frac{2GM}{R}}
   \)
   
   **Factors Affecting Second Cosmic Velocity:**
   - **Mass of the Celestial Body (\( M \))**: A larger mass increases the required escape velocity.
   - **Radius of the Celestial Body (\( R \))**: A larger radius decreases the escape velocity.
   - **Atmospheric Drag**: Presence of an atmosphere increases the required velocity due to resistance.

### **Mathematical Derivation of Third Cosmic Velocity**
The third cosmic velocity (\( v_3 \)) is the speed needed to escape not just the planet’s gravitational field, but the entire gravitational influence of a star system (e.g., the Solar System). 
   
   It is determined by the escape velocity from the planet and the orbital velocity of the planet around the star:
   
   \(
   v_3 = \sqrt{v_{	ext{esc,planet}}^2 + v_{	ext{orbital}}^2}
   \)
   
   **Factors Affecting Third Cosmic Velocity:**
   - **Orbital Velocity of the Planet**: If a spacecraft is launched in the direction of planetary motion, it gains additional velocity.
   - **Star’s Gravitational Influence**: A stronger gravitational field increases the required velocity to escape the system.
   - **Additional Propulsion**: Spacecraft may require additional propulsion systems to reach the required velocity.

## Summary of Escape and Cosmic Velocities
| Celestial Body | First Cosmic Velocity (km/s) | Escape Velocity (km/s) |
|---------------|-----------------------------|-------------------------|
| Earth         | 7.91                        | 11.19                   |
| Moon         | 1.68                        | 2.38                    |
| Mars         | 3.55                        | 5.03                    |
| Jupiter      | 12.44                       | 59.5                    |

This analysis comprehensively explains how cosmic velocities are derived and the key factors influencing them. These velocities are fundamental in space exploration and rocket science.