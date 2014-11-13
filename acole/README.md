Alex Cole
===============

Ruby
---

> Ruby is a dynamic, open source programming language with a focus on 
> simplicity and productivity. It has an elegant syntax that is natural to read > and easy to write.
> 

https://www.ruby-lang.org/en/

---
### History
Ruby is a language of careful balance. Its creator, Yukihiro “Matz” Matsumoto, blended parts of his favorite languages (Perl, Smalltalk, Eiffel, Ada, and Lisp) to form a new language that balanced functional programming with imperative programming.

He has often said that he is “trying to make Ruby natural, not simple,” in a way that mirrors life.

### Explanations
Ruby is an objected-oriented scripting language with many practical uses and
perhaps most popular that of a web developing language.

In Ruby a new scope is created when you first define a variable. That variable is then accessible by anything "downstream" of it in the code, until the current scope is exited (by leaving a method or loop, for instance).

Ruby is a dynamically and strongly typed. Dynamic as in the type of a variable
can be altered at any time, and strong because strict rules must be followed
concerning the usage of typed variables.

### Code Examples

# Functions
# Syntax

def functionname(variable)
   return <value>
end

# Example

def say_hello(name)
   var = “Hello, ” + name
   return var
end

# Calling a Function

function param1, param2
puts say_hello("alex")	# puts displays to console


# Recursion Example:

def countdown(n)
  return if n.zero? # base case
  puts n
  countdown(n-1)    # getting closer to base case 
end  

# Array Declaration Example:

array = [ '1', '2', '3' ] # simplest
Array.new(3, &plus_1) # => [1, 2, 3] # alternative method



