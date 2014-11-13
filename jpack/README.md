#Haskell
Haskell is a standardized, general-purpose, purely functional programming language. Among its notable features are lazy evaluation, pattern matching, list comprehension, type classes, and type polymorphism. Haskell was developed in 1987 to explore and develop functional programming languages.

###Why use it?
- Substantially increased programmer productivity.
- Shorter, clearer, more maintainable code.
- Fewer errors, higher reliablilty.
- Shorter lead times.
- A smaller "semantic gap" between the programmer and the language.

> "Haskell isn't for everyone. But everyone should give it a try."

###Scope rules
Haskell uses lexical scoping. Top level functions are available globally. Arguments to functions are scoped to that function.

###Typing system 
Haskell is strongly and statically typed, but with a sophisticated type inference system. The result is a language that offers the ease of use of a dynamic typing combined with the safety of static typing. Haskell also supports type classes, which allows for a programmer to define functions and constants that must exist for every type in a class. As an example:

    class Eq a where
        (==) :: a -> a -> Bool
        (/=) :: a -> a -> Bool

This defines the functions '==' and '/=' that must exist for every type that belongs to Eq. A function can then be defined in the following way:

    member :: (Eq a) => a -> [a] -> Bool
    member y [] = False
    member y (x:xs) = (x == y) || member y xs

This restricts a to types belonging to the type class Eq.

###Functions
Functions are the primary form of expression in Haskell. Functions take arguments and return a single result. No side effects are allowed. Functions can also be passed as arguments. The following example shows a simple function:
    
    doubleMe x = x + x 

###Recursion
Recursion in Haskell is as simple as calling a function inside of itself. A classic example of recursion in Haskell is demonstrated by quicksort:

    quicksort :: Ord a => [a] -> [a]
    quicksort []     = []
    quicksort (p:xs) = (quicksort lesser) ++ [p] ++ (quicksort greater)
        where
            lesser  = filter (< p) xs
            greater = filter (>= p) xs

###Arrays
Arrays in Haskell can be represented as a list. Lists are a fundamental tool for solving problems in Haskell, and the language provides many ways of working with them. This example shows how to find the largest element in a list:

    maximum' :: (Ord a) => [a] -> a  
    maximum' [] = error "maximum of empty list"  
    maximum' [x] = x  
    maximum' (x:xs)   
        | x > maxTail = x  
        | otherwise = maxTail  
        where maxTail = maximum' xs  