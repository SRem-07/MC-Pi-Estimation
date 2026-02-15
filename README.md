# Monte Carlo Pi Estimation
This notebook estimates the value for Pi via the Monte Carlo method. 

## Mathematical Background
The Monte Carlo method estimates the value of $\pi$ by simulating random points within a defined geometric area.

**Geometric Approach:** <br />
We first consider a square with side length of 1, which encloses a quadrant of a unit circle. The following are hence true:
  * The area of the square is 1.
  * The area of the unit circle is $\pi r^2$. As we are using a unit circle ($r = 1$), the area is just $\pi$.
  * The area of the quadrant (inside the square) is hence $\pi/4$.

**Estimation Formula:**
We can generate a large amount of random coordinates $(x, y)$, where $0 \le x, y \le 1$. Using these coordinates, we can determine the ratio of points that fall inside the quadrant of the unit circle to the total number of points generated. 

As the number of points increases, this ratio approaches the ratio of the areas:

$$\frac{\text{Points Inside}}{\text{Total Points}} = \frac{\text{Area of Quadrant}}{\text{Area of Square}} = \frac{\pi/4}{1}$$

Therefore, we can estimate $\pi$ using the following equation:

$$\pi = 4 \times \frac{\text{Points Inside}}{\text{Total Points}}$$

**Computational Efficiency:**
To determine if a point $(x, y)$ lies within the circle, we check if its distance from the origin is less than or equal to the radius ($r = 1$ as it is a unit circle), using the following:

$$\sqrt{x^2 + y^2} \le 1$$

However, as the radius of the circle is 1, we can simplify the above. This can improve computational efficiency by using the simplified form, which is as follows:

$$x^2 + y^2 \le 1^2 \implies x^2 + y^2 \le 1$$

## Features
* Chunking for estimations with a large amount of iterations for memory management and efficiency.
* Visualisation of the estimation method and where randomly generated points fall.
* Visualisation of the convergence of estimations to Pi itself (and how error decreases with more iterations).

## Dependencies
* NumPy
* Matplotlib
* Pandas

## Overview
This notebook uses tools like NumPy, Matplotlib and Pandas to estimate Pi through the Monte Carlo method. This notebook served as a way for me to learn, and apply, the Monte Carlo method. 

Accurate estimations require many simulations/iterations, however this puts a great amount of load on the memory. To combat this, I was also able to use some memory management techniques - my first exposure to such. 

## Usage
You can clone and use the notebook using the following:
``` bash
git clone https://github.com/SRem-07/MC-Pi-Estimation.git
```
You can install the required libraries for the notebook using:
``` bash
pip install -r requirements.txt