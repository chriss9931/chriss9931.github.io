---
layout: post
title:  "Method of Characteristics for Design of a Gradual Expansion Supersonic Wind Tunnel Nozzle"
date:   2021-11-15 23:31:35 -0500
categories: Project
author: "Chris Summers"
permalink: "MoCNozzle"
useMath: true
---
The design of a nozzle contour for a supersonic nozzle is a difficult problem, and this article presents a simplified solution for two dimensional supersonic nozzle design. There are two main types of supersonic nozzles.
First is a minimum length nozzle, designed for rocket engines. These nozzles achieve isentropic expansion for a target exit mach number in the minimum possible length, therefore minimizing mass.
Second is a gradual expansion nozzle, designed for use in supersonic wind tunnels. These nozzles also achieve isentropic expansion for a target exit mach number, but are longer and achieve a more desireable flow in the wind tunnel test section. 

There are many resources for minimum length rocket nozzle design. Below is a list of resources for reference. 
- [Minimum Length Nozzles][Paper-1]  
- [Wind Tunnel Nozzle Design][Paper-2] 
- [Ansys Tutorial for Method of Characteristics][Video-1]
- [Tutorial for solving by hand][Video-2]
- [MATLAB video tutorial][Video-3]

The method of characteristics takes advantage of a concept called characteristic lines. 
In two-dimensional, steady, inviscid, and supersonic flow, lines exist within the flow field along which the derivatives of the flow field variables have discontinuities and the values are indeterminate. 
The governing equation of this flow can be obtained by starting with the Navier-Stokes Equations, simplifying, and substituting in the velocity potential to get the following equation.

<img src="https://latex.codecogs.com/svg.image?[1-\frac{1}{a^{2}}(\frac{\partial&space;\phi&space;}{\partial&space;x})^{2}]\frac{\partial&space;^{2}\phi}{\partial&space;x^{2}}&space;&plus;&space;[1-\frac{1}{a^{2}}(\frac{\partial&space;\phi&space;}{\partial&space;y})^{2}]\frac{\partial&space;^{2}\phi}{\partial&space;y^{2}}&space;-&space;\frac{2}{a^{2}}\frac{\partial&space;\phi}{\partial&space;x}\frac{\partial&space;\phi}{\partial&space;y}\frac{\partial^{2}&space;\phi}{\partial&space;x\partial&space;y}=0" title="https://latex.codecogs.com/svg.image?[1-\frac{1}{a^{2}}(\frac{\partial \phi }{\partial x})^{2}]\frac{\partial ^{2}\phi}{\partial x^{2}} + [1-\frac{1}{a^{2}}(\frac{\partial \phi }{\partial y})^{2}]\frac{\partial ^{2}\phi}{\partial y^{2}} - \frac{2}{a^{2}}\frac{\partial \phi}{\partial x}\frac{\partial \phi}{\partial y}\frac{\partial^{2} \phi}{\partial x\partial y}=0" />

`YEAR-MONTH-DAY-title.MARKUP`

Where `YEAR` is a four-digit number, `MONTH` and `DAY` are both two-digit numbers, and `MARKUP` is the file extension representing the format used in the file. After that, include the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[Paper-1]: https://www.ijert.org/research/design-of-a-supersonic-nozzle-using-method-of-characteristics-IJERTV2IS110026.pdf
[Paper-2]: https://www.researchgate.net/publication/273460548_Design_of_supersonic_wind_tunnel_using_method_of_characteristics
[Video-1]: https://www.youtube.com/watch?v=k4RNsTLpbng
[Video-2]: https://www.youtube.com/watch?v=kfq-O-lho08
[Video-3]: https://youtu.be/iRuG_Zbz2Ig
[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/
