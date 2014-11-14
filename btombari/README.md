1)Scala is a language which uses the JVM to compile. It is an object oriented program similar in structure to Java. In addition it is a fully functional programming language with strong static types. It was designed by Martin Odersky around 2003.

2)Scala is an object oriented, compiled, and functional language. It contains many functional language features which can be found in languages like scheme or haskell. It contains other features not found in Java such as operator overloading and named parameters.

3)In scala you can limit the scope of varaible to a code block. Also like in Java, you can limit the scope of variables using modifiers like public or private. In scala all variables default to public. 

4) Scala is statically typed.

5) Functions act just like functions in Java or C type languages.

6/7) 

object Recursion {
   def main(args: Array[String]) {
      for (i <- 1 to 10)
         println( "Factorial of " + i + ": = " + factorial(i) )
   }
   
   def factorial(n: BigInt): BigInt = {  
      if (n <= 1)
         1  
      else    
      n * factorial(n - 1)
   }
}
