---
layout: post
title:  "Map vs Each"
date:   2017-09-14 23:43:07 +0200
categories: ruby hashes
---

{% highlight ruby %}
toppings = %w(pepperoni mushroom bacon pineapple)

{% highlight ruby %}
def pizza(toppings)
  toppings.each do |topping|
    puts "I love #{topping} pizza!"
  end
end
{% endhighlight %}

{% highlight ruby %}
pizza(toppings)
{% endhighlight %}


# Explicitly tell to change the return value
# Prvo definisemo prazan array my_statements koji pozovemo nakon izvrsenja
# te ispisemo vrijednost niza

{% highlight ruby %}
def pizza2(toppings)
  my_statements = []
  toppings.each do |topping|
    my_statements << "I love #{topping} pizza!"
  end
  my_statements
end
{% endhighlight %}

{% highlight ruby %}
pizza2(toppings)
{% endhighlight %}

# MAP

{% highlight ruby %}
def pizza3(toppings)
  toppings.map do |topping|
    puts "Ich liebe #{topping} pizza!"
  end
end
{% endhighlight %}

{% highlight ruby %}
pizza3(toppings)
{% endhighlight %}

# puts returns nil, we will not use puts in next example

{% highlight ruby %}
def pizza4(toppings)
  toppings.map do |topping|
   "Ich liebe #{topping} pizza!"
 end
end
{% endhighlight %}

# or alternative wat to write blocks

{% highlight ruby %}
def pizza5(toppings)
  toppings.map { |topping| "Ich liebe #{topping} pizza!" }
end
{% endhighlight %}


# References

* [Map vs Each][map-vs-each]


[map-vs-each]: https://learn.onemonth.com/ruby-tutorial-map-vs-each-a692b63e1850
