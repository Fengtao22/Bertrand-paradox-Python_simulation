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

![Method 1](https://github.com/Fengtao22/Bertrand-paradox-Python_simulation/blob/main/Method1.gif)

![Method 2](https://github.com/Fengtao22/Bertrand-paradox-Python_simulation/blob/main/Method2.gif)

![Method 3](https://github.com/Fengtao22/Bertrand-paradox-Python_simulation/blob/main/Method3.gif)


### Results analysis
Three different approaches result three different conclusions. The main reason is due to the ambiguity on how to get the chord randomly. Through the implementation, we can easily see that method 2 and method 3 differ in how to get the middle point. In particular, method 2 adopts sqrt(U) in the direction of radius while method 3 adopts U distribution directly. Method 2 focuses on getting the middle point uniformally within the 2D area and method 1 focuses on uniformally within 1D line. Method 1 is special by summing two independent uniform distributions. It is worth mentioning that the distribution of the sum is a triangle distribution (not a uniform!!) (https://math.stackexchange.com/questions/357672/density-of-sum-of-two-independent-uniform-random-variables-on-0-1).  

We can verify the distribution differences for the middle points on the three approaches:
![](https://github.com/Fengtao22/Bertrand-paradox-Python_simulation/blob/main/Method1_middle_points.png)
![](https://github.com/Fengtao22/Bertrand-paradox-Python_simulation/blob/main/Method2_middle_points.png)
![](https://github.com/Fengtao22/Bertrand-paradox-Python_simulation/blob/main/Method3_middle_points.png)
