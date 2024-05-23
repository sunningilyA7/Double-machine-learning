# Double-machine-learning


Case and Source of code: Causal Inference for The Brave and True https://matheusfacure.github.io/python-causality-handbook/landing-page.html



Causal inference * double machine learning 


background

Observed data has bias

That means , there is feature X not also affecting Outcome Y, but also affecting treatment T.

So, before doing the causal inference, we need to do something that will let treatment T is independent from feature X. → that means : the observed data is from Randomized Controlled Trials, RCT

As a result, we can use the ‘Conditional Average Treatment Effect' CATE for the evaluation 


Ice cream case:
A simple method of debiasing is linear regression, where we fit a linear regression model and hold the other variables constant to estimate the average causal effect (ATE).
Sales_i = α + β₁price_i + β₂temp_i + β₃cost_i + β₄Weekday_i + e_i

ATE is the value of β₁
But the relationship between feature X and Y may be nonlinear.


regression residuals  – DML base minds

ATE- DML
In the case of causal inference, we only care about the effect of Treatment T on outcome Y, so we can first use X to regression T to get a residual of T, then use X to regression Y to get a residual of Y, and finally use the residual of T to regression the residual of Y. The estimated parameter is the ATE we want.

Using DML to estimate CATE 
Similarly, we first use ML to obtain the residual of T and the residual of Y based on X, and then use lr to fit the residual, the difference is that this time we add the interaction terms of X and T, i.e

Add interaction terms for X and T: 
In a linear regression model, in addition to including the residuals for 𝑇 T and 𝑌 Y, add interaction terms for 𝑋 X and 𝑇 T. This step is critical because it allows the model to evaluate changes in the effect of 𝑇 T on 𝑌 Y for different values of 𝑋 X. This helps to understand how the processing effect varies with covariates, the conditional average processing effect (CATE). 
With this approach, the researchers were able to more accurately estimate the average effect of treatment or intervention across different subpopulations (as defined by the covariate 𝑋 X), independent of potential confounding factors.

What this means is that in order to assess the model's ability to distinguish between units or consumers that respond strongly to price changes (high price sensitivity) and those that do not (low price sensitivity), the researchers intend to use a method called cumulative elasticity curves.

 Price sensitivity Price sensitivity, also known as price elasticity, is often used to describe the degree to which demand responds to price changes. 
A high price elasticity means that a small change in price can lead to a large change in quantity demanded, while a low price elasticity means that demand is less sensitive to price changes. 
A cumulative elasticity curve is a tool that helps visualize and quantify how different groups of consumers respond to price changes.

 Through this curve, researchers can analyze and compare the changes in demand of different consumers or units at different price levels. 
This curve is particularly useful for: Identifying consumer groups: By analyzing the cumulative elasticity curve, researchers can identify which consumers are particularly sensitive to price changes and which are less sensitive.
 Develop pricing strategies: Based on the understanding of the sensitivities of different consumer groups, companies can develop more effective pricing strategies, such as pricing more competitively for price-sensitive groups, while maintaining or raising prices for less price-sensitive groups.
 
 For example, in market analysis, a company might want to know which segment of consumers will stop buying and which segment of consumers will not be affected when it raises the price of its product.
 By accumulating elasticity curves, companies can anticipate and plan for these changes to optimize their marketing and pricing strategies across different market segments.
 In summary, this statement suggests that the researchers will use the cumulative elasticity curve as an analytical tool to evaluate and understand how well the model differentiates between consumers with different price sensitivities. This helps to further optimize the model's prediction

