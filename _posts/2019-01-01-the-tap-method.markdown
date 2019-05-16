---
title: "The Tap Method"
layout: post
date: 2019-01-11 22:44
image:
headerImage: false
tag:
- ruby
- rails
- chaining
star: true
category: blog
author: woodylucas
description: The ability to enhance chaining with ruby has just gotten better. My first blog is about the Tap Method.
---
Over the pass few days, I stumbled upon a method referred to as tap. It was very mind boggling, because I didn’t have any idea on what it was, or what its actual purpose was.

After going through numerous documentation, it made it pretty obvious that this method basically linked methods together; without actually changing the the value. Tap is unable to return anything, then what it is actually given. To be honest, the proper word is just CHAINING.

Now I know you all are probably saying, what is the point? That’s just useless, we’re only returning what the value is just given, right? But let us just think about it, this gives us the power to basically just “tap” into a method chain and create a tangential function.

![Alt Text](https://media.giphy.com/media/3o6ZtfraiyfUkNDwru/giphy-downsized-large.gif){:height="50%" width="200%"}

So lets look at these examples:

```ruby
(1..10).map {|x| x*x }.tap {|x| puts "array: #{x.length} items long"}.join

array: 10 items long
 => "149162536496481100"
user = User.new
user.username = "foobar"
user.save!

```

As a reader it takes me 3 lines to recognize that someone is just creating an instances for the class User. We also had to make a temporary variable.

So what if I just “tap that” ?

```ruby

user = User.new.tap do |u|
  u.username = "foobar"
  u.save!
end

```

Look how much cleaner our code looks, and that temporary variable is GONE!

![Alt Text](https://media.giphy.com/media/oOGf9Xvp75ukzLQsQk/giphy.gif){:height="50%" width="200%"}


Tap gives us the ability, to access a part of the program that was really difficult to access. I really wonder what else can tap actually do ?
