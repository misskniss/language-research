

# Go #

 Melissa Clausen 



##	Description and History ##

This language, created in 2007, was originally developed at Google by Robert Griesmer, Rob Pike, and Ken Thompson. 
According to Ken Thompson this language initially just an experimental project. 
The language is loosely based on C but includes garbage collecting and type safety as well 
as some other added features. It has been used by Google for some programs created therein. 
 This programming language was built essentially to provide a new language that was not as clunky 
 as Java and C++. There aim was to create a new concurrent, garbage-collected language with fast 
 compilation. 
 
## What is Go good for? ##

This programming language was created out of frustrations with different systems programming languages. Go is being used internally with many programs inside Google. The server behind golang.org uses Go. It is also used in Google’s downlowd server dl.google.com. This language has some dynamic-typing capabilities. Interestingly, since it was derived from C you can link C program files with Go files. This language attempted to combine dynamically typed language with statically typed compiled language.

## Scope Rules##
Go is lexically scoped using blocks.

According to golang.org:

The scope of a predeclared identifier is the universe block.

The scope of an identifier denoting a constant, type, variable, or function (but not method) declared at top level (outside any function) is the package block.

The scope of the package name of an imported package is the file block of the file containing the import declaration.

The scope of an identifier denoting a method receiver, function parameter, or result variable is the function body.

The scope of a constant or variable identifier declared inside a function begins at the end of the ConstSpec or VarSpec (ShortVarDecl for short variable declarations) and ends at the end of the innermost containing block.

The scope of a type identifier declared inside a function begins at the identifier in the TypeSpec and ends at the end of the innermost containing block.


## Typing System ##
The language Go attempts to combat the cumbersome type systems of Java and C++.

Go's type system has no hierarchy, so no time is spent defining the relationships 
between types. Also, although Go has static types the language attempts to make types 
feel lighter weight than in typical OO languages.
## Functions ##
Go allows first class functions, higher-order functions, user-defined function types, function literals, closures, and multiple return values. Therefore, it can be used quite well as a functional programming language.  Because it has the option of multiple return values it improves upon some of the awkwardness of C.
## Recursion Example ##
	package main
	import “fmt”
	func MyRecurssion(value int) int {

   		if value == 0 {
			return value
		}
		
		retune value + MyRecurssion(value-2)
		
	}

	func main() {

  	  fmt.Printf( MyRecurssion(8))
	}

## Array Example##
 	
	var x [2]int
Essentially here you have x which is an array of 2 integers.
Below is an example of how to display the array in go:


	package main
	import “fmt”
	func main(){
		var x [2]int
		x[0] = 2
		x[1]=1
		fmt.Println(x)
	}

What should be displayed from this is:
	[2 1]
