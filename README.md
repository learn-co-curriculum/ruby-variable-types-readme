# Ruby Variable Types and Their Scope

Variables hold data of any type in memory. In Ruby, there are a few different variable types we'll be going over. Note that here "type" does not mean data type, unlike languages like C, C++, and Objective-C, data types in Ruby do not need to be explicitly declared in when variables are assigned.

We're going to focus here on 3 variable types. There are 5 total that are used in Ruby, but 2 we will focus on later when we learn about Classes and Object Orientation.

## Local Variables

You should already be familiar with declaring local variables. They're written most commonly as lowercase words, or sometimes you might see developers declare them with an underscore (like `_this`). Most commonly, they look like this:

```ruby
languages = ["Ruby", "JavaScript", "C", "Python"]
```

Local variables are distinguished from other types of variables primarily by their `scope`. Local variables have a local scope, meaning that where they are declared their definition remains.

If we define a variable within a method definition, only the method knows about that variable. Any type of reference to that local variable will result in an error;

```ruby
def my_method
  local_variable = "Only my method knows about me!"
end

puts local_variable
=> NameError: undefined local variable or method `local_variable' for main:Object
```

## Global Variables

Global variables, as you may have guessed, have a global scope. These variables my be accessed anywhere in a program.

Global variables are declared with a dollar sign in front of them, like so:

```ruby
$global_variable = "The whole program knows about me!"
```

Global variables should be used **very** sparingly, if at all. The concern with global variables is that because of their global reach, they can break encapsulation. If any method can modify a global variable, then any other place that relies on that variable can work in unpredictable ways. This is also difficult to debug.

## Constants

Constants are written either in all uppercase or capitalized. They have a global scope when defined globally, and local scope when defined within classes and modules. Constants cannot be defined within methods. When constants are initialized, they cannot be reassigned. For example, this would result in an error:

```ruby
CONSTANT = "I'm initialized!"
CONSTANT = "I can't be reassigned!"

=> warning: already initialized constant CONSTANT
```

You'll most often see constants used in class naming, or to hold data that will never need modification, like an array of words that will never be added to, or a hash of word definitions.
