# Final Project Calculus in Coding - Monte Carlo Integration
In this project, I will be exploring the theory behind Monte Carlo Integrations, and how Monte Carlo methods can be used to calculate the area under a curve. If time allows, I will use the Monte Carlo simulation to model the final point of contact of a kV photon and their final energy at that point. 

## Introduction to Monte Carlo Methods and Integration
Monte Carlo Methods refer to a class of algorithms that use random sampling and/or probability density functions (PDFs) to determine the most likely outcome of a situation with random variables. This outcome is an approximation of the expected value of a function. In it's simplest form, the Monte Carlo method finds the expected value by finding the sum of all possible values of $$x$$ and then divides this number by the total number of possible values: $$E(X) \approx \frac{1}{N}\int_{n=1}^{N}x_n$$

Monte Carlo integration is an integration method that uses the Monte Carlo methods to find the area within a speciic boundary. In this case, a Monte Carlo simulation with uniform distribution is used. The approximation that Monte Carlo Methods use can be described well by the image below: 

![image](https://github.com/user-attachments/assets/f4ee50e3-6dac-48db-a52e-6cc6ab3512a4)

In this method, we start with a function $$f(x)$$ as shown above. To find the approximation of the area under the curve, we use $$x$$ as the random variable in the Monte Carlo simulation. For each random value of $$x$$, we calculate the area $$A_x = (b-a) * f(x)$$. This gives us a rectangle of area $$A$$. When the sum of all of these areas is calculated, then divided by the number of random samples taken, an approximation to the area under the curve $$A = \int_{a}^{b}f(x)dx$$. 

This process can be represented by the basic Monte Carlo Estimator:  $$\bar{A}_N = (b-a) * \frac{1}{N}\sum_0^{N-1} f(x_i)$$. As the number of samples $$N$$ approaches infinity, the estimated area $$\bar{A}_N$$ approaches the true value of the integral.

In this Monte Carlo simulation, samples are randomly taken over the sample space $$x_i = a + \xi(b-a)$$ with the PDF $$x_i = \frac{1}{(b-a)}$$. Using a uniorm PDF in Monte Carlo Integration is important - if we have more samples distributed around an arbitrary point $$x_a$$ then the total area will be skewed to be closer to the area of the rectangle $$(b-a) * x_a$$.

## Why Use Monte Carlo Integration
Monte Carlo Integration is similar to taking the Riemann sum of rectangles under the curve to find the total area. Both methods converge to the calculated value of the integral as $$N$$ approaches infinity. However, taking the Riemann sum suffers from the curse of dimensionality. As the number of dimensions in the sample space $$d$$ increases, the Riemann sum method takes longer to converge, with the convergence rate increasing as a function of $$n^{\frac{-1}{d}}$$. In contrast, the convergence rate of the Monte Carlo method remains at $$ n^{\frac{-1}{2}}$$ regardless of the dimensionality of the sample space. 

I will not be using high-dimensionality sample spaces for this project as I believe it is beyond it's scope, but it is interesting to see what the benefits of Monte Carlo Integration can be. 

## What is Monte Carlo Integration used For?
Monte Carlo Integration is used most commonly in applications like ray tracing and shading in video games. It is also used in


## Sources
- [PubMed - Introduction to Monte Carlo](https://pmc.ncbi.nlm.nih.gov/articles/PMC2924739/)
- [Monte Carlo Methods in Practice](https://www.scratchapixel.com/lessons/mathematics-physics-for-computer-graphics/monte-carlo-methods-in-practice/monte-carlo-integration.html)
- [Mathematical Foundations of Monte Carlo Methods](https://www.scratchapixel.com/lessons/mathematics-physics-for-computer-graphics/monte-carlo-methods-mathematical-foundations/quick-introduction-to-monte-carlo-methods.html)
- [Monte Carlo Integration](https://www.scratchapixel.com/lessons/mathematics-physics-for-computer-graphics/monte-carlo-methods-in-practice/monte-carlo-integration.html)
- [Introduction to Monte Carlo Methods](https://www.stats.ox.ac.uk/~rebeschi/teaching/AdvSim/18/notes/notes1.pdf)
