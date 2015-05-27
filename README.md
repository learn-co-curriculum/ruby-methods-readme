---
tags: readme
language: ruby
resources: 0
track: web development
topic: ruby
unit: methods
lesson: defining, calling, scope, arguments
---

# Methods in Ruby

## Objectives

1. Understand how methods can define new routines and procedures for our code.
2. Define a method with the `def` keyword, supply the method's body, and close the method definition with the `end` keyword.
3. Evoke a method by calling it by name.
4. Understand the purpose of supplying a method with arguments.
5. Define methods that accept arguments.
6. Use a method's arguments within the body of the method.
7. 

## Video

<video controls width="100%">
  <source src="http://learn-co-videos.s3.amazonaws.com/ruby/introduction-to-methods-and-arguments-ruby.mp4" type="video/mp4" >
    The video accompanying this lab is best enjoyed on Learn.co
</video>

[MP4](http://learn-co-videos.s3.amazonaws.com/ruby/introduction-to-methods-and-arguments-ruby.mp4)

### 1. Introduction to Methods

Methods define a new thing your program can do. Variables are a mechanism to teach your Ruby program about data. Methods teach your Ruby program about a new routine or behavior it can use.

For example, imagine needing to say "Hello World!" ten times. You might do something like:

```ruby
phrase = "Hello World!"
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
```

That works pretty well. You made use of a variable to encapsulate the data you wanted to print and then the next 10 lines literally print the phrase.

Now imagine later in your program you again want to say "Hello World!" ten times. The entire program would look something like:

```ruby
phrase = "Hello World!"
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase

# ... The rest of the program

puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
puts phrase
```

We have to repeat the literal procedure for printing the value of `phrase` ten times. If variables encapsulate and abstract data, methods encapsulate and abstract procedure. Instead of literally `puts phrase` ten times, we can instead build a method, a little machine that does exactly that whenever we want.

The method would look like:

```ruby
def say_hello_world_ten_times
  phrase = "Hello World!"
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
end
```

Now when we use the bareword `say_hello_world_ten_times` in our program, it will evoke the method, running the code within the method. So the script above, saying hello ten times, doing other things, then saying hello ten times again could be rewritten as:

```ruby
def say_hello_world_ten_times
  phrase = "Hello World!"
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
  puts phrase
end

say_hello_world_ten_times

# ... The rest of the program

say_hello_world_ten_times
```

That's way cleaner. We define the abstraction, or the machine, `say_hello_world_ten_times` once, but can call it or evoke it, make it run, as many times as we want. Let's look at methods in greater detail.

### 2. Defining a Method

You can define a method in Ruby with the `def` keyword. A method's name can begin with any lowercase letter. Here's a quick example:

```ruby
def greeting # Method Signature
  puts "Hello World" # Method Body
end # Method Closing
```

That first line, `def greeting`, is called the method signature, it defines the basic properties of the method including the name of the method, `greeting`.

Once you open a method definition with the `def` keyword, all subsequent lines in your program are considered the method's body, the actual procedure or code that your method will run every time it's called.

You must terminate every opening `def` of a method with a corresponding `end` in order to close the method body. If you don't correctly `end` a method, your program will have unexpected results or break entirely because of a syntax error. A good practice is to define the method and then immediately close it before programming anything into the method.

```ruby
def greeting
  # Leave a line break for the method body
end # Immediately close the method.
```

Here we setup the method's structure first, ensuring a proper termination, before adding any other complexity. It's also a great practice to indent methods correctly. The body of a method should be indented 2 spaces, placing it visually within the method. When you `end` the method, go back to the same indentation of the `def`, aligning the opening and closing of the method visually.

Then you can easily define the body of the method and never worry about forgetting to `end` the method.

```ruby
def greeting
  puts "Hello World" # Now code the body of the method.
end
```

### 3. Evoking a Method

Once you define a method, you can execute the method whenever you want by using the method name in your code.

```ruby
def greeting
  puts "Hello World"
end

greeting # Executing the method by name
#> "Hello World"

greeting # Executing the method again
#> "Hello World"
```

Try it out. Make a new file called `greeting.rb` (you can use: `touch greeting.rb` from your terminal). Put the following code in it:

File: `greeting.rb`

```ruby
def greeting
  puts "Hello World"
end
```

Save your file and run it with `ruby greeting.rb`. You'll see:

```
$ ruby greeting.rb
$
```

You'll notice that when you run your program, nothing happens. Your program successfully defined the method but it never executed it. Just because you built a machine doesn't mean you turned it on. Update your `greeting.rb` to entirely read:

File: `greeting.rb`

```ruby
def greeting
  puts "Hello World"
end

greeting
```

Save your file and run it with `ruby greeting.rb`. You'll see:

```
$ ruby greeting.rb
Hello World
$
```

Now your program actually executed the program. Update the code again to entirely read:

File: `greeting.rb`

```ruby
def greeting
  puts "Hello World"
end

greeting
greeting
greeting
greeting
greeting
```

Save your file and run it with `ruby greeting.rb`. You'll see:

```
$ ruby greeting.rb
Hello World
Hello World
Hello World
Hello World
Hello World
$
```

The bareword `greeting` will execute the body of the defined method.

### 4. Understanding Arguments

Imagine needing to build a method that counts from 1 to 10. We could code something like this, using a cool ruby loop, `upto`.

```ruby
def count_from_one_to_ten
  1.upto(10) do |i| # Opens the loop for all number between 1 and 10
    # Don't worry about the line above, just know that the next line 
    # executes once for every number between 1 and 10, with i being
    # equal to the current number or iteration on every loop (1,2,3,etc).    
    puts i

  end # This ends the loop's block.
end # Ends the method
```

This method will print out every number between 1 and 10. Try it out, open an IRB session by running `irb` from your command line. Once you're in your IRB shell, paste in the code:

```ruby
def count_from_one_to_ten
  1.upto(10) do |i|
    puts i
  end
end
```

```
$ irb
001:0 > def count_from_one_to_ten
002:1 >   1.upto(10) do |i|
003:2>      puts i
004:2 >   end
005:1 > end
=> :count_from_one_to_ten
```

You've now defined the method. Notice that it did not execute. Type the following into IRB to execute your method: `count_from_one_to_ten`.

```
006:0 > count_from_one_to_ten
```

You should see:

```
1
2
3
4
5
6
7
8
9
10
=> 1
```

As amazing as this method is, it's still pretty literal. It hard-codes, or directly specifies the number to count to and the number to count from. If we wanted to build a method that counts from one to twenty, we'd have to re-implement the majority of the original logic from `count_from_one_to_ten`:

```ruby
def count_from_one_to_twenty
  1.upto(20) do |i|
    puts i
  end
end
```

Notice the only things that changed are the method name and the number `20` in the body of the method. It's as though that information should be specifiable or configurable when you call the method, otherwise we'd have to build every permutation of the method. Ideally, we would want our method to be more dynamic, more abstract, only providing the details of the number to count to on execution, not on definition.

Good news, that's exactly what method arguments (sometimes referred to as parameters) are for:

```ruby
def count_from_one_to(end_of_range)
  1.upto(end_of_range) do |i|
    puts i
  end
end

count_from_one_to(3)
# > 1
# > 2
# > 3

count_from_one_to(100)
# > 1
# > 2
# > 3
# > ...
# > 100
```

Let's dig into how to add arguments to our methods.

### 5. Defining Method Arguments

To add arguments to a method, you specify them in the method signature, the line that starts with `def`), after the method's name, in this case `count_from_one_to`), enclosed by `()`, as a list of comma separated barewords, in this case only a singular argument is specified, `count_from_one_to(end_of_range)`.

```ruby
  # method name       argument list
def count_from_one_to(end_of_range)
  # ...
end
```

Arguments create new local variables that can be used within the method. When you name an argument, all you are defining is what bareword you want to use to access that data, just like when you create a variable. Arguments follow the same rules as local variables, they can be any word that starts with a lowercase letter and they should be as semantic, describing the meaning of the data, as possible.

You can define a method to accept as many arguments as you want, in the example above, as dynamic as our `count_from_one_to` method is now that it accepts an `end_of_range` at which to stop counting, it still allows start at `1`. What if we wanted to change that as well? We could code the method to accept two arguments:

```ruby
  # method name   first_argument  second_argument
def count_from_to(start_of_range, end_of_range)
  # ... We'll see this implementation below, can you guess it?
end

count_from_to(1,3)
# > 1
# > 2
# > 3

count_from_to(5,25)
# > 5
# > 6
# > 7
# > ...
# > 25
```

To accept multiple arguments, simply separate the barewords in the argument list with commas.

#### Required Arguments

Once you define arguments for a method, they become required when you evoke or call the method. If you define a method that accepts a singular argument, when you call that method, you must supply a value for that argument, otherwise, you get an `ArgumentError`. Here's an example:

```ruby
def count_from_one_to(end_range)
  # ... etc
end

count_from_one_to() # I explicitly call the method without a value for the argument end_range
# > ArgumentError: wrong number of arguments (0 for 1)
```

In Ruby, all arguments are required when you evoke the method. You can't define a method to accept an argument and call the method without that argument. Additionally, a method defined to accept one argument will raise an error if called with more than one argument.

```ruby
def count_from_one_to(end_range)
  # ... etc
end

count_from_one_to(100, 5) # The method accepts 1 argument and I supplied 2.
# > ArgumentError: wrong number of arguments (2 for 1)
```

By default all arguments defined in a method are required in order to correctly evoke, call, or execute that method. If you build the method to behave a certain way and have certain expectations about data, you must follow those rules.

#### Optional Arguments with Default Values

Often we want our methods to accept arguments but also have a default value for that argument. Imagine our use-case of the method `count_from_to`. We designed that method to be very dynamic, you can supply it with 2 values, a number to start counting from and a number to stop counting at. That means that if we want to count from 1 to 100, we need to evoke `count_from_to(1,100)`, if we want to count from 1 to 10, we need to evoke `count_from_to(1,10)`, from 1 to 1000, we need to evoke `count_from_to(1,1000)`. It's probably a reasonable assumption that unless specified, we want to start counting from 1. However, given the method definition of:

```ruby
def count_from_to(start_of_range, end_of_range)
  # ...
end
```

We would constantly need to provide a value for the argument `start_of_range`, even if it was obvious and common, like the value `1`. The method is defined to require two arguments no matter what. Evoking it as: `count_from_to(100)` would raise `ArgumentError: wrong number of arguments (1 for 2)`.

How can we supply a default value for an argument thereby making it optional upon method evocation? Simple. In the argument list, assign a default value.

```ruby
#                 assigning a default value
def count_from_to(start_of_range = 1, end_of_range)
  # ...
end
```

In our argument list, `(start_of_range = 1, end_of_range)`, we simply assign the argument `start_of_range` a default value of `1`. By doing so, if the method is evoked with only one supplied argument, ruby will assume the value of the other argument to be its defaut, `1`:

```ruby
#                 assigning a default value
def count_from_to(start_of_range = 1, end_of_range)
  # ...
end

count_from_to(100)
# Will count from 1 to 100

count_from_to(10)
# Will count from 1 to 10

count_from_to(10, 100)
# Will count from 10 to 100

count_from_to
# Will raise an ArgumentError: wrong number of arguments (0 for 1..2)
```

With default arguments our once simple machine becomes profoundly useful and abstract:

```ruby
#                 1 arg with default, 2 required arg
def count_from_to(start_of_range = 1, end_of_range)
  start_of_range.upto(end_range) do |i|
    puts i
  end
end
```

We can now evoke this method with `count_from_to(100)` to count from 1 to 100. Evoking this method with only 1 argument forces ruby to assume that you the programmer are supplying a value for the undefined argument, `end_of_range` and not for `start_of_range` which has a default value.

You can also evoke it with `count_from_to(100,1000)` to count from 100 to 1000, now supplying values for both arguments. 

That's the power of abstraction when combining methods with arguments. You can build a machine, a method, that changes it's behavior when it is evoked, even containing defaults for certain values.

Default arguments are easy to add, you simply assign them a default value with `=` in the argument list to inherit if the argument is not supplied upon evocation. There's no limit to the amount of arguments you can make default.

```ruby
#                 1 arg with default, 2 arg with default
def count_from_to(start_of_range = 1, end_of_range = 100)
  start_of_range.upto(end_range) do |i|
    puts i
  end
end

count_from_to
# > 1
# > 2
# > 3
# > ...
# > 100

count_from_to(10)
# > 1
# > 2
# > 3
# > ...
# > 10

count_from_to(10,20)
# > 10
# > 11
# > 12
# > ...
# > 20
```

Method arguments, both required and optional, make methods powerfully abstract and dynamic machines that are easy to build yet very flexible and adaptable to different situations and requirements. Get used to defining methods with required and default arguments and calling them correctly.

### 6. Using Arguments in Methods

Now that we know how to define a method with arguments, either required, optional, or both, we should quickly talk about using those arguments, that data, within the method. Consider the simpler example of `count_from_one_to(end_range)`. This is a simple method that will count up to the number supplied to the method upon evocation.

```ruby
def count_from_one_to(end_range)
  1.upto(end_range) do |i|
    puts i
  end
end

# > count_from_one_to(5) # Will count from 1 to 5
# > count_from_one_to(50) # Will count from 1 to 50
```

When we define a method with arguments we are defining a bareword that we can use to reference the actual value supplied to the method upon evocation. We built a method that will count from 1 to any specified number. When we actually call that method, we need a word, an abstraction, a variable, that we can refer to that idea of "any specified number" as. That's an argument.

```ruby
def count_from_one_to(end_of_range)
  1.upto(end_of_range) do |i|
    puts i
  end
end
```

When we build that method we might ask ourselves, "Up to what number might this method count to?". The answer is "any number supplied, it doesn't matter." That's what makes the method abstract, the detail of what number it counts up to is hidden until the method is actually evoked: `count_from_one_to(10)`. Only then do we know that the method counts up to 10. The value of `end_of_range` is only supplied upon evocation.

When we define a method argument, we can assume that a valid value for that argument is provided upon execution of the method. The point of the argument is to make some aspect of the methods procedure abstract. Compare the original method `count_from_one_to_ten` to our dynamic method with an argument for the end of the counting.

```ruby
def count_from_one_to_ten
  1.upto(10) do |i|
    puts i
  end
end
count_from_one_to_ten #> Counts from 1 to 10

def count_from_one_to(end_of_range)
  1.upto(end_of_range) do |i|
    puts i
  end
end

count_from_one_to(100) #> Counts from 1 to 100
count_from_one_to(50)  #> Counts from 1 to 50
```

The bareword we use as the argument's name in the method signature becomes a local variable within the method. Through that variable we can reference the value of the argument supplied at evocation.

With the code above, when we say: `count_from_one_to(100)`, the value of the argument `end_of_range` is 100. During the particular runtime evoked by `count_from_one_to(100)`, any reference to `end_of_range` will have the value of `100`, allowing the method to behave as intended.

Similarly, when we say: `count_from_one_to(50)`, the value of the argument `end_of_range` is 50. So During that particular evocation, `count_from_one_to(50)` the value of the argument `end_of_range` is `50`, so the method behaves differently.

Method arguments simply create local variables for you to refer to the value used when the method is actually evoked. Imagine the following examples:

```ruby
def say_hello_ten_times
  10.times do 
    puts "Hello"
  end
end
say_hello_ten_times
# > Will say "Hello" 10 times.
```

The first thing we should abstract from this very literal method is the phrase that is being said 10 times. Let's add an argument to the method and use it within the method body.

```ruby
def say_ten_times(phrase) 
  # phrase is a local variable referencing the value passed on evocation.
  10.times do 
    puts phrase 
  end
end
say_ten_times("You're awesome") # phrase now equals "You're awesome"
# > Will say "You're awesome" ten times
say_ten_times("You're programming") # phrase now equals "You're programming"
# > Will say "You're awesome" ten times
say_ten_times # > Will raise an ArgumentError, 0 for 1.
```

In the first example we abstract the phrased said 10 times out of the literal method name and into a dynamic required method argument. But if we evoke the method without a phrase to say, we get an ArgumentError, after all, how can we say something 10 times when we don't even know what we're saying?

Let's make it more dynamic with a default phrase.

```ruby
def say_ten_times(phrase = "Hello")
  10.times do 
    puts phrase
  end
end

say_ten_times("I <3 Ruby")
# > Will say "I <3 Ruby" ten times
say_ten_times
# > Will say "Hello", the default value for phrase, ten times.
```

Awesome, no more errors and we have a default value for the variable `phrase`
within the method.

Let's take it a step further, in addition to abstracting the phrase repeated, yet providing a default phrase "Hello", let's abstract the amount of times the phase is repeated. So we add an additional argument to the method.

```ruby
def say_x_times(phrase = "Hello", x)
# Below, the once literal value 10 is replaced with the dynamic value of x
# supplied to the method when it is evoked.
  x.times do 
    puts phrase
  end
end
```

Notice where we once used the literal value `10` in the method body, we now replace that with a reference to `x`. The value for `x` will be supplied when the method is evoked, as demonstrated quickly below:

```ruby
def say_x_times(phrase = "Hello", x)
  x.times do 
    puts phrase
  end
end

say_x_times(10)
# > Will print "Hello" 10 times.
# Since x is required and phrased is optional, ruby assumes that 10 is the
# value for the required argument, x, and not the optional argument, phrase.

say_x_times("I can code", 10)
# > Will print "I can code" 10 times.

say_x_times
# > ArgumentError: wrong number of arguments (0 for 1..2)
# Calling the method with no arguments raises an error. 
```

That's really it. We've covered how to define a method, how to add arguments, how to make arguments optional by providing a default value, and how to use the arguments within the method.
