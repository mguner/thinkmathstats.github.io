---
layout: post
title:  "Variance - Bias Tradeoff"
date:   2018-10-20 22:00:00 +0000
image: /assets/images/twoscreen.jpg

---
In this blog, we will discuss the following equation which is famously known as bias-variance trade-off. 


$$\begin{equation}
E \left(y_{0} - \hat{f}(x_{0})\right)^2 = \mbox{Var}(\hat{f}(x_{0})) + \lbrack \mbox{Bias}(\hat{f}(x_{0}))\rbrack^2 + \mbox{Var}(\epsilon)\label{a}\tag{1}
\end{equation}
$$

where $$\hat{f}$$ denotes the estimate for $$f$$ which assumed to represent the true relationship between the variables $$c$$ and $$y$$. The other term $$\epsilon$$ stands for the error (noise) introduced to our data during the collection/recording of our data. Here we will follow the book's notation and use the notation $$\lbrace (x_0,y_0), \cdots, (x_n, y_n) \rbrace$$ to represent the dataset and write $$f(\mathbf{X}) = \mathbf{Y} + \mathcal{E}$$ where $$\mathbf{X} = \lbrace x_0, \cdots, x_{n} \rbrace$$, $$\mathbf{Y} = \lbrace y_0, \cdots, y_{n}\rbrace$$ and $$\mathcal{E} = \lbrace \epsilon_{0}, \cdots, \epsilon_{n} \rbrace $$.

Here let us also note that on the left hand side this equation we have *the expected test* __mean squared error__, that is the average test *MSE* that we would obtain if we repeatedly estimate $$f$$ using a large number of training sets, and tested each at $$x_0$$. So this equation tells us that in order to minimize the test error we should find a model with low *variance* and low *bias*. I hope that the derivation I will give in a minute will help to understand these terms more clearly but for more details you can find all these in [Introduction to Statistical Learning, p34][ISL].

The first crucial observation to derive $$\ref{a}$$ is that we think of $$\left( y_0 - \hat{f}(x_0) \right)^2$$ as a random variable over the space of samples drawn from the bigger population. That means, as you randomly choose datasets from the population our model will try to fit this new datasets and produce different predictions for $$x_0$$. So on the left hand side we calculate the expected value of these errors as you come up with different predictions $$\hat{f}(x_0)$$ as datasets are changing. 



$$\begin{equation}
E \left(y_{0} - \hat{f}(x_{0})\right)^2 = E \left(f(x_{0})-\hat{f}(x_{0}) - \epsilon\right)^2 = E\left((f(x_{0})-\hat{f}(x_{0}))^2  + \epsilon^2 -2\epsilon (f(x_{0})-\hat{f}(x_{0})\right).\label{b}\tag{2}
\end{equation}
$$

Here we just write $$ y_0  = f(x_0)+\epsilon$$ and expand the square. Using the fact that [$$E(X+Y) = E(X)+E(Y)$$](https://en.wikipedia.org/wiki/Expected_value):

$$
E \left(f(x_{0})-\hat{f}(x_{0}) - \epsilon\right)^2  = E \left(f(x_{0})-\hat{f}(x_{0}\right) ^2 + E\left(\epsilon\right)^2 - 2E\left(\epsilon (f(x_{0})-\hat{f}(x_{0})\right) \label{c}\tag{3}
$$

Here we got the first term that showed up in the original equation ($$\ref{a}$$). That is $$E(\epsilon)^2 = \mbox{Var}(\epsilon)$$. Here we will also note that the last term in equation ($$\ref{c}$$) is zero. To see this more clearly, we should note that $$\epsilon$$ and $$ (f(x_{0})-\hat{f}(x_{0})$$ are independent random variables and if $$X$$ and $$Y$$ are independent random variables then we have $$E(XY)= E(X)E(Y)$$. Therefore since we assume that $$\epsilon$$ is mean zero random variable we got what we wanted. 

$$ 2E\left({\large \epsilon} (f(x_{0})-\hat{f}(x_{0})\right) = 2 E \left( {\large \epsilon} \right) E\left(f(x_{0})-\hat{f}(x_{0})\right) = 0$$

So we are left with the first term in equation ($$\ref{c}$$). To handle this term, we will add and subract $$E(\hat{f}(x_0))$$ to this term.


$$
E \left(f(x_{0})-\hat{f}(x_{0}\right) ^2  = E\left(f(x_{0}) - \hat{f}(x_{0})+ E(\hat{f}(x_{0})) -E(\hat{f}(x_{0})\right)^2 \label{d}\tag{4}
$$

Let's expand the right hand side of this equation again:

$$
E\left( E(\hat{f} (x_{0} )) - \hat{f}(x_{0}) \right)^2 + E\lbrack f(x_{0}) - E(\hat{f}(x_{0})\rbrack^2 - 2E[(E[\hat{f}(x_{0})]-\hat{f}(x_{0}))(f(x_{0}) - E[\hat{f}(x_{0})])] \label{e}\tag{5}
$$

Here the first term will give us 


[ISL]: https://www-bcf.usc.edu/~gareth/ISL/

