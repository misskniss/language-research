###Description/History:

Ruby is a dynamic, reflective, object-oriented, general-purpose programming language.  It was developed in the mid 90’s by Yukihiro “Matz” Matsumoto in Japan.  Ruby was influenced by perl, Smalltalk, Eiffel, Ada, and Lisp.  It supports multiple programming paradigms (functional, object-oriented, imperative).  It also has a dynamic type system and automatic memory management



###What is Ruby good for (why would someone use it):

Ruby is a general purpose dynamic language that is frequently used for scripting.  
Also follows OOP
It’s one of the easier languages to learn
It is mostly used for web apps
Ruby can be interpreted or compiled
Ruby is not considered low-level



###Scope Rules:

lexical, sometimes dynamic



###Typing System:

duck typing/dynamic



##How are functions used:

Ruby methods are used to bundle one or more reputable statements into a single unit.  Ruby methods are a set of expressions that return a value.  Methods should be defined before calling them. See below for function examples.

```ruby
def method_name [( [arg [= default]]...[, * arg [, &expr ]])]
   expr..
end
```

```ruby
def method_name 
   expr..
end
```

```ruby
def method_name (var1=value1, var2=value2)
   expr..
end
```



###Code sample of Recursion:

```ruby
def factorial(n)
    if n == 0
        1
    else
        n * factorial(n-1)
    end
end
 
puts factorial(5) # =&gt; 120
```


###Code Sample demonstrating how to use arrays

```ruby
arr = [1, 2, 3, 4, 5, 6]
arr[2]    #=> 3
arr[100]  #=> nil
arr[-3]   #=> 4
arr[2, 3] #=> [3, 4, 5]
arr[1..4] #=> [2, 3, 4, 5]
arr[1..-3] #=> [2, 3, 4]
```