# Methods in Ruby

## Objectives

1. Understand how methods can define new routines and procedures for our code.
2. Define a method with the `def` keyword, supply the method's body, and close the method definition with the `end` keyword.
3. Invoke a method by calling it by name.

## Video

<video controls width="100%">
  <source src="http://learn-co-videos.s3.amazonaws.com/ruby/introduction-to-methods-and-arguments-ruby.mp4" type="video/mp4" >
    The video accompanying this lab is best enjoyed on Learn.co
</video>

[MP4](http://learn-co-videos.s3.amazonaws.com/ruby/introduction-to-methods-and-arguments-ruby.mp4)

### 1. Introduction to Methods

Methods define a new thing that your program can do. Variables are a mechanism to teach your Ruby program about data; methods teach your Ruby program about a new routine or behavior it can use. Variables are like nouns, methods are like verbs.

For example, imagine needing to say "Hello World!" ten times. You might do something like this:

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

That works pretty well. You made use of a variable to encapsulate the data you wanted to print and then the next ten lines literally print the phrase.

Now imagine later in your program you again want to say "Hello World!" ten times. The entire program would look something like this:

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

We have to repeat the literal procedure for printing the value of `phrase` ten times. If variables encapsulate and abstract data, methods encapsulate and abstract procedure. Instead of literally `puts phrase` ten times, we can instead build a method—a little machine that does exactly that whenever we want.

The method would look like this:

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
Now, when we use the bareword `say_hello_world_ten_times` in our program, it will invoke the method, running the code within the method. So the script above, saying hello ten times, doing other things, then saying hello ten times again could be rewritten as this:

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

That's way cleaner. We define the abstraction, or the machine, `say_hello_world_ten_times` once, but can "call" or "invoke" it—make it run—as many times as we want. Let's look at methods in greater detail.

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

Here we set up the method's structure first, ensuring a proper termination before adding any other complexity. It's also a great practice to indent methods correctly. The body of a method should be indented two (2) spaces, placing it visually within the method. When you `end` the method, go back to the same indentation of the `def`, aligning the opening and closing of the method visually.

Then you can easily define the body of the method and never worry about forgetting to `end` the method.

```ruby
def greeting
  puts "Hello World" # Now code the body of the method.
end
```

### 3. Invoking a Method

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

```bash
$ ruby greeting.rb
$
```

You'll notice that when you run your program, nothing happens. Your program successfully defined the method but it never executed it. Just because you built a machine doesn't mean that you turned it on. Update your `greeting.rb` to entirely read:

File: `greeting.rb`

```ruby
def greeting
  puts "Hello World"
end

greeting
```

Save your file and run it with `ruby greeting.rb`. You'll see:

```bash
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

```bash
$ ruby greeting.rb
Hello World
Hello World
Hello World
Hello World
Hello World
$
```

The bareword `greeting` will execute the body of the defined method.


Next up, we'll learn how to pass information into methods using method arguments. But first, it's your turn to define and invoke a method!

%%%

## Code Challenge I: defining a method that returns a string

Define a method called `best_coding_school` that returns the phrase "The Flatiron School". Then, invoke the method by simply typing the method name, `best_coding_school`.

**A Note On Method Return Values:** We haven't discussed return values in-depth yet. That's coming up soon. For now, just understand that the return value of the method is whatever code is last evaluated in the method––i.e., the last line of the method. The `puts` method, however, returns `nil`. The `best_coding_school` method shouldn't use the `puts` method to output the desired phrase. Instead, the method itself should return the phrase. You can achieve this by simply typing the phrase, enclosed in quotes, within the method and leaving it at that. 

~~~ruby

# code your method definition here!

# invoke your method here!

~~~solution

def best_coding_school
   "The Flatiron School"
end

best_coding_school

~~~validation

assert_equal(response, "The Flatiron School")

~~~

%%%

%%%

## Code Challenge II: defining a method that does math

Define a method called `calculate_sum` that adds two numbers, `7` and `3` and returns their sum. Refer back to the earlier lesson on simple math if you get stuck. Then, invoke your method.

~~~ruby

# code your method definition here!

# invoke your method here!

~~~solution

def calculate_sum
   7 +  3
end

calculate_sum 

~~~validation

assert_equal(response, 10)

~~~

%%%
