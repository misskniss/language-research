(1) Ruby is a pure object-oriented programming language. It supports multiple programming paradigms, including functional and imperative. It also has a dynamic type system and automatic memory management. It was created in 1993 by Yukihiro Matsumoto of Japan. Ruby is a general-purpose, interpreted programming language like PERL and Python.

(2) Ruby is object-oriented scripting Language and it was followed in the early 2000s by around 20 books on Ruby published in Japan. Ruby is frequently compiled and the output of that compilation is then interpreted. There are a few programs that use Ruby for scripting tasks, and there are doubtless numerous free-standing Ruby programs that would likely qualify as scripts (web scraping, system administration, etc). Ruby is considered a higher level programming language than C++. A high-level language features strong abstractions from computer details. Whereas low-level languages are closer to machine details. Ruby on Rails is a framework that uses and depends on the Ruby programming language. And it is a software framework for creating web applications.

(3) Scope defines where in a program a variable is accessible. Ruby has four types of variable scope, local, global, instance and class. In addition, Ruby has one constant type. Each variable type is declared by using a special character at the start of the variable name as outlined in the following table. 
Name Begins With	Variable Scope
$ 	A global variable 
@ 	An instance variable 
[a-z] or _ 	A local variable 
[A-Z] 	A constant
@@	A class variable

(4) Type systems are a fundamental part of every programming language. In fact, the way a language designer approaches typing goes a long way towards outlining the way that thoughts are expressed in that language. Ruby’s dynamic nature facilitates a style of type system known as duck typing. In particular, duck typing breaks the strong association between an object’s class and its type by defining types based on what an object can do rather than what class it was born from. This subtle shift in semantics changes virtually everything about how you need to think about designing object oriented systems, making it a great topic for Practicing Ruby to cover.

(5) The Ruby language makes it easy to create functions. 
Function Syntax
def functionname(variable)
   return <value>
end
Examples
Your function can compute values and store them in local variables that are specific to the function. Those values can then be returned with the return statement.
def say_hello(name)
   var = “Hello, ” + name
   return var
end
The return statement also can be shortened for very simple functions into a single line
def say_hello(name)
   return “Hello, ” + name
end

(6) A recursive function/method calls itself. For a recursive algorithm to terminate you need a base case and you also need to make sure that you get closer to that base case in each recursive call.
def countdown(n)
  return if n.zero? # base case
  puts n
  countdown(n-1)    # getting closer to base case 
end               

countdown(5)
5
4
3
2
1

(7) An array in Ruby is an object. Arrays can be instantiated with the new method. 
#!/usr/bin/ruby

nums = Array.new

nums.push 1
nums.push 2
nums.push 3
nums.push 4
nums.push 5

puts nums
In the script we first create a nums array. Then we add five integers to it. 
nums = Array.new
An array object is created. 
nums.push 1

