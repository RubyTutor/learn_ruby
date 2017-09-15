---
layout: post
title:  "Sorting hashes in Ruby"
date:   2017-09-15 10:00:07 +0200
categories: ruby hashes
---

We will create a Hash object named people containing names as the keys and ages
as the values.

{% highlight ruby %}
people = {
  :fred => 23,
  :joan => 18,
  :pete => 54
}
{% endhighlight %}

People object is a Hash, let's check that.

{% highlight ruby %}
puts people.class
{% endhighlight %}

or with

{% highlight ruby %}
people.is_a?Hash
{% endhighlight %}


# Sort by name

{% highlight ruby %}
people.sort
{% endhighlight %}

{% highlight ruby %}
puts "Sort by name using only sort method " + people.sort.inspect
{% endhighlight %}

sort method will convert our Hash to Array, we can check that with

{% highlight ruby %}
people.sort.class
{% endhighlight %}

to convert it back to Hash we use to_h method

{% highlight ruby %}
people.sort.to_h
{% endhighlight %}


# How to sort by ages?

### Using sort method

{% highlight ruby %}
people.values.sort
{% endhighlight %}

{% highlight ruby %}
puts "Sort by age using vales and sort methods " + people.values.sort.inspect
{% endhighlight %}


### Using sort_by method

How to display both keys and values and do a sort by value/age?
We use sort and sort_by

{% highlight ruby %}
people.sort_by { |name, age| age }
{% endhighlight %}


{% highlight ruby %}
puts "Sort by value and show name and age " + people.sort_by { |name, age| age }.inspect
{% endhighlight %}


### Sort_by returns the list as an Array

{% highlight ruby %}
people.sort_by { |name, age| age }.class
{% endhighlight %}

To convert it to a Hash we use to_h method

{% highlight ruby %}
people.sort_by { |name, age| age }.to_h
{% endhighlight %}


# Nested hashes
### A more complex situation

{% highlight ruby %}
people_nested = {
  :fred => { :name => "Fred", :age => 23 },
  :joan => { :name => "Joan", :age => 18 },
  :pete => { :name => "Pete", :age => 54 }
}
{% endhighlight %}


{% highlight ruby %}
people_nested.sort_by { |k, v| v[:age] }
{% endhighlight %}


{% highlight ruby %}
puts "Sort by values the nested hashes " + people_nested.sort_by { |k, v| v[:age] }.inspect
{% endhighlight %}


# References

* [Ruby sort hashes][ruby-sort-hash]
* [hash-tricks-in-ruby][hash-tricks-in-ruby]
* [hashes][hashes]



[ruby-sort-hash]: http://www.rubyinside.com/how-to/ruby-sort-hash
[hash-tricks-in-ruby]: http://thirtysixthspan.com/posts/hash-tricks-in-ruby
[hashes]: https://launchschool.com/books/ruby/read/hashes
