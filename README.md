# Ruby Variable Types and Their Scope

## Objectives

1. Learn about the different types of variables in Ruby
2. Learn about the scoping of these variable types

## Introduction

Variables hold data of any type in memory. In Ruby, there are a few different variable types we'll be going over. Note that here "type" does not mean "data type". Unlike in languages such as C, C++, and Objective-C, data types in Ruby do not need to be explicitly declared when variables are assigned.

We're going to focus here on three variable types. There are five total that are used in Ruby, but we will focus on the other two later when we learn about classes and object-orientation.

## Local Variables

You should already be familiar with declaring local variables. They're written most commonly as lowercase words, or sometimes you might see developers declare them with an underscore (like `_this`). Most commonly, they look like this:

```ruby
languages = ["Ruby", "JavaScript", "C", "Python"]
```

Local variables are distinguished from other types of variables primarily by their "scope". Local variables have a "local scope", meaning that their definitions remain where they are declared.

If we define a variable within a method definition, only the method knows about that variable. Any type of reference to that local variable will result in an error;

```ruby
def my_method
  local_variable = "Only my method knows about me!"
end

puts local_variable
=> NameError: undefined local variable or method `local_variable' for main:Object
```

## Global Variables

Global variables, as you may have guessed, have a "global scope". These variables may be accessed anywhere in a program and are declared with a dollar sign in front of them, like so:

```ruby
$global_variable = "The whole program knows about me!"
```

Global variables should be used **very** sparingly, if at all. The concern with global variables is that because of their global reach, they can "break encapsulation"—if any method can modify a global variable, then any other place that relies on that variable can work in unpredictable ways. This can be very difficult to debug.

## Constants

Constants are written either in all UPPERCASE or they are Capitalized. They have a global scope when defined globally, and local scope when defined within classes and modules. Constants cannot be defined within methods. When constants are initialized, they should not be reassigned. Attempting to do so will result in a warning:

```ruby
CONSTANT = "I'm initialized!"
CONSTANT = "You shouldn't reassign me!"

=> warning: already initialized constant CONSTANT
```

You'll most often see constants used in class naming, or to hold data that will never need modification, like an array of words that will never be added to, or a hash of word definitions.
