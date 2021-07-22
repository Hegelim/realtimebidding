## Summary

1. *Optimal Auctions* - Provide a theoretical base on how to set an optimal reserve price such that it maximizes the revenue for the publisher. 
2. *Optimal Auction Design* - Provide mathematical proof on how to design an optimal auction mechanism that maximizes the revenue for the publisher. 
3. *Yield Optimization of Display Advertising with Ad Exchange* - A practical implementation of the bid-policy algorithm based on Optimal Auctions and Optimal Auction Design. 
4. *Reserve Prices in Internet Advertising Auctions: A Field Experiment* - The first large scale field study on Yahoo! sponsored search engine that shows the importance and practicality of setting an optimal reserve price in increasing the revenue. 
5. *Pricing Analysis in Online Auctions using Clustering and Regression Tree Approach* - Show the improvements in predicting the end-price in auctions using clustering and regression trees. 
6. *Multiple Linear Regression with Kalman Filter for Predicting End Prices of Online  Auctions* - Show that MLRKF model effectively reduces training time and increases training accuracy in predicting end prices in auctions. 
7. *An Empirical Study of Reserve Price Optimization in Real-Time Bidding* - Propose an algorithm OneShot for publisher revenue optimization in Real-Time Bidding (RTB) and compares its performance with several other commonly adopted algorithms. 
8. *Optimal Reserve Prices in Upstream Auctions: Empirical Application on Online Video Advertising* - Derive a new downstream-corrected reserve price compared to the classical optimal monopoly price in the context where there is a upstream auction and a downstream auction. 
9. *Learning Algorithms for Second-Price Auctions with Reserve* - Predict a beneficial reserve price with a combination of historical data and user features. 
10. *A Dynamic Pricing Model for Unifying Programmatic Guarantee and Real-Time Bidding in Display Advertising* - Figure out an optimal percentage of future impressions to sell in advance and provides an explicit formula to calculate at what prices to sell. 
11. *Information Disclosure in Real-Time Bidding  Advertising Markets* - Find equilibrium information disclosure strategies for  publishers in a RTB impression auction game. It shows information disclosure is profitable for publishers (142).
12. *Optimal Real-Time Bidding for Display Advertising* - Design an optimal bidding strategy for DSP. 
13. *Optimal Real-Time Bidding Strategies* - Design an optimal bidding strategy for DSP. 
14. *Real-time Bidding for Online Advertising: Measurement and Analysis* - Analyze the behavior of RTB including bids' distributions, daily pacing, periodic patterns, etc through data. 
15. *Predicting Winning Price in Real Time Bidding with Censored Data* - learn the winning price, in the aspect of a DSP, with historical RTB bids and to deal with the problem of various winning price censoring at the same time. 

## Closely related articles

1. Optimal Auctions 
2. Optimal Auction Design 
3. Reserve Prices in Internet Advertising Auctions: A Field Experiment
4. An Empirical Study of Reserve Price Optimisation in Real-Time Bidding
5. Multiple Linear Regression with Kalman Filter for Predicting End Prices of Online Auctions
6. Real-time Bidding for Online Advertising: Measurement and Analysis
7. Learning Algorithms for Second-Price Auctions with Reserve
8. Reserve Price Optimization at Scale
9. Information Disclosure in Real-Time Bidding  Advertising Markets
10. Predicting the final prices of online auction items

## Terminology

* **<u>Real-time bidding (RTB)</u>**-  the process in which digital advertising inventory is bought and sold. This process occurs in less than a second (usually less than 100ms [5, 14]) It allows advertisers to bid for impressions based on targeted audiences [7] on a per-access bases [5].
* **<u>Vickrey Auction (Second price auction)</u>** [link](https://en.wikipedia.org/wiki/Vickrey_auction)- a type of sealed-bid auction. Bidders submit written bids without knowing the bid of the other people in the auction. The highest bidder wins but the price paid is the second-highest bid. This type of auction gives participants an incentive to reveal their true valuation of the item [5].
* **Generalized second-price auction (GSP)** [link](https://en.wikipedia.org/wiki/Generalized_second-price_auction) - a non-truthful auction mechanism for multiple items. Each bidder places a bid. The highest bidder gets the first slot, the second-highest, the second slot and so on, but the highest bidder pays the price bid by the second-highest bidder, the second-highest pays the price bid by the third-highest, and so on.
* **Public Information** - the information that are available to the public during auctions. In online bidding, it can be user information [10].
* **Private Information** - the information that is not available to the public. For example, the bidder's valuation of the item. 
* **Publisher** - a person or a company that displays ads on their digital space. 
* **Advertiser** - a person or company that advertises a product, service, or event.
* **Supply-side platform (SSP)** - a supply-side platform or sell-side platform is a technology platform to enable web publishers and digital out-of-home media owners to manage their advertising inventory, fill it with ads, and receive revenue.
* **Demand-side platform (DSP)** - a demand-side platform is a system that allows buyers of digital advertising inventory to manage multiple ad exchange and data exchange accounts through one interface.
* **Ad Exchange** - where advertisers bid and compete between each other for an ad slot. The winner then pays the publisher and his ad is displayed.
* **<u>User attributes (Impression attributes/user information/public information [10])</u>** - a vector of attributes $U_i \in \mathcal{U}$ where $\mathcal{U}$ is some finite subset of $\mathbb{R}^M$ that uniquely identify users/impressions. For instance, the web address, user's demographics, device, operating system, etc [2].
* **<u>Placement qualities (quality score [15])</u>**- some statistics that measure the quality of the impression. For instance, click-through rate (CTR) or conversation rate (CVR) then times the value of a click/conversation [17]. $Q_{i,a}$ represents the quality advertiser a would receive if the impression i is assigned to her [2].
* **<u>Value estimate (reservation value/private value [15])</u>**- for each bidder and seller $i$, there is some quantity $t_i$ which is $i$'s value estimate for the object, and which represents the maximum amount which $i$ is willing to pay for the object given his current information about it [11].
* **Bid** - each advertiser submits a bid $p$ to online bidding platform that represents their private valuation of the item. Usually, we assume that bids are symmetric (drawn from the same distribution) and independent conditional on user attributes disclosed [2]. 
* **Key Performance Index (KPI)** - the total performance of a campaign, e.g. the number of clicks, conversations, or total revenue [5, 17].
* **Opportunity cost** - the amount of money the publisher could have earned by selling impressions through guaranteed offline contracts [2, 7].
* **<u>Reserve price</u>** - the lowest bid that the seller is willing to accept for his item. Only bids that are higher than this price can get involved in the auction [15]. 
* **Pricing function** - a function $p^*$ that quotes a reserve price based on bid and potentially user attributes [2].
* **Revenue** - the amount earned. In our case, we care about the revenue for the publisher. 
* **Preference uncertainty** - the bidders' personal preferences might be unknown to other agents (for example, if the object is painting, the others might not know how much he really enjoys looking at the painting) [11].
* **Quality uncertainty** - the bidder  might have some special information about the intrinsic quality of the object (he might  know if the painting is an old master or a copy) [11].

## Workflow [2, 5]

![image-20210716103714145](C:\Users\zhouyewen_sx\AppData\Roaming\Typora\typora-user-images\image-20210716103714145.png)

1. On the supply side, each time a user visits a website, the publisher can choose to allocate the impression to guaranteed contract advertisers, or connect to Ad Exchange for RTB. 
2. On the demand side, DSP receives the requests, together with user information, and choose the bid level that best suits their strategy. 
3. On Ad Exchange, the bids are processed, the slot is attributed to the bidder who has proposed the highest bid and the price is paid depending on the type of the auction. 
4. If no bids won, the impression is rejected and the publisher can choose to either allocate it to the guaranteed contract or discard it. 

## General Assumptions

1. There is a single seller (monopolistic) with n buyers [11, 14].
2. The seller does not know how much the bidders are willing to pay [11].
3. The buyers don't know other's bids and will not cooperate (non-cooperative) [14], because of **preference uncertainty** and **quality uncertainty** [11].
4. The **value estimates** **(reservation value/private value)** distribution should be strictly increasing and differentiable [14, 15].
5. The distribution is usually assumed to be Uniform or Log-normal [12, 15, 20].
6. **In second-price auctions, buyers will bid exactly their value estimates** [14, 15]*.
7. The **bids** are drawn i.i.d. from **value estimates** distribution [11, 14].
8. The RTB is Vickrey Auction (second-price auction) [5, 11, 14].
9. The publisher has access to historical data [10]. 
10. The publisher has access to user attributes [8, 10].
11. The publisher and advertisers are risk-neutral [11, 14].

<img src="C:\Users\zhouyewen_sx\AppData\Roaming\Typora\typora-user-images\image-20210722110938589.png" alt="image-20210722110938589" style="zoom:67%;" />

<img src="C:\Users\zhouyewen_sx\Desktop\realtimebidding_literature_review\Utility-function-shapes-for-risk-averse-risk-neutral-and-risk-seeking-individuals.png" style="zoom:70%;" />

## Common Technologies

* Clustering (k-means clustering...)
* Regression (Multi-linear Regression, Ridge Regression, Logistic Regression...)
* Reinforcement Learning (DQN...)
* Deep Learning 
* SVM
* KNN [22]
* Mixed Models
* Pure Theories

## Core Findings

* The optimal reserve price does not depend on the number of buyers [14].
* In practice, the Uniform distribution works better than Log-normal distribution [12, 15, 20].
* In reality, reserve prices are substantially lower than the theoretically optimal ones [12].
* The more bidders, the lower the effect of setting an optimal reserve price [12]. 

## Variations

* There can be both an upstream and a downstream Ad Exchange [1].
* The publisher can choose to disclose user information or not [7].
* The publisher can have the option to set a soft floor price and a hard floor price [20].

## Our problem

1. Develop a structure for online bidding. 
2. Find a reserve price that can maximize the expected revenue.

## Define a good model

1. Easy to implement.
2. Robust (Accurate, or better, optimal).

## Two approaches

1. Set the reserve price directly based on pure theories (Optimal Auctions, variations...). 
2. Learn the reserve price through historical data (machine learning...). 

## Pure Theories

### Private value based algorithm

#### Set $v_*$

Assuming i.i.d. and buyers are risk-neutral with only **preference uncertainty**, the optimal reserve price can be set according to [11] as: 

$v_* = v_0 + \sum_{j \in N, j \neq 0} e_j(v_j) + \frac{1-F(v_*)}{f(v_*)}$ 

where $e_j(v_j)$ is revision effect function [11].

For pure **preference uncertainty** and **quality uncertainty**, the optimal reserve price is set according to [14, 15] as: 

$v_* = v_0 + \frac{1 - F(v_*)}{F'(v_*)}$

#### Set $F$

1. $F$ is often assumed to be Uniform distribution or Log-normal distribution [12, 15]. (If $X$ is log-normally distributed, then $Y = log(X)$ is normally distributed). 
2. The parameters of F are set based on historical data [15].
3. When $F$ is uniform distribution ($F(v) = v$ for $v \in [0, 1]$), and $v_0 = 0$, it is proved that $v_* = \frac{1}{2}$ [12, 14].

#### Set $v_0$

1. From guaranteed contract with a flat CPM [15].

2. From another ad network where the average revenue is known [15], in this case, we can first compute the reserve-price $\alpha(t)$ assuming private-value-free by averaging past payoff. 

   $\alpha(t) = \frac{1}{M} \sum_{i=t-M}^{t-1} r(i)$

   Then, plug in the previous equation and get $V_0$. 

### Private value free algorithm

#### FIXED and ZERO algorithms

* Set $\alpha(t) = \alpha$ for all time steps. 
* $\alpha$ is pre-chosen, can adopt negotiated contract price as the reserve price [15]. 
* Probably the most widely adopted algorithm in today's marketplaces [15]. 
* When $\alpha = 0$, it becomes the ZERO algorithm. 
* Performed well under certain circumstances [15].

#### AVERAGE and WeightedL algorithm

* $\alpha(t) = \frac{1}{M} \sum_{i=t-M}^{t-1} r(i)$
* $\alpha(t)  = \frac{1}{M}\sum_{i=t-M}^{t-1} w(i,t)r(i)$
* Recognizes the fluctuation of demand and supply in the market [15]. 

## Learning Algorithms

### Multiple Linear Regression with Kalman Filter (MLRKF) [8]

* Core idea:

  ![image-20210714102011833](C:\Users\zhouyewen_sx\AppData\Roaming\Typora\typora-user-images\image-20210714102011833.png)

* Pros:

  * **Performance**: produce highly accurate results with less training data and lower time cost (182). It also reduces over-fitting. 
  * **Dynamically update coefficient**: the MLRKFP model can dynamically optimize regression coefficients to produce more accurate results (183). 
  * **Implementation**: multiple-linear regression and Kalman filter is relatively easy to implement using existing tools such as sklearn and pyfilter. 
  * **Input**: only need to know $x_1, x_2, ... ,x_n$ as descriptive variables, coefficients can be learned by regression (184). 

* Cons:

  * **Complexity**: needs to have a very good understanding of multi-dimensional Kalman filter. 

### Bid-Price Policy with Dynamic Pricing $\mu^B$ [2]

* Core idea:

  ![image-20210709170737578](C:\Users\zhouyewen_sx\AppData\Roaming\Typora\typora-user-images\image-20210709170737578.png)

* Pros:
  * **Optimal**: asymptotically optimal (28) in the sense that it maximizes the revenue for the publisher.

* Cons: 
  * **Input**: need to know user attributes, placement qualities, pricing functions in advance. 
  * **Complexity**: have a very complicated tie-breaking rule (18). Have complicated math. Need to use advanced methods such as SAA (Sample Average Approximation) and SDM (sub-gradient descent method) in practice (24). 
  * **Assumptions**: have a lot of assumptions. For example, the bids are drawn i.i.d. from $F$.
  * **Hyper-parameter tuning**: have to tune the hyper-parameter $\gamma$. 

### Clustering and Regression [6]

* Core idea:

  ![image-20210714101852200](C:\Users\zhouyewen_sx\AppData\Roaming\Typora\typora-user-images\image-20210714101852200.png)

* Pros: 
  * **Complexity**: clustering and regression can be implemented relatively easy with existing tools such as sklearn. 
* Cons:
  * **Input**: clustering is done based on attributes for each auction (4). 
  * **Relevance**: the article mainly talks about how to predict the end-price from a set of auctions, whereas  in our problem, there is one auction and many bidders. 
  * **Ambiguity**: it is not clear how the bid selector works and how it nominates the cluster (6). It is also not clear (to me) how the autonomous agent based system is developed. 
  * **Optimality**: the optimal strategies mentioned in the article is optimal relative to other possible bidding strategies produced by trees. It is not rigorous whether it is the absolute optimal strategy. 

### OneShot [15]

* Core Idea:

  ![image-20210714102045939](C:\Users\zhouyewen_sx\AppData\Roaming\Typora\typora-user-images\image-20210714102045939.png)

* Pros:
  * **Complexity**: the algorithm is easy with only three lines of mathematical equations. 
  * **Performance**: out-performed than a variety of other algorithms (9). 
  * **Relevance**: it is an algorithm for real-time bidding (RTB), which closely relates to our problem. 
* Cons:
  * **Hyper-parameter tuning**: in practice, one needs to tune 4 parameters based on the training data. 
  * **Assumptions**: needs to assume the distribution of bids, which can lead to poor performance (9).  

### DC (difference of convex functions) Programming (Not DC Comics :smile:) [10]

* Core Idea (15):

  ![image-20210715152033504](C:\Users\zhouyewen_sx\AppData\Roaming\Typora\typora-user-images\image-20210715152033504.png)

* Pros:
  * **Assumptions**: did not assume bids are i.i.d. and are very close to reality (3).
  * **Rigorous**: present a very detailed proof of the algorithm. 
  * **Speed**: $O(mlogm)$ (2).
  * **Performance**: out-performs convex-surrogate (CVX), ridge regression (Reg), and algorithm that uses no features to set reserve prices (NF) (17). 
* Cons:
  * **Complexity**: cannot understand :smile:. 

### Dynamic Pricing model [3]

* Core Idea:

  ![image-20210715154928458](C:\Users\zhouyewen_sx\AppData\Roaming\Typora\typora-user-images\image-20210715154928458.png)

* Cons:

  * **Complexity**: cannot understand :smile:

### Linear Regression and  SGD (Stochastic Gradient Descent) [23]

* Core Idea:

  ![image-20210719112646661](C:\Users\zhouyewen_sx\AppData\Roaming\Typora\typora-user-images\image-20210719112646661.png)

  ![image-20210719112712407](C:\Users\zhouyewen_sx\AppData\Roaming\Typora\typora-user-images\image-20210719112712407.png)

* Pros:

  * **Complexity**: simple to implement. 
  * **Performance**: robust, statistically significant daily revenue lift of about 35% (533). 
  * **Complexity**: relatively easy to understand and implement. 

* Cons:

  * **Linearity**: the model uses linear features, which can return negative values (535).

## Comparison

| Algorithms                                            | Parameters                                              | Update between auctions | Yewen's advice      |
| ----------------------------------------------------- | ------------------------------------------------------- | ----------------------- | ------------------- |
| Bid-Price Policy with Dynamic Pricing $\mu^B$         | user attributes, placement qualities, pricing functions | No                      | Hard                |
| Clustering and Regression                             | $k$, Bid Selector, attributes for an auction            | No                      | Not closely related |
| Multiple Linear Regression with Kalman Filter (MLRKF) | data features (188)                                     | Yes                     | Most promising      |
| OneShot                                               | $\epsilon$, $\lambda_h$, $\lambda_e$, $\lambda_l$ (5)   | Yes                     | Most promising      |
| DC Programming (Not DC Comics :smile:)                | a lot                                                   | Yes                     | Hard                |
| Dynamic Pricing model                                 | a lot                                                   | Yes                     | Hard                |
| Linear Regression and  SGD                            | data features                                           | Yes                     | Most promising      |

## Limitations:

* i.i.d.: in practice, bids are usually correlated. 
* second-price auction: we are doing first-price auction. 
* RTB: in our setting, there is lag. 

## Possible Solution

![](C:\Users\zhouyewen_sx\Desktop\realtimebidding_literature_review\solution.png)

## Conclusion

* for simplest model - assumptions + pure theories (FIXED, AVERAGE, WEIGHTEDL...)
* for intermediate model - assumptions +  learning coefficients (MLRKF, OneShot, Linear Regression + SGD...)
* for more advanced model - relax assumptions (DC Programming, Multi-armed Bandit...)

## Detailed Review

### Optimal Auctions

Goals:

1. what form does the competition among the few buyers take under the most common auction procedures? How is the sale price determined?
2. by what means can the seller best exploit his monopoly position? For example, would it be more profitable for the seller to require payment not only by the highest bidder, but also by those with lower ranked bids?

Assumptions:

- A **single seller** with reservation value v, faces **n potential buyers**, where buyer i holds reservation value v,, i= 1,. ..,n (381). 
- The reservation values of the parties are **independent and identically distributed**, drawn from the **common** distribution F (381). 
- There is a common equilibrium bidding strategy in which each buyer makes a bid b, which is a strictly **increasing function** of his reservation value u (383). 
- A **single indivisible good** is to be sold to the highest bidder (389). 
- The greater a bidder's reservation value the more he will bid for the good (389).
- Buyer roles are symmetrical (i.e., buyer values are drawn from a common distribution) and each buyer is **risk neutral** (389).
- Buyer values are independent (389).
- Each buyer is informed of his own reservation price and, more important, that his price conveys no information about any other buyer's value (390).

Core ideas:

- The high and second bid auctions with reserve price  $b_0 = v*$ are both optimal in the family of auctions. 
- In asymmetrical model (where the reservation prices of the buyers are no longer drawn from a **common** distribution F), The assignment of the good and the appropriate buyer payment will depend not only on the list of offers, but also on the **identities** of the buyers who submit the bids. In short, an optimal auction under asymmetric conditions violates the principle of buyer anonymity (389).
- Under the assumption of risk neutrality, the seller can do no better than to employ the second bid auction with an optimal reserve price. In this auction, buyers will have no difficulty formulating an optimal bidding strategy. Nor need they know the form of the distribution function F(u). Against any distribution of opponents' bids, each buyer's dominant strategy is to **bid his reservation value** (389).
- The optimal reserve price does not depend on the number of buyers (390). 
- Assuming that the reservation values (buyers’ valuation of the good) follow a uniform distribution and that the seller’s valuation of the object $v_0 = 0$, then the optimal price is 1/2.(386). 

Limitations:

- can’t deal with multiple goods (389).
- can’t deal with a single divisible good (389).  
- The derivation of the class of optimal auctions relied explicitly on the existence of a common equilibrium bidding strategy. Without this, these propositions no longer hold (389).

### Optimal Auction Design 

Goal:

- Construct optimal auctions for a wide class of sellers’ auction design problems and prove that no other auction mechanism can give higher expected utility to the user (58). 

Assumptions: 

* one seller, a single object to sell, n bidders (59). 
* for each bidder, there is some quantity $t_i$ which is i's **value estimate** for the object (59).
* the seller's uncertainty about the value estimate of bidder i can  be described by a continuous probability distribution over a finite interval (59).
* the value estimates of the n bidders are stochastically independent random variables (59). 
* the seller has no private  information about the object, so that $t_0$ is known to all the bidders (59). 

Core ideas: 

- ***preference uncertainty vs. quality uncertainty***: if there are quality uncertainties, then bidder i might tend to revise his valuation of the object after learning about other bidders' value estimates. That is, if i learned that $t_j$ was very low, suggesting that j had received discouraging information about the quality of the object, then i might honestly revise downward his assessment of how much he should be willing to pay for the object (60). 

- ***with quality uncertainty***: the optimal reserve price can be set as: 

  ![image-20210709162517403](C:\Users\zhouyewen_sx\AppData\Roaming\Typora\typora-user-images\image-20210709162517403.png)

- ***optimal price in the general case*** (70): 

  ![image-20210709162648627](C:\Users\zhouyewen_sx\AppData\Roaming\Typora\typora-user-images\image-20210709162648627.png)

Relationships with Optimal Auctions 

- **Optimal Auctions** assumes **pure preference uncertainty**, while **Optimal Auction Design** also adds in **quality uncertainty**, which gives rise to the **revision effect functions** $e_i$. Without revision effect functions, two are essentially the same.
- **Optimal Auctions** focuses more on determining the reserve price, while **Optimal Auction Design** focuses on mathematical proof of designing optimal auction mechanisms. 

### Yield Optimization of Display Advertising with Ad Exchange

Goal:

* Formalize this combined optimization problem as a multi-objective stochastic control problem and derive an efficient policy for online ad allocation in settings with general joint distribution over placement quality and exchange prices (1). 

Core ideas: 

* **trade-off**: in presence of Ad Exchanges, publishers face the multi-objective problem of maximizing the overall placement quality of the impressions assigned to the reservations together with the total revenue obtained from AdX, while complying with the contractual obligations (2). 

* **workflow**: 

  ![image-20210709165943265](C:\Users\zhouyewen_sx\AppData\Roaming\Typora\typora-user-images\image-20210709165943265.png)

* **objective**: yield = revenue(AdX) + γ · quality(advertisers).

* **user information**:  in practice, bids from the exchange may be correlated with the user information disclosed, and publishers maintain different estimates of the bids’ distribution as a function of the attributes. We assume that conditional on the user information u ∈ U bids are independent across impressions, and identically distributed according to a c.d.f. F(·;u). Hence, when the publisher discloses some information u the impression is accepted with probability $1 − F(p;u) = \bar{F}(p;u)$ (9).

* **opportunity cost**: suppose the publisher has computed an opportunity cost c for selling this inventory in the exchange; that is, the publisher stands to gain c if the impression is given to a reservation advertiser (10).

* **objective function**: $R(c;u) = \max_{p \geq 0} \bar{F}(p;u)p + F(p;u)c$ 

* **stochastic algorithm**: 

  ![image-20210709170737578](C:\Users\zhouyewen_sx\AppData\Roaming\Typora\typora-user-images\image-20210709170737578.png)

* **tie-breaking**: 

  ![image-20210709170948929](C:\Users\zhouyewen_sx\AppData\Roaming\Typora\typora-user-images\image-20210709170948929.png)

* **sample-average approximation (SAA)**: approximating the underlying stochastic program via sampling, and then solving the approximate problem via a Sub-gradient Descent Method (SDM) (24).

Results: 

* Interestingly, starting from the baseline case that disregards AdX (γ = ∞), we observe that the revenue from AdX can be substantially increased by sacrificing a small fraction of the overall quality of the impressions assigned (27).
* Conversely, starting from the case that disregards the advertiser’s quality (γ = 0), the publisher can raise placement quality by a large amount at the expense of a small decrease in AdX’s revenue.  
* the Greedy Policy under-performs in the given instances with losses in yield of up to 70% (28).
* The Static Price Policy tends to under perform when the trade-off parameter γ is close zero, that is, when the publisher strives to maximize the revenue extracted from AdX. If the publisher fails to dynamically adjust the auctions’ reserve price to take into account the opportunity cost of the impression, she can incur losses in yield of up 69% (28). 
*  When the trade-off parameter γ is large, the exchange’s revenue contribution to the yield is negligible, and the Static Price Policy is nearly optimal.

Limitations: 

* learning in the case of unknown distributions. 
* stochastic approximation of the deterministic problem. 

### Reserve Prices in Internet Advertising Auctions: A Field Experiment∗ 

Goal: 

* We present the results of a large field experiment on setting reserve prices in auctions for online advertisements, guided by the theory of optimal auction design suitably adapted to the sponsored search setting. Consistent with the theory, revenues increased substantially after the new reserve prices were introduced (1).

Core ideas: 

*  For the case with symmetric bidders, the answer is particularly elegant: the optimal mechanism can be implemented by a second-price auction with an appropriately chosen reserve price (2). 
*  The revenues in the treatment group have increased substantially relative to the control group, showing that reserve prices in auctions can play an important role and that theory provides a useful guide for setting them (2).
*  Remarkably, the optimal reserve price depends neither on the number of bidders nor on the number of available positions.  The impact of reserve prices on revenues, however, depends critically on these parameters (6). 
*  In fact, in single-object auctions, reserve prices only play an important role if the number of bidders is small (6). 
*  In order to estimate optimal reserve prices for the experiment, it was assumed that bidders’ values are drawn from log-normal distributions (7). 

Results: 

*  Even with six bidders, reserve prices remain very important: the optimal reserve price improves the revenues by 45% (7).
*  Similar to the example with the uniform distribution of values, the impact of optimal reserve prices on revenues in the GSP auction is substantial: with six bidders, setting the reserve price at zero instead of the optimal level results in the loss of 25% of revenues; and even with ten bidders, the loss is noticeable: 9% (7).
*  The results of the experiment described in this paper show that setting appropriate reserve prices can lead to substantial increases in auction revenues (19).
*  These results also show (to the best of our knowledge, for the first time) that the theory of optimal auction design is directly applicable in practice (19).

### Pricing Analysis in Online Auctions using Clustering and Regression Tree Approach

Goal:

* Show the improvements in the **end price prediction** using clustering and regression tree approach (1). 

Core Ideas:

* Forecast bid amounts of buyers using historical data (2).
* Use a price forecasting agent (PFA) to forecast the end-price of an online auction for autonomous agent based system (2).
* The input auctions are clustered into groups of similar auctions based on their characteristics using k-means algorithm (2).
* Features are predefined attributes from the vast feature space of online auctions (5). 
* K is estimated using ANOVA (2).
* Bid selector nominates the cluster after clustering (2).
* Finally, regression trees are employed to forecast the end-price and to design the bidding strategies (2). 
* Optimal bidding strategies are designed by employing regression trees on each cluster and evaluating the model by test-sample cross validation approach (10).
* Forecasting is seen as a time-series problem and is solved using moving averages and  exponential smoothing (3). 
* Authors have used sequence mining to improve the decision mechanism (3). 

Results: 

* The improvement in root mean square error after clustering for each of the five clusters are 16.43%, 29.47%, 20.76%, 31.17% and 64.91% respectively. This indicated that the proposed price forecasting agent can improve the accuracy of the forecasted price for online auctions (8).

### Multiple Linear Regression with Kalman Filter for Predicting End Prices of Online  Auctions

Goal:

* Show that a hybrid algorithm with multiple linear regression and Kalman filter can produce highly accurate results with less training data and lower time cost. 

Core ideas: 

* Multiple linear regression:  y is the end price of an online auction i. $x_1, x_2, ..., x_i$are the available explanatory variables, and they  may be StartingBid, HitCount, AuctionAvgHitCount, and  SellerItemAvg (184).
* Kalman filter is used to optimize weight coefficients,  which is a parameter optimization problem (185).
* Let x denote the n-dimensional weight vector of a  multiple linear regression algorithm. We assume that x follows Gaussian distribution with mean $x_b$ and covariance $P_b$ .
* More details are on page (186).

Results: 

* MLRKF has the lowest training time compared to random forest regressor, SVM, RNN, Lasso (188).
* Table IV shows that the proposed model  has the smallest MAE, RMSE, and MAPE values compared  to MLRP, MLRRP, Lasso, Random Forest, SVM and RNN models (188). 
* MLRKF prediction is better fitted for true end prices with dataset1 (189).

### An Empirical Study of Reserve Price Optimization in Real-Time Bidding

Goal: 

* Report the first empirical study and live test of the reserve price optimization problem in the context of Real-Time Bidding (RTB) display advertising from an operational environment and show that the proposed game theory based OneShot algorithm performed the best. 

Core Ideas: 

* A reserve price defines the minimum that a publisher would accept from bidders. It reflects the publisher’s private valuation of the inventory: bids will be discarded if they are below the reserve price (1). 
* One iteration usually finishes in less than 100ms to achieve users' satisfactory (2). 
* In practice, there are drawbacks of the optimal auction theory mostly due to the difficulty of learning bidders’ private values, e.g., $F(x)$. Firstly, a bidder could have a complex private value distribution for impressions.

## References 

1. Alcobendas Lisbona, Miguel Angel, et al. “Optimal Reserve Prices in Upstream Auctions.” *Proceedings of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining*, 2016, doi:10.1145/2939672.2939877. 
2. Balseiro, Santiago R., et al. “Yield Optimization of Display Advertising with Ad Exchange.” *Management Science*, vol. 60, no. 12, 2014, pp. 2886–2907., doi:10.1287/mnsc.2014.2017. 
3. Chen, Bowei, et al. “A Dynamic Pricing Model for Unifying Programmatic Guarantee and Real-Time Bidding in Display Advertising.” *Proceedings of 20th ACM SIGKDD Conference on Knowledge Discovery and Data Mining - ADKDD'14*, 2014, doi:10.1145/2648584.2648585. 
4. Davis, Andrew M., et al. “Do Auctioneers Pick Optimal Reserve Prices?” *Management Science*, vol. 57, no. 1, 2011, pp. 177–192., doi:10.1287/mnsc.1100.1258. 
5. Fernandez-Tapia, Joaquin, et al. “Optimal Real-Time Bidding Strategies.” *Applied Mathematics Research EXpress*, 2016, doi:10.1093/amrx/abw007. 
6. Kaur, Preetinder, et al. “Pricing Analysis in Online Auctions Using Clustering and Regression Tree Approach.” *Lecture Notes in Computer Science*, 2012, pp. 248–257., doi:10.1007/978-3-642-27609-5_16. 
7. Li, Juanjuan, et al. “Information Disclosure in Real-Time Bidding Advertising Markets.” *Proceedings of 2014 IEEE International Conference on Service Operations and Logistics, and Informatics*, 2014, doi:10.1109/soli.2014.6960708. 
8. Li, Xiaohui, et al. “Multiple Linear Regression with Kalman Filter for Predicting End Prices of Online Auctions.” *2020 IEEE Intl Conf on Dependable, Autonomic and Secure Computing, Intl Conf on Pervasive Intelligence and Computing, Intl Conf on Cloud and Big Data Computing, Intl Conf on Cyber Science and Technology Congress (DASC/PiCom/CBDCom/CyberSciTech)*, 2020, doi:10.1109/dasc-picom-cbdcom-cyberscitech49142.2020.00042. 
9. McAfee, R. Preston, and Philip J. Reny. “Correlated Information and Mecanism Design.” *Econometrica*, vol. 60, no. 2, 1992, p. 395., doi:10.2307/2951601. 
10. Mohri, Mehryar, and Andres Munoz Medina. “Learning Algorithms for Second-Price Auctions with Reserve.” *Journal of Machine Learning Research*, vol. 17, 16 Apr. 2016, pp. 1–25. 
11. Myerson, Roger B. “Optimal Auction Design.” *Mathematics of Operations Research*, vol. 6, no. 1, Feb. 1981, pp. 58–73. 
12. Ostrovsky, Michael, and Michael Schwarz. “Reserve Prices in Internet Advertising Auctions: A Field Experiment.” *SSRN Electronic Journal*, 2009, doi:10.2139/ssrn.1573947. 
13. Preston, McAfee R., and Vincent Daniel. “Updating the Reserve Price in Common Value Auctions.” *Discussion Paper, Northwestern University, Kellogg School of Management, Center for Mathematical Studies in Economics and Management Science, Evanston, IL*, ser. 977, 1992. *977*. 
14. Riley, John G., and William F. Samuelson. “Optimal Auctions.” *The American Economic Review*, vol. 71, ser. 3, June 1981, pp. 381–392. *3*, www.cs.princeton.edu/courses/archive/spring09/cos444/papers/riley_samuelson81.pdf. 
15. Yuan, Shuai, et al. “An Empirical Study of Reserve Price Optimisation in Real-Time Bidding.” *Proceedings of the 20th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining*, 2014, doi:10.1145/2623330.2623357. 
16. Zhang, Weinan, et al. “Feedback Control of Real-Time Display Advertising.” *Proceedings of the Ninth ACM International Conference on Web Search and Data Mining*, 2016, doi:10.1145/2835776.2835843. 
17. Zhang, Weinan, et al. “Optimal Real-Time Bidding for Display Advertising.” *Proceedings of the 20th ACM SIGKDD International Conference on Knowledge Discovery and Data Mining*, 2014, doi:10.1145/2623330.2623633. 
18. X. Li, L. Liu, L. Wu, Z. Zhang, “ Predicting the final prices of online  auction items,”Expert Systems with Applications,vol.32,no.3,pp.542- 550, 2006.
19. C.H. Wu, M.Y. Yeh, M.S. Chen, “Predicting winning price in real time bidding with censored data,” ACM SIGKDD International  Conference on Knowledge Discovery and Data Mining, ACM, pp.  1305–1314, 2015.
20. Yuan, Shuai, et al. “Real-Time Bidding for Online Advertising.” *Proceedings of the Seventh International Workshop on Data Mining for Online Advertising - ADKDD '13*, 2013, doi:10.1145/2501040.2501980. 
21. M.R. Khadge, M.V. Kulkarni, “Machine Learning Approach For  Predicting End Price Of Online Auction,” in Proceedings of 2016 International Confeerence on Inventive Computation  Technologies(ICICT), Coimbatore, India, Aug.2016,pp. 748–752. 
22. S.Zhang, W. Jank , G. Shmueli, “Real-time forecasting of online auctions via functional -nearest neighbors,” International Journal of  Forecasting,vol.26,no.4, pp.666-683, 2010.
23. Austin, Daniel, et al. “Reserve Price Optimization at Scale.” *2016 IEEE International Conference on Data Science and Advanced Analytics (DSAA)*, 2016, doi:10.1109/dsaa.2016.32. 

