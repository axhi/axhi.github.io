---
layout: post
title:  "Active Record"
date:   2014-07-06 12:05:10
categories: dbc phase-0 active-record
---

Wo-hoo! Active record! While one would not regularly address something such as Active Record with such excitement and enthusiasm, it is extremely important to the Model-View-Controller (MVC) model which Ruby relies on. Active record handles the transformation of data from a database, such as a SQL table, to a Ruby object.

The great thing about Active Record is that you can bypass SQL statements and queries by just using ActiveRecord to map the database row and perform the function for you. And then you can create models to represent table rows and headings.

As an example, we can go through a table for a user profile.
{% highlight ruby %}
class Users < ActiveRecord::Base
end
{% endhighlight %}

This assigns the Users class to the table of the same name. Now, however the table was created, we can call methods from the class, after creating a new one based on our table schema.

{% highlight sql %}
CREATE TABLE users (
    id int NOT NULL auto_increment,
    username varchar(255),
    email varchar(255),
    age int
);
{% endhighlight %}

From that SQL table we can now call all these elements after making a new class from our ActiveRecord class above.

{% highlight ruby %}
user1 = Users.new
user1.name = "John Smith"
user1.email = "jsmith@jsmith.com
user1.age = 25
{% endhighlight %}

Now when we call these elements, they will populate from the database we setup. Following the CRUD method, which is Create, Read, Update, Delete - modifications can be made the table and actions cal be called as it is stored in an array type object that can be iterated and what have you.