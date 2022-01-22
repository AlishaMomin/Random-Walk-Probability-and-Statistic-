# Random-Walk-Probability-and-Statistic-
## Purpose
The purpose of this project is to familiarize students with the realization of probabilistic methods with simulations and coding. 
The first question introduces the idea of calculating expected value through multiple simulations. Furthermore, students should come to realize that the expected value found through this way may lie close or far from the theoretical value. Thus, it is useful to calculate the expected value several times and plot it to experience the often normal distribution that expected values follow.
The aim of the second question is to teach students to pick values from an arbitrary distribution. Since, the only true random number generator is computers is uniform, students must learn to simulate different distributions by mapping from the uniform distribution. They need to be aware of the both the computational and mathematical side of it. 
The third question is aimed at addressing natural biases when modelling a scenario. Students must come understand what assumptions they can or cannot make, and what assumptions are at work without their knowledge. 
The fourth question takes this concept a step further by showing that simplify specify the scenario to modelled without specifying the method is also not enough, as different methods to model a single scenario can result in different distributions. 
Question five aims to help students understand and apply what they have learned to understand overarching concepts, in this case hypothesis testing, a concept independent of the underlying choice of distribution. It also introduces them to more practical probability and teeters on the edge of statistics.
## 1 Random Walk 
Random walk– a random walk is a mathematical object, known as a stochastic or random process, that describes a path that consists of a succession of random steps on some mathematical space such as the integers. Mathematical modelling of the movement of animals, micro-organisms and cells is of great relevance in the fields of biology, ecology and medicine.
### 1.1 
A very simple random walk can be simulated by imagining an object starting at x = 0 on a number line. The object is going to take an n number of steps of one unit each, where each step can be right or left with probabilities p and 1 −p respectively.

![pro](https://user-images.githubusercontent.com/60126292/150655588-ca52d94b-5e84-4811-9197-170ec95604b4.PNG)

Intuitively one can judge that if p = 0.5, then the object will return to its starting position often, or at least close to it. We are going to confirm this using simulation. Implement a function that takes in two parameters n and p. It should take, n, number of steps left or right, as dictated by the probabilities and note the final position of the object. This should be repeated several items, which we will call iterations, and the expected value of the objects final position should be calculated using these iterations. The expected value will not come out to be zero every time even if appropriate probabilities are passed. Thus, the procedure/experiment must be repeated several times, to obtain several expected values. Plot the histogram of these expected values to observe if they follow some trend. Tune the bin width, bin count, number of iterations, number of experiments as you see fit to make the trend obvious. Mention them in your report. Repeat this with a different value of p. You may work out the expected final position for arbitrary n and p for a bonus. Some good approaches for this are the Bernoulli random variable and the Binomial Random variable. Include full working in your report if you do.
### 1.2 
Now we are going to simulate the same random walk with an added constraint. Namely, that going into the negative part of the number line is not allowed. Therefore, at any time the object finds itself at x = 0, the only option it has is to move in the positive direction. Implement a function that takes in parameter, n and p, and does exactly what the above the function does. Plot a histogram of expected values and discuss your results.
### 1.3 
Removing the constraint of the previous question, we will now note the number of steps it takes for two objects initialized at different points, and moving randomly to meet. Implement a function that akes in 4 parameters, the start position of object 1, the start position of object 2, the probability of object 1 to move right and the probability of object 2 to move right. It conducts a large number of experiments each with several iterations, to collect a number of expected values for the number of steps it takes for the two objects to meet. It should plot the expected values in a histogram. You may assume that the initial distance between the objects is an even number.
## 2 Simulating Distributions
Look at the following algebra and examine the accompanying code. Let X follow a uniform distribution between 0 and 1. The probability that X is less than some number, x, is P(X < x) = x. Suppose we want Y to follow a random distribution for which we do not have any in built functions. Let Y follow the distribution fY (y) = e−y for y ≥ 0. The following trick is used to derive the relation between X and Y.

![pro1](https://user-images.githubusercontent.com/60126292/150655647-0ab1bc33-5005-4e2d-968f-842215d85a7f.PNG)

### 2.1 
Does the code accomplish simulating the distribution? Which distribution does it follow? Try running the code with different number of bins. Attach plots and discuss your results.
### 2.2 
Examine the following section of code and mathematically deduce what distribution Y follows (Try working the above trick in reverse starting with the last statement). Show all required working.

![pro2](https://user-images.githubusercontent.com/60126292/150655681-464501c3-f56a-47a4-9c17-a855ce6db989.PNG)

### 2.3 
Implement a function that returns a random variable from the distribution,
![pro3](https://user-images.githubusercontent.com/60126292/150655701-947d516f-2657-4ef9-b280-821456870687.PNG)
Use it to produce a histogram and line plot like the above code. Implement a different function that calculates the expected value using the experiments and iterations approach and plots the set of expected values obtained. You may need to utilize the trick pointed to in the above lines and choose an appropriate cutoff for both of these.




