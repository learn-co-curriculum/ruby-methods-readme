# Methods in Ruby

## Overview

In this lesson, we'll introduce methods, distinguish them from data types, and
cover how to create and execute them in your Ruby program.

You can follow along using IRB by typing `irb` in your terminal and copying the
provided code examples. Alternatively, in the `lib` folder, there is also a
file, `example.rb`, that you can use to copy the code examples into. You can run
this file from the lesson's main directory by typing `ruby lib/example.rb` to
see what it produces.

## Objectives

- Describe how methods can define new routines and procedures for our code.
- Define a method with the `def` keyword, supply the method's body, and close
  the method definition with the `end` keyword.
- Invoke a method by calling it by name.

### Video

<iframe width="560" height="315" src="https://www.youtube.com/embed/njJB-fuE-qE?rel=0&modestbranding=1" frameborder="0" allowfullscreen></iframe><p><a href="https://www.youtube.com/watch?v=njJB-fuE-qE">Introduction to Ruby Methods</a></p>

### Why Use Methods

Methods define a new thing that your program can do. Variables are a mechanism
to teach your Ruby program about data; methods teach your Ruby program about a
new routine or behavior it can use. Variables are like nouns, methods are like
verbs.

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

That works pretty well. You made use of a variable to encapsulate the data you
wanted to print and then the next ten lines literally print the phrase.

Now imagine later in your program you again want to say "Hello World!" ten
times. The entire program would look something like this:

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

We have to repeat the literal procedure for printing the value of `phrase` ten
times. If variables encapsulate and abstract data, methods encapsulate and
abstract procedure. Instead of literally `puts phrase` ten times, we can instead
build a method—a little machine that does exactly that whenever we want.

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

Now, when we use the bareword `say_hello_world_ten_times` in our program, it
will invoke the method, running the code within the method. So the script above,
saying hello ten times, doing other things, then saying hello ten times again
could be rewritten as this:

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

That's way cleaner and follows the code principle "Don't Repeat Yourself" or
DRY. We abstract the action or procedure of putting "Hello World!" ten times
into a method. By defining the method  `say_hello_world_ten_times` once, we can
"call" or "invoke" the method as many times as we want in the future. Let's look
at methods in greater detail.

### Defining a Method

You can define a method in Ruby with the `def` keyword. A method's name can
begin with any lowercase letter. Here's a quick example:

```ruby
def greeting # Method Signature
  puts "Hello World" # Method Body
end # Method Closing
```

That first line, `def greeting`, is called the method signature, it defines the
basic properties of the method including the name of the method, `greeting`.

Once you 'open' a method definition with the `def` keyword, all subsequent lines
in your program are considered the method's body, the actual procedure or code
that your method will run every time it's called.

You must terminate every opening `def` of a method with a corresponding `end` in
order to close the method body. If you don't correctly `end` a method, your
program will have unexpected results or break entirely because of a syntax
error. A good practice is to define the method and then immediately close it
before programming anything into the method.

```ruby
def greeting
  # Leave a line break for the method body
end # Immediately close the method.
```

Here we set up the method's structure first, ensuring a proper termination
before adding any other complexity.

> **Aside**: It's also a great practice to indent methods correctly. The body of
> a method should be indented two (2) spaces, placing it visually within the
> method. When you `end` the method, go back to the same indentation of the
> `def`, aligning the opening and closing of the method visually. Then you can
> easily define the body of the method and never worry about forgetting to `end`
> the method.

```ruby
def greeting
  puts "Hello World" # Now code the body of the method.
end
```

### Invoking a Method

Once you define a method, you can execute the method whenever you want by using
the method name in your code.

```ruby
def greeting
  puts "Hello World"
end

greeting # Executing the method by name
#=> "Hello World"

greeting # Executing the method again
#=> "Hello World"
```

> **Note**: If you have been using IRB so far, exit out of it before continuing.
> The remaining portion of this lesson involves bash commands you will need to
> enter into the terminal.

Let's try making a method we can use over and over. Make a new file called
`greeting.rb` (you can use: `touch greeting.rb` from your terminal). Put the
following code in it:

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

You'll notice that when you run your program, nothing happens. Your program
successfully defined the method but it never executed it. Just because you built
a machine doesn't mean that you turned it on. Update your `greeting.rb` to
entirely read:

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

Now your program actually executed the program. Update the code again to
entirely read:

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

#### Writing Code vs Reading About Code

Programmers love conventions, or agreed upon rules that help them talk to each
other about code. A common syntax convention for Ruby methods is to preface them
with a `#`, and in subsequent lessons, you might see methods written with a `#`
in front of the method name. For example, if a method is named 'greeting',
rubyists will often refer to it as `#greeting`. This is so that other rubyists
can instantly recognize it as a method, as opposed to a variable or a bareword
or a class.  But remember that when you write it in your code, it should be
`greeting` and not `#greeting`.

<p data-visibility='hidden'>View <a href='https://learn.co/lessons/ruby-methods-readme' title='Methods in Ruby'>Methods in Ruby</a> on Learn.co and start learning to code for free.</p>
