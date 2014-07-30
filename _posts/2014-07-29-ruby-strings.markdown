---
layout: post
title:  "Ruby Strings, the difference between ' and ''"
date:   2014-07-29 12:05:10
categories: ruby, strings
---

Today we worked in SQL queries and writing Ruby to translate SQL database rows into Ruby objects. This, in itself, was just extremely exciting and warrants its own blog post, but today I want to write about the difference between using single and double quotes in Ruby.

So, in the world of an actual `String`, Ruby does not necessarily care. If we have two strings:

{% highlight ruby %}
str1 = "string one"
str2 = 'string two'

p str1
#=> "string one"
p str2
#=> "string two"
{% endhighlight %}

Both `str1` and `str2` returned a string of the same format, no difference can be noticed. So, in this regard, using a single/double quote is solely preference. Some programmers feel the necessity to keep the code "clean" so they use single quotes, and others like the literal translation as in <code>this variable is a string</code>.

Now, the real fun begins when we look into interpolation and Ruby methods. If we were to try to send a command to a SQL database that looks like this:

{% highlight ruby %}
id = 1
$db_name.execute(
    "SELECT * FROM db_name WHERE id = #{id}"
)
#=> id in this case would be 1
$db_name.execute(
    'SELECT * FROM db_name WHERE id = #{id}'
)
#=> id in this case would translate to \#{id}
{% endhighlight %}

As you can see from these two examples, using a single quotes would escape the `id`, not allowing us to search for the specific value. And since SQL requires you to send its statement as a string that is basically inputs into a terminal like command, you need to pass some form of string. You may be saying to yourself, "Joey, why don't you just use the literal variable then?" Well, if we did that it would just pass a string id as the lookup value so we would still be in the same situation. 

While it may be cleaner to use single quotes for most situations, be very careful when you are needing to do some interpolation as the value will not translate to what you are looking for. Anyway, that is some basic Ruby string and single vs. double quote situations.