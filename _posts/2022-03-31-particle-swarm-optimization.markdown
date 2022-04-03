---
layout: post
title:  "Particle Swarm Optimization"
date:   2022-03-31 23:31:35 -0500
categories: Project
author: "Chris Summers"
permalink: "ParticleSwarmOptimization"
---
This post is about a single objective particle swarm optimization algorithm. [Particle Swarm Optimization][Particle-Swarm-Optimization] is a nature-inspired heuristic optimization algorithm. 
It allows one to find the global minimum of a function subject to any constraints without calculating any gradients. 

Single objective optimization consists of finding the global miniumum of a function, $ f(x, y) $, over a range of bounds for x and y, and subject to some constraint. 
For example, consider the function:

$$ f(x, y) = sin(y)e^{\((1-cos(x))^{2}} + cos(x)e^{\((1-sin(x))^{2}} + (x - y)^{2} $$

![Me](/assets/img/pso_surface.png){: .mx-auto.d-block :}

The goal of Single Objective Optimization is to find the global minium of this function, which is $$ f(-3.13, -1.58) = -106.76 $$. However, this function has multiple local minumums, which can make it difficult to solve. 
A resource for psuedo code for this algorithm can be found [here][pseudo-code].

Particle swarm optimization (PSO) is a stochastic search method that finds the global minimum of a function by taking an a number of guesses and moving them around in the search space. 
Each particle is aware of it's own location and the value of it's function value. Then, 




### Example Equation

$$
\begin{align}
  \tag{1.1}
  V_{sphere} = \frac{4}{3}\pi r^3
\end{align}
$$

### Example code snippets

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[Particle-Swarm-Optimization]: https://en.wikipedia.org/wiki/Particle_swarm_optimization
[pseudo-code]: https://mae.ufl.edu/haftka/stropt/Lectures/PSO_introduction.pdf
[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
