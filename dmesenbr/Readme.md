David Mesenbrink
--------------
### Ruby Programming Language

Ruby is a flexable multi-use scripting language released first in 1995 by Yukihiro Matsumoto. The motivation for creating Ruby was to have an object oriented scripting language. Since initial release, Ruby has gone through multiple major releases with version 2.0 being released in December of 2013.

Currently Ruby is used most commonly with the Ruby on Rails Framework to create websites and web content. It is growing in popularity because of its easy to use syntax and fast development cycles.

#### Technical Details

Ruby is run through an interpreter as it is a scripting language. It is very high level and all of the memory allocation is automatic. The language is strongly object oriented as even literals are objects. 

**Scope**

By definition, ruby is Statically scoped. However, ruby is highly flexible with scoping, you can declare the scope of 
variables to be global, instance, class, or local depending on the preceding symbol. Ruby also supports closures. 

**Typing**

Ruby uses both duck and dynamic typing. The language will complain if you pass the wrong kind of data into a function. However if a variable was assigned an integer it could then be assigned a string at any later point. You can even add both numbers and strings into the same array. It is up to the developer to avoid problems with typing. 

**Functions**

Functions in Ruby are defined using the keywords __def__ and __end__ to mark their beginning and end. For example:

        def write_name name
            puts name
        end

Functions can also be embeded in classes and become public member functions then by default.

**Recursion Sample**

For this sample I create a method which takes a positive integer and returns the sum of all its digits

        def sumofdigits number
            if number<10 
                sum=number
            else
                sum=(number/10)+sumofdigits(number%10)
            return sum
        end

**Array Sample**

    a = [1,2,3,4,5,6]
    sum=0
    a.each do |x|
        sum+=x
    end
