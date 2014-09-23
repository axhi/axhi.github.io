---
layout: post
title:  "Hooray for optimization!"
date:   2014-06-24 12:05:10
categories: ruby, optimization
---

SQL databases are an amazing tool and can do a ridiculous amount of things. The problem with amazing tools like this one is that can perform so many functions, which creates a whole slew of computer processing problems. So, as we learn about databases and how to create, manipulate, and store data we will also need to learn how to optimize these tables to return query results in the shortest amount of time possible.

After performing some research on the subject I found a few things to do to insure a timely database query. The first thing to keep in mind is to fully understand how your database will be used. The queries you will run on your database, how often, and how complex can be controlled if you know what you are looking for.

Below is a link to a Microsoft checklist that is useful for increasing SQL service performance.

####Scale Up vs Scale Out
Scaling is the process of literally adding more computing power to your servers. Scaling up is considered vertical scaling, this is done by adding more processors and RAM to a server (beefing up the one you have). Scaling out is considered horizontal, and that is adding more physical servers. They each have their pros/cons but as far as things we can accomplish in our code, it doesn't relate that much.

![Optimzation image](/assets/optimize.png)

####Schema/Queries
The schema of a database should contain appropriate data types and all primary keys should be properly defined. It is important to not fill a database with keys that aren't necessary or that can be utilized elsewhere. As far as Queries go, there are a lot of things that can be done to speed up results and query times. A few that should become part of our regular code should be to only return rows/columns that are needed. Try not to run `*` on `SELECT` unless you need to return all fields. Also, operators such as `NOT LIKE`, query long and can be written with well formed `IN` statements instead.

There are so many ways to just shorten queries and query loads that optimizing the database itself hasn't even come up yet. A lot of my research said that optimizing database performance will start with good database design. This can be accomplished by keeping in mind the Schema/Query section I listed and going through the handy checklist from the resources section.

####Resources
[Microsoft's SQL Checklist][SQL] >> 
[Foliotek's Optimization Guide][optimization]

[SQL]: http://msdn.microsoft.com/en-us/library/ff647681.aspx
[optimization]: http://www.foliotek.com/devblog/sql-server-database-optimization-a-beginners-guide/
