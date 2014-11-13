Lennox Matsinde

Ruby

Ruby is a dynamic, open source programming language with a focus on simplicity and productivity. It has an elegant syntax that is natural to read and easy to write.
Every procedure in Ruby is a method of some object. Some method calls appear to be function calls as in other languages, but in fact they are actually invocations of methods belonging to self. Parentheses can be omitted if unambiguous.
Ruby is a dynamic, reflective, object-oriented, general-purpose programming language. It was designed and developed in the mid-1990s by Yukihiro "Matz" Matsumoto in Japan.

According to its authors, Ruby was influenced by Perl, Smalltalk, Eiffel, Ada, and Lisp.[12] It supports multiple programming paradigms, including functional, object-oriented, and imperative. It also has a dynamic type system and automatic memory management.



Ruby is an objected-oriented scripting language very similar to python (also very popular) with many practical uses.

In terms of scoping in ruby, when you first define a variable, a new scope is created. That variable is then accessible by anything below of it in the code, until the point you leave that current scope e.g. exiting the method.
Ruby is a dynamically and strongly typed. The type of a variable
can be altered at will, and there are strict rules concerning the usage of typed variables.




The Ruby language makes it easy to create functions.

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





Recursion in Ruby

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


Code showing Array Usage:

# Empty array  
var1 = []  
# Array index starts from 0  
puts var1[0]  

# an array holding two strings  
var3 = ['Hello', 'Goodbye']  
puts var3[0]  
puts var3[1]  

browsers = ['Chrome', 'Firefox', 'Safari', 'Opera', 'IE']
browsers.length			 #=> 5
browsers.count 			 #=> 5



