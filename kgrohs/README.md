Konrad Grohs
===============

Ruby
---

> Ruby is a dynamic, reflective, object-oriented, general-purpose programming language. 
> It was designed and developed in the mid-1990s by Yukihiro "Matz" Matsumoto in Japan.
>
> According to its authors, Ruby was influenced by Perl, Smalltalk, Eiffel, Ada, and Lisp.
> It supports multiple programming paradigms, including functional, object-oriented, and imperative.
> It also has a dynamic type system and automatic memory management.

https://www.ruby-lang.org/en/

---

> Variables in Ruby: 
> 
> $			A global variable
> 
> @			An instance variable
> 
> [a-z] 	or _	A local variable
> 
> [A-Z]		A constant
> 
> @@		A class variable


Describe language

 TODO

---
### Code Samples

```ruby
# The following code creates an array of 5 numbers, 1 through 5.
nums = [1, 2, 3, 4, 5]

# you can loop with .each
nums.each do |num|
    puts num
end

# Ruby has some built in functionality 
Math.sqrt(9)

# Ruby can create methods
def h
  puts "Hello World!"
end

# Ruby can even create classes and methods can have optional parameters..
class Greeter
 def initialize(name = "World")
     @name = name
   end
   def say_hi
     puts "Hi #{@name}!"
   end
   def say_bye
     puts "Bye #{@name}, come back soon."
   end
 end
 
 
TODO

more code samples


