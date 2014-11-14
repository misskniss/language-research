<h1>SWIFT</h1>

<h4>ABOUT:</h4>
<p>Swift is a programming language for the iOS and OS X that builds off of C and Objective C. Development of Swift was started in June 2010 by Chris Lattner and other programmers. Swift also took language ideas from "Rust, Haskell, Ruby, Python, C#, CLU, and far too many others to list" (Lattner's Home Page). </p>

<h4>WHY WOULD YOU USE IT:</h4>
<p> - Easy to use for new programmers </p>
<p> - Expressive like a scripting language </p>
<p> - Designed for safety </p>
<p> - Provides object-oriented features </p>

<h4>TYPE</h4>
<p>Int, Float, Bool, String</p>
<p>var is used for variables, let is used for constants</p>
<pre>var welcomeMessage: String</pre>

<h4>Function</h4>
<p>function with return type int:</p>
<pre>func halfOpenRangeLength(start: Int, end: Int) -> Int {
         return end - start
}</pre>
<p>function with no return type:</p>
<pre>func sayGoodbye(personName: String) {
  println("Goodbye, \(personName)!")
}</pre>

<h4>RECURSION</h4>
<pre>func test(val: Int) {
      println("\(val)")
      if val > 0 {</p>
        test(val - 1)
    }
}
test(3)</pre>

<h4>ARRAY USE</h4>
<pre>var shoppingList: [String] = ["Eggs", "Milk"]
// shoppingList has been initialized with two initial items
var firstItem = shoppingList[0] 
// firstItem is equal to "Eggs" 
shoppingList.append("Flour")
// shoppingList now contains 3 items, and someone is making pancakes
shoppingList += ["Baking Powder"]
// shoppingList now contains 4 items
shoppingList += ["Chocolate Spread", "Cheese", "Butter"]
// shoppingList now contains 7 items</pre>
