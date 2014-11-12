Todd Fogdall
CS354-003
November 13, 2014

Language Research Project - Part 2

  - Quick description/history of the language you chose

Dart was designed and implemented by Google engineers to provide a
fast new language that would be familiar to C and Java programmers 
and provide features that would make the design and implementation
of complex web-based applications easier than before. The Dart
VM can be plugged into Chrome to, for all intents and purposes, make
it a fully functioning platform for Dart-based applications. However, 
engineers recognized the importance of being able to compile the 
language to Javascript so that all browsers could run applications 
developed in Dart.

  - What it is good for (why would someone use it?)

Dart is designed to be "easy to write development tools for, well-suited
to modern app development, and capable of high-performance implemen-
tations." (https://www.dartlang.org/support/faq.html#q-why-dart) In 
short, Google believes that it can be a language that will modernize and
improve the development process for modern web applications. This
claim is up for debate, as currently, Dart code compiled to Javascript 
ran at "about 78% of the performance of hand-written Javascript". 
(http://en.wikipedia.org/wiki/Dart_(programming_language)) It is per-
haps worth noting, however, that native Dart code ran faster than
similar Javascript code, but this requires the Dart VM, which can only
be incorporated into the Chrome browser.

    - Is it a scripting language?

Dart can be used to "script" the browser in which it runs, so in that
sense it is a scripting language. However, the SDK ships with a stand-
alonge VM that allows command-line runs of Dart code, so in that sense
it's not. 

    - Compiled?

Dart can be compiled to Javascript, but whether it's run as native Dart
code or as compiled Javascript code, it's interpreted. 

    - Low-level? 

Dart would probably not be considered low-level, given that it is most
often used in web-based applications.

  - An explanation of the scope rules

Dart is lexically scoped, i.e. "scope of variables is determined static-
ally, simply by the layout of the code." (https://www.dartlang.org/dart
-tips/dart-tips-ep-7.html)

  - An explanation of the typing system

Dart's typing system is unorthodox. It is a dynamically typed language,
but there are optional type tags that can be used to statically check
for potential run-time errors.

  - An explanation of how functions can be used

Dart is a truly object-oriented language, so functions are objects that
can be passed as parameters. The language has a special "call()" function
that allows programs to use instances of a class as functions themselves.
By implementing the call() method within a class, one simply calls the 
reference variable of an object and pass parameters directly to it. For 
instance, suppose a developer defines call as "call(int a, String s)" 
inside a class called aFunction{}. Now suppose af is an instance of 
aFunction, x is an int, and y is a String. af(x,y) references the call()
method that was defined in the class. In this way, functions can be passed
dynamically. 

  - A code sample showing how to use recursion

/* Simple program that uses recursion to generate partial sums
 * of the positive integers and the squares of the positive integers.
 */

var intacc = 0;
var sqacc = 0;

void main() {
  var start = 1; // This is the first integer to add.
  var end =4; // This is the last integer to add.
  acc(start, end);
}

acc(var s, var e) {
  if(s==e) {
    print("Partial Sum #" + s.toString() + ":");
    print("Integer Sum: " + (intacc+=s).toString());
    print("Square Sum: " + (sqacc+=(s*s)).toString());
  }
  else {
    print("Partial Sum #" + s.toString() + ":");
    intacc+=s;
    print("Integer Sum: " + intacc.toString());
    sqacc+=(s*s);
    print("Square Sum: " + sqacc.toString());
    acc(s+1,e);
  }
}

The above program generates the following output on the command line:

Partial Sum #1:
Integer Sum: 1
Square Sum: 1
Partial Sum #2:
Integer Sum: 3
Square Sum: 5
Partial Sum #3:
Integer Sum: 6
Square Sum: 14
Partial Sum #4:
Integer Sum: 10
Square Sum: 30

  - A code sample showing how to use arrays

An array in Dart is a List. The code below shows how a List can
be created and used.

/*
 * Simple program that defines a three-element List called 
 * fruits and then loops over the List, printing elements 
 * one at a time.
 */
void main() {
  var fruits = ["apple", "banana", "coconut"];
  var l = fruits.length;
  
  var i;
  for(i=0;i<l;i++){
    print(fruits[i]);
  }
}

The command line output of the above code is:

apple
banana
coconut
