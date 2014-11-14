Matt Handyside
==============

Python
------

> Python was designed by Guido van Rossum in 1991 as a high-level interpreted 
> language with a large comprehensive standard library, which can accomodate
> multiple programming paradigms such as:

- Object-oriented programming
- Imperative programming
- Functional programming
- Procedural programming

> Python is a strong, dynamically typed language. Which is the proccess of
> verifying the type-safety of a program at run-time.

Python Scopes
-------------

---
### Scop Rules

> If a variable is a assigned inside a 'def,' it is local to that function.

```python
#example of local assignment
def function():
    x = 5+5
# x is only visible inside this function 
```

> If a variable is assigned in an enclosing 'def,' it is non-local to nested 
> functions.

```python
def function1():
    x = 5
    def function2():
 		y = x + 5
    print(x + y)
# x is visible to the entire block.
# y is only visible inside function2.

```

> If a variable is assigned outside of all 'def' is it global to the file.

```python
x = 5
def function1():
    y = x
    def function2():
		z = y + x
     	# will print 10
        print z
    # will print 5
    print y
# is visible through entire program
print x

```

Python Functions
----------------

> Python functions begin with the 'def' keyword, followed by the function name
> and parentheses which can contain a number of parameters.

> The beginning of the function code starts with a ':' after the parentheses.
> Functions in python can also have an optional return statement which can
> return an expression of sorts or nothing at all.

###Syntax

```python

#no return
def functionName( parameters ):
    #function code

#return nothing
def functionName( parameters ):
    #function code
    return

#return an expression
def functionName( parameters ):
    #function code
    return parameters

```

###Basic Function

```python
#ass in a string and print.
def printMe( str ):
    #print str
    print(str)
#call function
printMe( "Me" );

```

###Recursive Function

```python

#primary function
def main():
    #set num to 5
    num = 5
    #set fact to call the factorial function passing in num as a parameter
    fact = factorial(num)
    #print final value of factorial recursion
    print("Factorial of ", num, " is ", fact)

#define factorial function
def factorial(num):
    #num is 0 return 1
    if num == 0:
	   	return 1
    #recurse until it reaches 0
    else:
		return num * factorial(num-1)

main() 

```

###Lambda (anonymous) Functions

> Python also supports an idea from Scheme or Lisp called Lambda(Anonymous) Functions.
> Lambda functions are functions that can take any number of arguments, not within parentheses, and returns the value of a single expression.
> Lambda functions also cannot contain more than one expression.

###Syntax

```python
#assign the return value of lambda to g
g = lambda x: x*2

#reference the function by calling it through g
g(3)
#will print 6

#call lambda function without variable assignment
(lambda x: x*2)(3)
#will print 6

```


Python Lists & Arrays
-----------------------

###Lists

> In python lists are the most veristile data-type available.
> Lists are basically a generic list of comma-seperated values.
> Items in lists do not all have to be the same type.
> Strings, integers or charactrs can all go into the same list.

###Syntax

```python

listName = [value1, value2, valu3,]

```

###Example

```python

#list of numbers
list_1 = [1, 2, 3, 4, 5];

#list of strings
list_2 = ["Me", "You", "Them"];

#list of Integers and Strings
list_3 = ["Me", "You", "Them", 1, 2 ,3];

```

###Accessing Elements

> Accessing elements in a List is done by referencing the index value
> starting at 0.

```python

#list of numbers
numbers = [1, 2, 3, 4 ,5];

#list of names
names = ["Matt", "Bob", "Jerry", "Tom", "Skip"];

#access '3' in numbers by referencing index 2 which is the 3rd element
print numbers[2]

#access "Jerry" in names by referencing index 2 which is the third element
print names[2]

#access a range of values in numbers
#access '2', '3' and '4' by referencing index 1, 2 and 3
print numbers[1:3]

#access a range of values in names
#access "Bob", "Jerry" and "Tom" by referencing index 1, 2 and 3
print names[1:3]

```

###Changing Elements

> Changing list data is fairly straight forward. By referencing the index
> and assigning a value to referenced index.

```python

#list of numbers
numbers = [1, 2, 3, 4, 5];

#access 4th element in numbers
print numbers[3]
#prints 4

#assign '500' as 4th element of numbers
numbers[3] = 500

#access 4th element again
print numbers[3]
#prints 500

```

###Arrays

> Arrays in python are similar to lists; they are a list of comma-seperated 
> elements which can be accessed by referrencing the index of said elements
> starting at 0.

> The one major difference between arrays and lists is arrays are type specific.
> They can only hold one type of elements, like integers, strings or other
> types.

> One other major difference is there is no array type for strings.

> Arrays are initialized to a variables name with the keyword "array", with a
> typecode and initializer. The typcodes for defining the type of array are as follows:

- ‘b’ -> Represents signed integer of size 1 byte
- ‘B’ -> Represents unsigned integer of size 1 byte
- ‘c’ -> Represents character of size 1 byte
- ‘u’ -> Represents unicode character of size 2 bytes
- ‘h’ -> Represents signed integer of size 2 bytes
- ‘H’ -> Represents unsigned integer of size 2 bytes
- ‘i’ -> Represents signed integer of size 2 bytes
- ‘I’ -> Represents unsigned integer of size 2 bytes
- ‘w’ -> Represents unicode character of size 4 bytes
- ‘l’ -> Represents signed integer of size 4 bytes
- ‘L’ -> Represents unsigned integer of size 4 bytes
- ‘f’ -> Represents floating point of size 4 bytes
- ‘d’ -> Represents floating point of size 8 bytes


###Syntax

```python

arrayName = array(typecode, [initializer])

```

###Example

```python

#array of integers from 1 to 5
myArray = array('i', [1, 2, 3, 4, 5])

```
###Accessing Elements

> Accessing elements of an array are exactly the same as lists.
> By referencing the index of the value we want.

```python

#array of ints from 1 to 5
myArray = array('i', [1, 2, 3, 4, 5])

#access the third element, '3'
print myArray[2]

#access the first thrugh fourth elements, '1, 2, 3, 4'
print myArray[0:3]

```

###Changing Elements

> Changin array elements can be done in the same way as lists.
> By referencing the index of the value we want.

```python
#array of integers 1, 2 ,3 ,4 and 5
myArray = array('i', [1, 2 ,3 ,4 ,5])

#access element three, '3'
print myArray[2]

#change element three, '3', to '500'
myArray[2] = 500

#will print 500 instead of 3
print myArray[2]

```
