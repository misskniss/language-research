History of Ruby: Ruby was developed in the mid 1990s by Yukihiro "Matz" Matsumoto.  It is a dynamic, object oriented 
and general purpose programming language.  It was influenced by other coding languages such as Perl, Smalltalk, Eiffel, Ada and Lisp.  

What's it good for?
Ruby is object-oriented with inheritance and metaclasses.  It is a scripting language designed with the user experience in mind.
It follows the principle of least astonishment and should behave in a way that minimizes confusion for experienced users.
It is not low level.

Scope Rules:
Ruby has four types of variable scope, local, global, instance and class. Each type is declared by using a special character at
the start of the variable name.
$ - global.  @ - instance [a-z] or _ - local. [A-Z] -constant @@ A class variable

Typing System:
Ruby using duck typing and dynamic typing.

Functions: 
Methods should be defined before calling them with the keywords def at the beginning and end at the end.  

def method_name [( [arg [= default]]...[, * arg [, &expr ]])]
   expr..
end

Recursion:

Example: def countdown(n)
  return if n.zero? # base case
  puts n
  countdown(n-1)    # getting closer to base case 
end 

Arrays:

nums = [1, 2, 3, 4, 5]

nums.each do |num|
    puts num
end

Results will be: 

1
2
3
4
5
