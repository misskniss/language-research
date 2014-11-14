C# was created by Microsoft in 1999. Originally, the team called 
the language "Cool" , which stood for "C-like Object Oriented 
Language" but the name was changed to C# for copyright reasons 
(Wikipedia). C# has received criticism for its similarity
to Java, though it was originally based on C and C++.

C# is known for its object-oriented nature and rapid prototyping
of graphical applications. It is a compiled, high-level language.
It uses static scoping. It is strongly typed. In C#, functions 
are first-class objects. 

In C#, recursion is performed the same as how you would in Java.
Ex: 
	static int factorial(int x){
		if ( x == 0 ){
			return 1;
		}
		else return x*factorial(x-1);
	}

In C#, arrays are similar to Java, however, in declaration the 
square brackets come after the type, not the variable. 
Ex: 
	int[] array; //not: int array[];
	array = new int[10];
Multidimensional arrays are declared with comma-separation
Ex:
	int[,] array; //declares a 2d array;
	int[,,] table; //declares a 3d array;
	array = new int[2,4];
	table = new int[5,2,3];
Jagged arrays are declared as arrays of arrays.
Ex:
	int[][] array;
	array = new int[5][];
	for (int i = 0; i < 5; i++){
		array[i] = new int[i];
	}//Creates an array of int arrays, where each array has 
	//a different size
