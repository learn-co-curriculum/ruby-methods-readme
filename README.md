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

## Introduction
* Methods are instructions and logic that are defined for programmers by Ruby, like `puts`, or that programmers define themselves.
* To make a custom method, write `def`, short for define, and then the name that you want to call the method. When you are done with your method, finish with an `end`. 
* To make a method run, you must call on it. To call on a method, you simply write the name of the method below it.

## Example: No Arguments

```ruby
def answer_phone
  puts "Hello? Arel speaking."
end

answer_phone
```
The code above will print "Hello? Arel speaking." when it is run.

## Arguments
* Arguments make it easy to give methods information.
* To pass one arguement to a method, you put parentheses after the name of the method. Within those parentheses, put the variable name that you want to call the info. 

### Example: One Argument
* For instance:

```ruby
def answer_phone(name)
  puts name
end

answer_phone("Arel")
answer_phone("Logan")
```
* When run, the code above will print "Arel" and then  will print "Logan". We can see that this is more flexible than the code above becuase the name can change to be any string, instead of being hardcoded as Arel.

* If we want the method answer_phone to print "Hello this is" followed by the value of name, which in the case above is Arel then Logan, we have to add a `#` symbol and wrap the variable in brackets, see below.

```ruby
def answer_phone(name)
  puts "Hello, this is #{name}."
end

answer_phone("Arel")
answer_phone("Logan")
```
* When run, the code above will print "Hello, this is Arel.", just like the first method in this overview. It will then print "Hello, this is Logan." 

### Example: Multiple Arguments
* If we want to pass multiple arguments to the method, we separate those arguments by commas when we define the method AND when we call on the method.
* When defining the method, it helps to use descriptive words or phrases to describe what the order the method is expecting the arguments in.

```ruby
def answer_phone(adjective, name)
  puts "Hello, it is a #{adjective} day at Flatiron School. this is #{name} speaking."
end

answer_phone("beautiful", "Arel")
answer_phone("wonderful", "Logan")
```
The code above will print "Hello, it is a beautiful day at Flatiron School. This is Arel speaking." and then will print "Hello, it is a beautiful day at Flatiron School. This is Logan speaking."
