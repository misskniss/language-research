Swift is a new programming language by Apple to develop applications for iOS and OS X. 
It has been years in the making and was officially unveiled in June of this year, and 
is now officially supported in Xcode so you can build apps from iOS 8 and iPhone 6 and 
6 Plus using swift. I chose this language because I am very fascinated with it and I 
would like to learn how to use it more for app development, so I thought I may as well 
dabble more in it.

Swift is good for many things and one of the best things is that it is friendly to new 
programmers. It is the first industrial-quality systems programming language that is 
as expressive and enjoyable as a scripting language. It supports playgrounds, an 
innovative feature that allows programmers to experiment with Swift code and see the 
results immediately, without the overhead of building and running an app.

Swift uses global scope rules.

The typing system in Swift is interesting because you assign variables in swift like this:
let testNumber = 5
You can omit the type or part of the typr of many of the variables and expressions in your code. 

You declare a function as follows:
func isToTheRightOfX(x: Double) -> Bool
This is declaring isToTheRightOfX as a function that takes a parameter x of type Double 
and returns a boolean value. 

An example of recursion is:
func factorial(n: Int) -> Int {
    return n == 0 ? 1 : n * factorial(n — 1)
}
You can simply call the function within itself. I have read that there is no tail call 
optimisation which makes it risky.

You can make a single dimensional array as follows:
let someArray: [String] = ["Alex", "Brian", "Dave"]
A multidemensional array is possible too:
var array3D: [[[Int]]] = [[[1, 2], [3, 4]], [[5, 6], [7, 8]]]
