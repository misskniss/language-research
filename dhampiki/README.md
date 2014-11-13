Introducing Clojure
Daniel Hampikian


History: 
Clojure is a powerful general purpose dynamic programming language that was developed by Rich Hickey, over the course of 2.5 years, where Rich worked exclusively on developing the program.  Clojure is a modern Lisp for functional programing that was symbiotic with the established Java libraries and designed for concurrency, simplicity, and expressive power.  It 

Advantages: 
Clojure is a high-level functional language that keeps data structures immutable, and most functions free from side effects.  This feature makes it easier to write correct programs and to compose large programs from smaller ones.  Clojure simplifies concurrent programing by providing alternatives to locking such as software transactional memory, agents, atoms, and dynamic variables.  Clojure and Java are symbiotic, both can use each others' libraries and calling Java from Clojure is fast and direct.  It takes advantage of the optimizations possible on modern JVMs.  Clojure has the power inherent of Lisp without being constrained by its history.  Clojure is designed in a clean and careful way that allows you to write elegant solutions without that get right to the heart of a problem.    

Scope Rules: 
When you define an object in Clojure it is stored as a var with dynamic scope binding.  By default, Vars are static, but per-thread bindings for Vars defined with metadata can make them able to be dynamically rebound on a per-thread basis and are bound to names, but this is not the only kind of binding used in Clojure.  A functions parameter bindings have lexical scope and so are only visible inside the text of the function body.  

Typing System: 
Clojure is dynamically typed, which is unusual for a functional language.  Every value has a type and the program can know that type at runtime, and so in this sense it is really the limit of a dynamic type system: it presents types at runtime and then defers to the program.  While it inherits runtime types from Java, the semantic of evaluation are independent of the type system.  

Function Usuage: 
A function call in Clojure is a list whose first element resolves to a function.  For example, the list:

(str “mashed” “together” “words”) 

is a call to str that concatenates the arguments to create a string:

“mashedtogetherwords”.  

To define your own function, use defn in Lisp-like fashion (prefix form and surrounding every expression with parentheses) as follows:

(defn average [& nums]
    ( / 	(reduce + nums)
        (count nums)))

Where the function name is average, & and nums are arguments for the function, and & is parameter that can take many different arguments because it has variable arity (without & Clojure functions enforce their arity or expected number of arguments).  The function reduce is being called, and + is a name of another function that we're passing into the reduce function along with nums.  The reduce function is then going to use the plus function to reduce over some number of numbers by calling plus on each pair until it reaches the sum.  Then it will divide that by the count.  So you read the function from the innermost function out: reduce will happen with + and nums, then / will happen with count and nums, then the overall list will reduce to the first parameter the function average.  There are no type declarations because it is a dynamically typed language, whatever you call this function with it will return the same kind of value.  

Examples of Recursion:

Two Fibonacci Programs, one that is stack-consuming recursion and one that is tail-end recursion (from Halloway and Bedra, Programming Clojure Second Edition The Pragmatic Programmers 2012):

(defn stack-consuming-fibo [n]
    (cond
    (= n 0) 0
        (= n  1) 1
            :else  ( + (stack-consuming-fibo (- n 1))
                (stack-consuming-fibo (- n 2)))))

And the tail-recursion fuction (where the recursion happens at an expression that is the return value fo the function)

(defn tail-fibo [n]
    (letfn [(fib
        [current next n]
            (if (zero? n)
                current
            (fib next (+ current next) (dec n))))]
            (fib 0N 1N n)))

Example of Array: 
(from Halloway and Bedra, Programming Clojure Second Edition The Pragmatic Programmers 2012):


Because Clojure collections cannot function as Java Arrays or vice versa, Clojure provides a make-array to create Java arrays.  For example:

(make-array String S)

Which can then be wrapped as a Clojure sequence so that the individual array elements can be printed:

(seq (make-array String 5)) 

Will output: (nil nil nil nil nil)



