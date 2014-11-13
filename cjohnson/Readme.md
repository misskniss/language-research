# Google Dart

##### Dart is a cohesive, scalable platform for building apps that run on the web (where you can use Polymer) or on servers (such as with Google Cloud Platform). Use the Dart language, libraries, and tools to write anything from simple scripts to full-featured apps.
[Dart Homepage]

Dart is not only a programming language but a suite of tools used for developing.  To get started you first need to download Dart from the homepage provided above.  Included in the download will be all of the tools you will need to begin.  Below are just a couple of the tools included in the download.

**1. DartEditor**
  * The DartEditor is based on Eclipse and looks just like the Eclipse IDE too.  When developing your program in the DartEditor you gain access to code completion, debugging, Dart syntax highlighting and building your program with its dependencies to be ready for deployment.  There are also alternative plugins for other IDEs such as IntelliJ, Sublime and Vim but these plugins may not be fully supported and be used at your own risk when choosing not to use the DartEditor.

**2. Chromium**
  * Every web browser may not be able to support running Dart natively and therefore use Darts JavaScript version compiled by the dart2js tool described later.  "Chromium is a special build of the Chromium web browser, called Dartium, that has the Dart VM (virtual machine) embedded. You can run your apps directly in this browser, or use Dart Editor to do it for you, thereby streamlining the build-test cycle." - [quote from dartlang.org](https://www.dartlang.org/docs/tutorials/get-started/)

Google found the JavaScript language to be suitable for web development but seeked a solution for providing what they wish was included or different in JavaScript.  That solution is Dart.  As we have learned with other languages the compiler is typically better at producing better code in that it will save space and improve performance of your application.  The dart2js compiler will provide this for JavaScript while developers use a higher level language (Dart) to better understand and more easily develop their application code.

```javascript
void main() {
  querySelector('#inputName').onInput.listen(updateBadge);
  genButton = querySelector('#generateButton');
  genButton.onClick.listen(generateBadge);

  setBadgeName(getBadgeNameFromStorage());
}

void updateBadge(Event e) {
  String inputName = (e.target as InputElement).value;
  setBadgeName(new PirateName(firstName: inputName));

  if (inputName.trim().isEmpty) {
    genButton..disabled = false
        ..text = 'Aye! Gimme a name!';
  } else {
    genButton..disabled = true
        ..text = 'Arrr! Write yer name!';
  }
}
```

The Dart language brings structure to the existing JavaScript language.  From the code snippet shown above you can see the syntax looks very similar to Java.  You are capable of defining top-level functions, classes, type specific variable including public and private, and creating getters and setters for your class variables.  Using these constructs will help reduce errors introduced into your code as you will be forced to make your code predictable.

Dart cannot replace JavaScript as it is not as widely accepted on all web browsers since they are not all equipped with Dart VM, as Dartium is.  Google's solution to this is the dart2js (Dart to JavaScript) compiler.  The compiler allows the user to develop their program in the Dart language and deploy their application with both the Dart and compiled JavaScript versions.  There is a script included that detects whether the web browser will support running Dart natively and chooses to either bootstrap the Dart VM or load the compiled JavaScript (*programName*.dart.js).

### Scope

The scope rules of Dart are very similar to Java and also use similar keywords.  A final variable is a variable defined in the file or class that cannot change.  A public variable is is any variable defined within your application that does not start with an underscore.  The public variable has a scope limited to the block that it is defined in, or to the class/file the variable is defined in if it is proceeded by the keyword *static* otherwise the variable is global to your application.

Dart does not use a *private* keyword and instead a variable is defined as private if it begins with an underscore.  The private variable uses the same scope rules as Java.  An example of defining a private variable inside of a user-defined class is shown below.
```javascript
class PirateName {
  String _firstName;
  . . .
}
```
In the example above the *firstName* variable is private to the class *PirateName*.  This variable can then be accessed using setters and getters defined within the class.  The *Get* method is a special function in Dart providing read access to the variable.  A shortened way of writing a getter to return the value of *firstName* is shown below.
```javascript
  String get name =>
      _firstName.isEmpty ? '' : _firstName;
```
In Dart the '=>' is the same as writing out the code block within brackets "{ return expr; }".

### Type System

Dart is defined as a dynamically typed language.  There are its advantages to remaining a dynamic language similar to the reasons why JavaScript was developed as a dynamically typed language.  Dart can also be classified as a dynamically typed language though since it is capable of defining types for its variables.  Rather than everything being defined as a *var*, Dart does support types such as numbers, strings and booleans.  Dart leans on being dynamically typed by assuming that the code is valid unless it can be certain that it is statically not correct.

### How to use functions

![alt text](https://www.dartlang.org/docs/tutorials/get-started/images/signature-parts.png "Logo Title Text 1")

The above image, taken from [Dart Homepage], shows the structure of defining a function.  To define a function in Dart is very similar to the same syntax as Java but there are some additional features to using functions.  Dart includes the ability for named parameters.  This might be familiar to anyone who has developed in Objective-C, but it allows the callee to define the parameters passed to a function by their name.
```javascript
PirateName name = new PirateName(firstName: inputName);
```
In the above example a new instance of the *PirateName* class is being created using the constructor and keyword *new*.  Another feature of defining functions in Dart are the ability to define optional parameters in the function definition.  The code below is the constructor defined for the *PirateName*.
```javascript
  PirateName({String firstName, String appellation}) {
    if (firstName != null) {
      _firstName = firstName;
    }
    if (appellation != null) {
      _appellation = appellation;
    }
  }
```
Something that might look unique to Dart is the brackets, { and }, in the parameters.  These are used to define the parameter as optional for the function.  The constructor is also able to check if the parameter is equal to *null* since all variables, including numbers are initialized to *null* if not defined.

### Recursion

Dart does support recursion and a popular example is the Fibonacci numbers.  The code below defines a function called *fibonacci* that uses the condensed version of "{ return *expr*; }".  The function will return *n* if the number is less than two, otherwise it will calculate *fibonacci(n - 1) + fibonacci(n - 2);*.
```javascript
int fibonacci(int n) =>
      (n < 2) ? n : fibonacci(n - 1) + fibonacci(n - 2);
```

### Arrays
In the code snippet below there is an example of an array created in the class *PirateName*.  This array is a class-level object that cannot be changed, as defined by the *static* *final*.  In Dart arrays are called a *List* and are treated the same as an array known in other languages.
```javascript
class PirateName
{
  static final List names = [
    'Anne', 'Mary', 'Jack', 'Morgan', 'Roger',
    'Bill', 'Ragnar', 'Ed', 'John', 'Jane' ];
  . . .
}
```
To get the number of elements in the array you can use the *List* method *length* and to access an element in the array use the [ and ] brackets.
```javascript
String billsName = names[5];
```
The list is a generic type and hold any kind of type, but if you wanted to define a list to hold only a specific type you can define the list as follows.
```javascript
List<String> names;
```
Additional information about lists can be found in the List API [here](https://api.dartlang.org/apidocs/channels/stable/dartdoc-viewer/dart:core.List).

[Dart Homepage]:https://www.dartlang.org/
