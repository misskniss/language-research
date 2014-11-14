#GalaxyScript
Ayrton Stout
<br />
<br />
#History: 
GalaxyScript/Galaxy is a C-like language developed by Blizzard Entertainment to be used in creating complex, unique events in the real-time strategy game, StarCraft 2. Galaxy is a simple, procedural programming language designed purely to improve the capabilities of the StarCraft 2 map design.


#Advantages: 
With a narrow focus on doing only one thing, but doing that one thing very well, Galaxy has a small amount of overhead. Being similar to C, Galaxy has support for functions, structs, typedefs, pointers, as well as loops. However, some things have been changed to make it easier to use for a more average person to be able to pick it up, such as automatic garbage collection. Finally, being an in-house language, Galaxy is built from the ground up to be able to easily interact with the game world. 


#Scope Rules: 
Scope in Galaxy is similar to C. A variable must be declared above the code that will execute it. A variable declared within a function is local to that function. A variable declared outside of a function is considered global. A static global variable makes the variable private to the file it’s located in.


#Typing System: 
Galaxy is a more strongly typed language, though implicit conversions between pointers and ints are still allowed. Unsurprisingly, Galaxy is also statically typed.


#Function Usage: 
Functions can take multiple parameters, and have one return type. Functions that don’t return anything must be declared void. Unlike C, functions cannot be passed via pointers to other functions.


#Examples of Recursion:
Simple cases of recursion are perfectly fine in Galaxy. An example of a recursive factorial function is

```
int factorial(int input)
{
     if (input == 1) {
          return 1;
     }
     return input * factorial(input - 1);
}
```
However, Galaxy suffers from the same problem it did in the past- overflow. Galaxy has to work with a 2MB memory limit for its code and variables. The limit is likely to prevent a game with multiple players from becoming bloated. 


#Example of arrays: 
Arrays are syntactically the same as they are in C. 
```
int[10] someInts;
```
creates an array of 10 ints. Unlike C, these values are assigned default values (usually 0). And like C, individual values are referenced by
```
someInts[1] = 255;
```
Being a zero-indexed based language, the above code accesses the 2nd array slot.

Unlike C arrays, arrays in Galaxy cannot be assigned to other arrays. They also cannot be passed into functions or returned from functions. Multi-dimensional arrays are allowed.
