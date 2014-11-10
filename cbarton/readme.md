#Python

##Description
Python was originally designed in 1991 by Guido van Rossum and continues to be developed 

by the Python Software Foundation. It's a high-level programming language with a design 

philosophy that emphasizes code readability and syntax that allows programmers to express 

concepts in fewer lines of code than Java or C++.

##Uses
As a result of its ease of use, Python tends to be slower than other languages but often 

take much less time to develop. This makes it a good choice for any project where 

runtime isn't a significant factor.

Similar to Java, Python is compiled into bytecode, which is then executed by an 

interpreter. 

##Scope Rules
Like most modern programming languages, Python is statically scoped. There are three levels 

of scope: function, module, and global.

##Typing System
Python is both dynamically and strongly typed. Meaning a variable's type can be changed, 

but the variable can be used in a way that isn't defined for its data type.

##Functions
Function arguments are passed by reference. Unlike most languages, Python functions and 

arguments don't have a declared type so the return statement can return any type or else 

'none'.

##Recursion Example
```sh
def listsum(numList):
   if len(numList) == 1:
        return numList[0]
   else:
        return numList[0] + listsum(numList[1:])

print(listsum([1,3,5,7,9]))
```

##Array Example
####Defining an array
```sh
myList=[1,2,3,4,5,6]
```

####Assigning a single element
```sh
myList[2]=100
```

####Assigning multiple elements
```sh
myList[0:2]=[0,1]
```
