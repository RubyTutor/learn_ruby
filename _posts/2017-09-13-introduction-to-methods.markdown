---
layout: post
title:  "Introduction to Methods"
date:   2017-09-13 22:33:07 +0200
categories: ruby methods introduction
---

Methods in Ruby always, implicitly or explicitly, return values.


# A method that implicitly returns nil

{% highlight ruby %}
def output_value(value)
  puts value
end
{% endhighlight %}

{% highlight ruby %}
output_value(2)
{% endhighlight %}

# A method that explicitly returns a value

{% highlight ruby %}
def calculate_value(x,y)
  x + y
end
{% endhighlight %}

{% highlight ruby %}
calculate_value(1,1)
{% endhighlight %}

# References

* [Method Calls][method-calls]

[method-calls]: https://en.wikibooks.org/wiki/Ruby_Programming/Syntax/Method_Calls
