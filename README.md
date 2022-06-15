# Final-Submission

Our primary approach and documentation is included in Jupyter Notebook, while this readme.md focus on other potential approach we could be creating if time allows.

Alternative Approach on Q3 if time allows - Create diet plan with Modern Portfolio Theory(Without tensorflow) | It definitely sounds incredibly dumb below as time and indicator values of food product are still not clear.

#1, With PyPortfolioOpt
Maximise nutrition level while minimize carbon emission across the world? Doesn't that sounds like 'Maximize return and minimize risk'? When we are managing a portfolio? </br>

Modern Portfolio Theory(MPT) or mean-variance analysis is a mathematical model for creating portfolio which aims to maximize the return for a given amount of risk. The assumption is that we only accept a less risky portfolio. The risk mitigation can be done by either investing in traditional safe havens or by diversification. The disadavantage of MPT is it doesn't look at trends or use any predictive analytics which is ill-suited for modern portfolio construction, but in our case of creating diet that meets daily nutrition intake requirement but minimise carbon emission, without any predictive analytics -- theoretically, it is a great approach. </br> 

1,Diet Plan's Expected Nutrition Value | Portfolio Expected Return:  The portfolio expected return of a portfolio is calculated by multiplying the weight of the asset by its return and summing the values of all the asset together. In our practice we could calculate the diet plan by multiplying the nutrition value of each food as weight and summing the value of all food's nutrition. </br>

2, Diet Plan's Carbon Emission | Portfolio Variance: used as th measure of risk and in our case we want to have the minimum amount of carbon emission as possible(super low risk). The tricky part is carbon emission of each food seem to decrease overtime and it doesn't change/have the volatility as we want in asset class - yes we don't have a solution for that yet. </br>

3, Diet Plan's nutrition intake in relation to Carbon Emission | Sharpe Ratio: The higher the sharpe ratio within similar risk, the better. Same as our nutrition plan, the higher nutrition intake the better.</br>

4, The Optimal Diet Plan | Efficient Frontier: The plot measure risk vs returns and in our case lowest carbon emission and highest nutrition intake. </br>

An example of how the chart could look like can be seen below:
![image](https://user-images.githubusercontent.com/79988376/173869178-f975968b-456c-4970-85da-90a1dad2d309.png)

We took a pre-built python package called PyPortfolioOpt and tried to twix around it but due to time constraint we couldn't finish.</br>

#2, With DeepDow</br>
DeepDow is a Python package that focuses on neural networks that perform asset allocation in a single forward pass. DeepDow is one of the Deep Learning Package simplifies financial timeseries data processing for portfolio optimisation. The hustle of calculating standard deviation, mean, variance across time series data narrowed down to three core ideas as 3D tensor with following dimensions: 
1) Time
2) Asset
3) Indicator/Channel

![image](https://user-images.githubusercontent.com/79988376/173870481-75675751-4c04-49d7-8530-dbd4dd77e402.png)

While training a time step(current) we can split food carbon emission to 3 disjoint subtensors.
![image](https://user-images.githubusercontent.com/79988376/173871291-2472234c-0954-4231-b66e-e187ba2773b6.png)
We'd be focusing on a special type of neural networks that input nutrition value and return a single weight allocation w overall assets such that they sum up to 1. 
![image](https://user-images.githubusercontent.com/79988376/173871484-2a1d08e4-e3b6-4b1c-9499-88de748a7f33.png)

Reference: 
1, Automating Portfolio Optimisation using Python https://towardsdatascience.com/automating-portfolio-optimization-using-python-9f344b9380b9
2, Foundation of Portfolio Theory, Harry M. Markowitz, Journal of Finance, 1991
3, Deepdow Documentation: https://deepdow.readthedocs.io/en/latest/auto_examples/end_to_end/getting_started.html#preliminaries
4, Deep Learning for Portfolio Optimisation, Zihao Zhang, Stefan Zohren, Stephen Roberts, https://arxiv.org/abs/2005.13665
5, Single Forward Pass https://morioh.com/p/e8bd82d1f622
