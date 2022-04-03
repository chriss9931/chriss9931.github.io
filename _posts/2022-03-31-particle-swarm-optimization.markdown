---
layout: post
title:  "Particle Swarm Optimization"
date:   2022-03-31 23:31:35 -0500
categories: Project
author: "Chris Summers"
permalink: "ParticleSwarmOptimization"
useMath: true
---
<script type="text/javascript" async
  src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-MML-AM_CHTML">
</script>
<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

This post is about a single objective particle swarm optimization algorithm. 
[Particle Swarm Optimization][Particle-Swarm-Optimization] is a nature-inspired heuristic optimization algorithm. 
A resource for psuedo-code for this algorithm can be found [here][pseudo-code].
This is one of several types of heuristic optimization algorithms that allow one to find the global minimum of a function subject to any constraints without calculating any gradients. 

Single objective optimization consists of finding the global miniumum of a function, $$ f(x, y) $$, over a range of bounds for x and y, and subject to some constraint. 
For example, consider the function:

$$ f(x, y) = sin(y)e^{(1-cos(x))^{2}} + cos(x)e^{(1-sin(x))^{2}} + (x - y)^{2} $$

![Me](/assets/img/pso_surface.png){: .mx-auto.d-block :}

The goal of Single Objective Optimization is to find the global minimum of this function, which is $$ f(-3.13, -1.58) = -106.76 $$.
However, this function has multiple local minumums, which can make it difficult to solve. 
There are two main classes of optimization algorithms:
- Gradient-based Algorithms:  Calculates the local gradients of the function and moves towards the negative values
- Heuristic Algorithms: Designed to solve problems quickly, often attempting to imitate nature.

Particle swarm optimization (PSO) is an heuristic algorithm designed to simulate social behavior, or swarm intelligence.
In order to find the global minimum, a swarm of particles is created and placed in the search space. 
Then, each particle is given velocity its p, moving it towards its personal best position and the global best position.

Each iteration, every particle in the swarm moves while updting the global and personal best positions in search of the global minimum.
If a particle moves to a location outside of the search space, then the particles position is set to the boundary of the space.
If there are constraints on the problem, then any particle violating those constraints are considered as inelegible to become one of the 'best' positions. 
The stopping condition is defined when either the global best position does not change for a number of iterations, or the maximum number of iterations is exceeded. 

### Particles

In order for the algorithm to work, particles need to be able keep track of their own data, send data, recieve data, and move. For this, we will make a particle class.
{% highlight python linenos %}
class Particle():
    def __init__(self, func, constraintfunc, position, LB, UB):
        self.func = func
        self.constraintfunc = constraintfunc
        self.x_current = position
        self.v_current = np.zeros_like(position)
        self.f_current, self.eligible = self.evaluate(position)
        self.fp_best = self.f_current
        self.xp_best = np.zeros_like(position)
        self.LB = LB
        self.UB = UB
{% endhighlight %}

When initializing a particle, two functions are passed. The first is the function to be minimized, taking in an array of input variables and returns the value. 
The second is a constraint function that takes in the array of input variables and the function value returning a boolean that states whether or not the position is feasible.
An initial position is also given, as well as the upper and lower bounds on the input variables. The initial position is then evaluated, and the intial velocity is set to zero.
The personal best position and value are set as the intial. 

The evaluation function takes a position, passes it through the function. Then takes the position and function value and passes it through the constraint function.

In order to 

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
