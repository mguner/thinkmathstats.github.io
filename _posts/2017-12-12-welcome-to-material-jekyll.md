---
layout: post
title:  "Variance - Bias Tradeoff"
date:   2018-10-20 22:00:00 +0000
image: /assets/images/twoscreen.jpg
---
In this blog, we will discuss the following equation which is famaously known as bias-variance trade-off.[Introduction to Statistical Learning, p34][ISL]

$$\begin{equation}
E \left(y_{0} - \hat{f}(x_{0})\right)^2 = \mbox{Var}(\hat{f}(x_{0})) + \lbrack \mbox{Bias}(\hat{f}(x_{0}))\rbrack^2 + \mbox{Var}(\epsilon)\label{a}\tag{1}
\end{equation}
$$

The left hand side of this equation is known as *the expected test* mean squared error, that is the average test *MSE* that we would obtain if we repeatedly estimate $$f$$ using a large number of training sets, and tested each at $$x_0$$.
$$\begin{equation}
x = -b \pm \sqrt{b^2-4ac} \over 2a
\end{equation}$$

Jekyll also offers powerful support for code snippets:
Deneme deneme 

$$\begin{aligned}
\nabla \times \vec{\mathbf{B}} -\, \frac1c\, \frac{\partial\vec{\mathbf{E}}}{\partial t} & = \frac{4\pi}{c}\vec{\mathbf{j}} \\   \nabla \cdot \vec{\mathbf{E}} & = 4 \pi \rho \\
\nabla \times \vec{\mathbf{E}}\, +\, \frac1c\, \frac{\partial\vec{\mathbf{B}}}{\partial t} & = \vec{\mathbf{0}} \\
\nabla \cdot \vec{\mathbf{B}} & = 0 
\end{aligned}
$$

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
[ISL]: https://www-bcf.usc.edu/~gareth/ISL/

You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
