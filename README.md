# Bertrand-paradox-Python_simulation
This is a small simulation experiment to test different sampling distributions for the random chord choice. Part of the code is using https://github.com/czimbortibor/Bertrand-paradox as a reference. In particular, the modifications are:

- Adjust the circle plot so that it looks more like a circle through "ax.set_aspect('equal')".
- Generate a dynamic plot instead of static figure.
- Use a dynamic point instead of one fixed point for all three methods.
- Further analysis on the different results with respect to the three methods.
- I also provide some code samples for generating gif images (commented)

### Background
Bertrand paradox (https://en.wikipedia.org/wiki/Bertrand_paradox_(probability)) is an interesting probability question, that is, to draw the chord "randomly" in a circle and what is the probablity for the length of chord is greater than sqrt(3)*r (r is the radius of the circle). 

### Existing but paradox solutions

- Method 1: Select two points in the circumference uniformally and independently. This is implemented by randomly selecting two angles and then deriving the two points. **Its theoretical result/probablity should be 1/3**.

- Method 2: Randomly select the middle point of this chord within the 2D circle. This is implemented by randomly selecting the radius angle (the chord will be perpendicular with this radius), then use the sqrt(U)*r probability distribution to determine the intersection point (the chord and the radius), which would be the middle point of the chord. Here U represents uniform distribution and the reason we take sqrt(U) is to make sure the area increment is constant. **Its theoretical result/probablity should be 1/4**.

- Method 3: Randomly select a radius, then get the middle point within this radius uniformally. **Its theoretical result/probablity should be 1/2**. 

### Simulation verification

