# Problem 2: Estimating Pi using Monte Carlo Methods

## Introduction
Monte Carlo methods are a class of computational algorithms that rely on random sampling to obtain numerical results. The method is particularly useful when dealing with problems that are difficult or impossible to solve analytically. One of the most famous applications of Monte Carlo methods is estimating the value of π. By employing randomness and probability, we can estimate π through simulations involving geometric probability.

The most common Monte Carlo approach to estimate π involves generating random points within a square and determining how many of them fall inside a circle inscribed within that square. This method, despite its simplicity, effectively demonstrates the power of random sampling in solving complex problems. Another interesting technique for estimating π is Buffon’s Needle problem, which uses probability theory to approximate π by analyzing how often a randomly dropped needle crosses parallel lines.

Monte Carlo methods are particularly useful because they allow for estimating values through repeated random sampling, which often provides an accurate approximation even when the exact solution is difficult to determine. As the number of samples increases, the accuracy of the approximation improves, illustrating a fundamental property of statistical convergence.

This problem provides insights into the fundamentals of probability, numerical computation, and statistical convergence. Through these exercises, we can better understand the efficiency and accuracy of Monte Carlo methods in approximating important mathematical constants like π. Additionally, understanding these concepts allows us to apply similar methods to a wide range of problems beyond mathematics, including physics, finance, and various fields of engineering.

---

## Motivation
Monte Carlo simulations are a powerful class of computational techniques that use randomness to solve problems or estimate values. One of the most elegant applications of Monte Carlo methods is estimating the value of π through geometric probability. By randomly generating points and analyzing their positions relative to a geometric shape, we can approximate π in an intuitive and visually engaging way.

This problem connects fundamental concepts of probability, geometry, and numerical computation. It also provides a gateway to understanding how randomness can be harnessed to solve complex problems in physics, finance, and computer science. The Monte Carlo approach to π estimation highlights the versatility and simplicity of this method while offering practical insights into convergence rates and computational efficiency.

Furthermore, the use of Monte Carlo methods in estimating π showcases the broader applicability of these techniques, particularly in scenarios where deterministic approaches may be too complex or computationally expensive to implement. The accuracy of the approximation increases as the number of random points or needle drops increases, providing a valuable example of how statistical methods converge towards true values.

---

## Part 1: Estimating π Using a Circle

### 1. Theoretical Foundation

The Monte Carlo method for estimating π is based on the area ratio between a circle and the square that bounds it. This method utilizes geometric probability to achieve a numerical approximation of π through random sampling.

#### Explanation and Derivation

Consider a **unit circle** centered at the origin `(0, 0)` and enclosed within a square of side length `2` (spanning from `-1` to `1` along both axes).


- The area of the square is calculated as the square of its side length:

  $$
  A_{square} = (2)^2 = 4
  $$

- The area of the circle is given by the formula for the area of a circle:
  $$
  A_{circle} = \pi r^2 = \pi (1)^2 = \pi
  $$

- Therefore, the ratio of the area of the circle to the area of the square is: 
  $$
  	\text{Ratio} = \frac{A_{circle}}{A_{square}} = \frac{\pi}{4}
  $$


Now, we can use **Geometric Probability** to relate this ratio to a simulation:
- We randomly generate points `(x, y)` within the square with coordinates satisfying:

  $$
  -1 \leq x \leq 1, \quad -1 \leq y \leq 1
  $$

- The probability that a randomly generated point falls inside the circle is equal to the ratio of the circle’s area to the square’s area.

According to the probability definition:

$$
	\text{Probability} = \frac{\text{Number of points inside circle}}{\text{Total number of points}} = \frac{\pi}{4}
$$

By rearranging, we can estimate \( \pi \) as follows:

$$
\pi \approx 4 \times \frac{\text{Number of points inside circle}}{\text{Total number of points}}
$$

### 2. Simulation

1. Generate random points `(x, y)` where both `x` and `y` are uniformly distributed between `-1` and `1`.

2. Count the number of points that fall inside the unit circle by checking if:

$$
x^2 + y^2 \leq 1
$$

3. Estimate π using the formula derived above.

### 4. Analysis

- As the number of points increases, the estimate of \( \pi \) becomes more accurate.

- The convergence rate follows the law of large numbers and is proportional to:

  $$
  	\text{Estimation Error} \approx \frac{1}{\sqrt{N}}
  $$

  Where `N` is the total number of random points.


---

## Part 2: Estimating π Using Buffon’s Needle

### 1. Theoretical Foundation

Buffon’s Needle problem is a classic Monte Carlo simulation used to estimate \( \pi \) based on probability.

#### Description and Derivation

Consider a floor with equally spaced parallel lines separated by a distance `d`. A needle of length `L` is randomly dropped onto this plane. We want to determine the probability that the needle crosses one of the lines.

If \( L \leq d \), the probability of crossing a line depends on two random variables:

**θ:** The acute angle between the needle and the parallel lines, which is uniformly distributed between \( 0 \) and \(\frac{\pi}{2}\)

**x:** The distance from the midpoint of the needle to the nearest line, uniformly distributed between \( 0 \) and \(\frac{d}{2}\).

The needle crosses the line if:

$$
x \leq \frac{L}{2} \sin(\theta)
$$

Calculating the probability involves integrating over all possible values of \( 	heta \):

$$
P = \frac{2}{\pi} \int_{0}^{\frac{\pi}{2}} \frac{L}{d} \sin(\theta) d\theta = \frac{2L}{\pi d}
$$

Rearranging to solve for \( \pi \):

$$
\pi \approx \frac{2L}{dP}
$$

### 2. Simulation

- Randomly drop a needle onto the plane.

- Check if the needle crosses a line based on its midpoint and orientation.

- Repeat for many iterations to calculate the probability.

- Estimate \( \pi \) using the derived formula.

### 4. Analysis

- As the number of needle drops increases, the estimate of \( \pi \) becomes more accurate.

- The convergence rate is slower compared to the circle-based Monte Carlo method, making it less efficient for practical computation.

---

## Deliverables
1. A detailed Markdown document with explanations and mathematical derivations.
2. Python code for implementing both methods (To be done).
3. Graphical outputs and visualizations (To be done).
4. Analysis comparing the two methods in terms of accuracy and computational efficiency.

