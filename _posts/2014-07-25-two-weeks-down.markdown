---
layout: post
title:  "Two weeks down, seven to go..."
date:   2014-07-25 12:05:10
categories: dbc phase-1
---

![My helpful screenshot](/assets/solong.jpeg)

It has been far too long since my last post and it isn't because I've been crazy busy...which I have been, but more that my exhaustion level after a day at DBC is so high that I just want to unwind at the end of the day.

This week consisted of a mock-assessment to properly analyze our status with the material at this point and mine went pretty well. The days are packed with excitement, frustration, enlightenment, fear and possibly all ranges of emotions you could think of. We have lectures, emotional empathy training, stand-ups, pairing sessions, assessments, code reviews and many other new things every day. My time has been so fulfilling thus far and I am extremely eager to get up every morning and start a new day at DBC.

My Chicago life has been pretty awesome thus far as well. I have had Portillo's like 4 times and have no plans on slowing down. I wish I had more time to see more of the city and go out and about but my addiction to learning doesn't allow me much escape.

I'm now realizing this blog post is jumping all over the place, and I apologize for that. I, in conclusion, wanted to write a little about things I've learned thus far. Some key points are object oriented design, data parsing and command line arguments. It is a little odd to realize we are spending so much time in the command line when in just 1 short week, we will jump heavily into the web but the building blocks are essential. The programs I'm writing now are so much more sophisticated and complex than anything I've done to before today and could not be happier about it. I'll look at a snippet of my code for parsing CSV data.

{% highlight ruby %}
def return @list if @list
    @list = []
    CSV.foreach('todo.csv') do |item|
        @list << Task.new(item)
    end
end
#=> adds each item to the list array.
{% endhighlight %}

Two weeks ago, I wouldn't have exactly known what was going on on the above code and I'll try and explain as best I can here. First I am using the `CSV` class for Ruby so I will need to require it at the top of my document. Then, I have a method called read_file that takes no parameters.

The next line is basically a little "only run this method one time" check. It will return the list of a list exists. It is a little check trick I learned here at DBC. `@list` is a class variable as can be denoted by the `@` symbol. You don't know it from this snippet but I have initialized this class with `@list = nil`. That is our way of making the return line work. The first check is saying `return @list` if it exists, and since we set it to nil, it doesn't.

{% highlight ruby %}
CSV.foreach('todo.csv') do |item|
    @list << Task.new(item)
end
{% endhighlight %}

This line is where all the magic happens. To learn a bit more about the Ruby CSV class, click [here][csv]. So this is calling the CSV class and running a foreach on it by passing the parameter of a filename to it. The do `|item|` snippet is a way of running the method iteratively and return the block of code for each line that .foreach returns.

The method takes a CSV file, parses each line, and returns the line into a new Task object. I didn't do the best job explaining this, I can tell, but it makes total sense to me. I'm excited that I'm learning-and learning so fast.

[csv]: http://ruby-doc.org/stdlib-1.9.2/libdoc/csv/rdoc/CSV.html