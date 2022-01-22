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
## 3 Picking a random point correctly 
### 3.1 
For this question, you have to pick random points in a circle in a uniform manner. The most intuitive approach for this is usually to pick a random number, r, from the uniform distribution between 0 and R, where R is the radius of the circle. Similarly, one can pick the angle θ in a similar manner and generate x, y coordinates from them. Implement a function that takes in a radius, R, and samples a large number of points in the described manner. The function should generate a scatter plot containing all the sampled points, as well as plotting a circle of the appropriate radius, Find and mention the variation in the x-coordinates as well.
### 3.2
This, however, does not result in a uniform pick.2 You may spot this from the plot which should have points concentrated more towards the center rather then points being uniformly spread out across the circle. Change the number points you are plotting if you do not observe this trend. Now instead of generating r and θ values we will generate x and y values uniformly. To generate random points on a circle of radius, R, pick both x and y independently and uniformly from the range [−R, R] to obtain a point. If the distance of this point from the origin is more than R, discard it and generate a new point in its place. Implement a function that takes in a radius, R, and samples a large number of points in the described manner. The function should generate a scatter plot containing all the sampled points, as well as plotting a circle of the appropriate radius, Find and mention the variation in the x-coordinates as well. Comment on why this found variation is different or same as in the previous part.
### 3.3
To get an intuition of why the first approach does not result in a uniform pick imagine a circle of radius 1 embedded in a circle of radius 2 as shown in Fig.2. If points are picked randomly, the probability of the point lying inside the larger circle should be 4 times than the smaller one. Does this hold when the above described method to pick r and θ is used? Explain in report with working.

![pro4](https://user-images.githubusercontent.com/60126292/150655782-2fbb1b23-7e94-4989-a674-eb6dae024404.PNG)

In this part, modify one or both of the ways to pick r and θ, such that the points are sampled in a uniform manner and a plot similar to that in part 2 is obtained. Implement a similar function as the above part. The plot generated this time should contain points that are uniformly spread across the circle. Describe how are you picking the random variables and find the variance of the x-coordinates once again and comment on your results. If you feeling up to it or for a bonus then you may derive the distribution from the following two facts. The probability of a point to lie inside a circle of radius, r ≤ R is proportional to its area. i.e. P(r ≤ R) = k · πr2. The probability of it lying inside the outermost circle of radius, R, should be 1 i.e. P(R ≤ R) = 1. After finding the distribution that r follows, you may then generate the values of r appropriately by mapping from the uniform random distribution as in the previous questions. Show all mathematical working.
## 4 Saying random is not enough - Approaches effect distributions 
In this question we are going to observe the distribution followed by the length of a random chord picked from a circle of radius r. The difficulty of the question lies in how to pick a random chord in a circle. For each of the described approaches implement a different function that takes in radius, r and plots a histogram of the length of chords with an appropriate number of bins, with proportion (probability) of values in the bin on y-axis instead of counts. Include mathematical calculation of chord lengths in all parts.
### 4.1
For the first approach we imagine the circle centred on the origin of the Cartesian plane. The θ = 0 ray/line is defined as starting at the origin and pointing in the direction of increasing x, and theta increasing counter clockwise. We pick two angles θ1 and θ2 uniformly between 0 and 2π, and our random chord is the chord between the points of the circle defined by those two angles.

![pro5](https://user-images.githubusercontent.com/60126292/150655833-1abf7692-b407-4d07-a6d7-926f5211b45e.PNG)

### 4.2 
For the second approach we imagine the circle in a similar manner. Then we pick a random direction, θ, and draw a line from the center of the circle to its boundary such that the angle from the ray θ = 0 to this line, measured counter clockwise is θ. To create a random chord, we pick a point along this line and construct the perpendicular bisector of the line at this point. The perpendicular bisector can be extended to touch the boundary of the circle at either ends to obtain a chord.

![pro6](https://user-images.githubusercontent.com/60126292/150655857-06440108-4757-4f97-b4ae-614e5f6ed08e.PNG)

### 4.3
For the third approach we again visualize the circle as before. This time we pick a random point uniformly from the circle as we did in the previous question. You may use any helper functions you may have developed in the previous part for this. After picking a point we find the chord which will have this point as it midpoint and this will be our random chord. There will be only one such chord.

![pro7](https://user-images.githubusercontent.com/60126292/150655875-54f636a0-b71a-4893-88b3-74a4112aba66.PNG)

## 5 Hypothesis Testing
Intuition - If someone hands you a coin, and tells you its fair, you toss it 15 times and get 15 heads, you are going to be skeptical. That is the essence of hypothesis testing, we make a certain assumption, and then sample some data. If the sum of probability of obtaining the observed data or data less or equally likely is less than a certain threshold then we conclude our assumption to be false. The statement ‘or data less likely’ is a little vague and more importantly problem dependent. Let use look at a concrete example. Suppose you have a coin which we do not know as fair or not. We assume that the coin is fair. This is known as the null hypothesis. The alternative hypothesis is that the coin is not fair. We then set a certain threshold, and declare that given our assumption if the observed data or data less or equally likely has a total probability less than this threshold we will reject our assumption. Let us set the threshold at 0.05. We toss the coin 15 times and obtain 15 heads. The probability of this happening given that the coin is fair is (1/2)^15 ≈ 0.00003. An event that is less or equally like is getting 15 tails, with a probability of 0.00003 as well. The cumulative of these is 0.00006 which is less than our threshold, therefore we reject the null hypothesis. Suppose instead that we had tossed the coin 10 times and obtained 2 heads, while using the threshold of 0.1. The events equally or less likely are getting 2 or less heads and 2 or less tail, the sum of whose probabilities is 0.109375, which is greater than our threshold. Therefore, we declare that the null hypothesis is valid, and an unlikely but not too unlikely possibility has occurred. It may be argued that in the former case as well, the coin could have been fair and it was only that an unlikely possibility had occurred. The argument is valid, and when it comes to simulations, one can rectify this problem by repeating several times to obtain an expected value, and then repeating the entire experiment multiple times, to get a distribution of the expected values as we did in the previous questions. In real life, however, we hardly have such liberties, such as when conducting surveys, and therefore hypothesis testing remains a reliable method. Of course, we could be wrong sometimes to reject the null hypothesis but we would be right most of the time. That’s just how probability works.







