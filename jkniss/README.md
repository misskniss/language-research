MicroPython
===========
- [Official Site](http://micropython.org/ "MicroPython Official Site")
- [MicroPython Git Hub](https://github.com/micropython/micropython "MicroPython Git Hub")

Description
-----------

"A lean and fast implementation of the Python 3 programming language that is
optimised to run on a microcontroller."
- [PyBoard Git Hub](https://github.com/micropython/pyboard "PyBoard @ Git Hub")

Micro Python is open source.

Micro Python includes:
- Parser
- Compiler (code is compressed into byte code and runs ont he built-n VM)
- Virtual Machine
- Runtime System
- Garbage Collector
- Full implmentation of the Python 3 grammar
- Subset of the Python 3 standard libraries
- Support ofr  32-bit ARM processors (Thumb v2 instruction set)
- Supports in-line assembly
- File and command-line code execution
- Mark and sweep garbage collection (alternatively, many functions can be
written to not require heap memory allocation)

What It's Good For
------------------

Micro Python allows microcontroller projects to be written in an interpretted
language that were, until recently, written in C or the core's native assembly
then compiled and flashed to the hardware.

With Micropython, code can be written, loaded to the board (which is seen as a
USB drive) and run without the overhead of traditional compilation and flashing. 
Micro Python can also be written and executed interactively in the embedded
interpreter. This is a huge advantage when developers want to get something
running on a development board quickly and easily while providing all the
advantages of object oriented design.

While ultimately a compiled language, python has the advantage of beind an
interpreted language.

- [Micro Python Tutorials](http://docs.micropython.org/en/latest/tutorial/index.html)

The Micro Python Board was developed for Micro Python.
[Board specs:](http://docs.micropython.org/en/latest/hardware/index.html#datasheets-for-the-components-on-the-pyboard)

- Based ont he STM32F405 Microcontroller
- 168MHz clock
- 1 MB Flash
- 192 KB RAM
- Presents itself as a USB device
- Screen (or similar serial comm program) can be used to program the board and
acts as stdin/stdout
- Micro SD slot (storage)
- 4 LEDs
- 2 Switches (reset and gneral purpose)
- Real-time clock
- Accelerometer
- 30 General I/O pins
- 5 USARTs
- 2 SPIs
- 2 I2C busses
- 14 ADC pins
- 2 DAC pins
- 4 Servo ports
- etc



Brief History
-------------
Micro Python was created by Damien George in 2013 and released as a Kickstarter
Project that was fully funded (and then some) and completed in December of 2013.

Micro Python was developed to minimize RAM usage. RAM being a primary
constraint in development for a Microcontroller. Typical RAM available is
192 KB (on the Micro Python Dev board for instance). This is in stark
constrast to the Gigabytes (or much more) of RAM available in your typical
laptop or other computer system. Because RAM is the general purpose "working"
memory used for storing data and variables created by the running programs,
the space required to implement any programs or to store data needs to be
minimized quite a bit for use with microcontrollers. 

- [Micro Python PyCon UK 2014 Slides](http://micropython.org/static/resources/pyconuk14-mpinternals.pdf "Micro Python PyCon UK 2014")
- [Some differences between CPython & Micro Python](https://github.com/micropython/micropython/wiki/Differences)

Scope Rules
-----------

In brief, the scope rules are the same for Micro Python as Python3.

For example, the following is a Micro Python scope check module and its output:

<pre><code>
f_words = ' global scope '
e_words = ' global scope '
g_words = ' global scope '

def some_func():
    f_words = ' some function scope '

	def enc_func():
		e_words = ' enclosed scope '
		print('enc_func(): f_words: ', f_words)
		print('enc_func(): e_words: ', e_words)
		print('enc_func(): g_words: ', g_words)
	 

	 enc_func()
	 print('some_func(): f_words: ', f_words)
	 print('some_func(): e_words: ', e_words)
	 print('some_func(): g_words: ', g_words)


 some_func()
 print('main: f_words: ', f_words)
 print('main: e_words: ', e_words)
 print('main: g_words: ', g_words)

</code></pre>


<pre><code>
enc_func(): f_words:   some function scope 
enc_func(): e_words:   enclosed scope 
enc_func(): g_words:   global scope 
some_func(): f_words:   some function scope 
some_func(): e_words:   global scope 
some_func(): g_words:   global scope 
main: f_words:   global scope 
main: e_words:   global scope 
main: g_words:   global scope 

</code></pre>

The scope heirarchy for searching python namespaces for a name is:

Local -> Enclosed -> Global -> Built-in

Typing
------

Python is both dynamically and strongly typed. 

- The interpreter tracks what type variables refer to (strong typing).
- Values assigned to variables have a type, but a variable itself does not have
to be declared as a particular type before assigning a value to it. (dynamic
typing)

```
micro = "small"		<-- variable micro refers to type string 
python = "python"   <-- variable python refers to type string
python = 3			<-- now, variable python refers to an integer

ver = micro + python	<--TypeError: cannot concatenate 'str' and 'int' objects
```

Strong typing is seen when the interpreter complains about trying to
concatenate values of different types. The interpreter is tracking what type
each variable refers to *currently*.

Dynamic typing can be seen by the lack of type declaration on the creation and
assignment/re-assignment of the variables 'micro' and 'python'. 

Also, every object in python has a type. 


Functions
---------

In the following simple example, variables are assigned to LED objects on
the Micro Python board using the pyb library calls for the LEDs. A function
called 'leds_on' is created to turn on all the LEDs previosly defined. Finally
the function is called with ```leds_on()```

<pre><code>

import pyb
    		
	one = pyb.LED(1)
	two = pyb.LED(2)
	three = pyb.LED(3)
	four = pyb.LED(4)

	def leds_on():
		one.on()
		two.on() 
		three.on()
		four.on()

	leds_on()

</code></pre>


Recursion Example(s)
-------------------

In general, recursion is possible but should be avoided where possible with
Micro Python. Recursion is an expensive feature as each iteration needs to
save state (memory for which is allocated in RAM). 

Arrays Example(s)
-----------------

Single Dimensional Arrays

```
single_dem = [1,'a',2.2,"three"]
print(single_dem[0])
print(single_dem[3])

> 1
> three

```

Multi-dimensional Arrays

```
multi_dem = [['a','c','b'],[1,2,3]]
print(multi_dem[0][0])
print(multi_dem[0][1])
print(multi_dem[0][2])
print(multi_dem[1][0])
print(multi_dem[1][1])
print(multi_dem[1][2])

> a
> b
> c
> 1
> 2
> 3
```

Language Implementation Details 
===================================

General Implementation
----------------------

Micro Python was written in ANSI C and compiled with gcc. The C API allows the
developer to use C functions in their Python code and vice versa. See details
discussed by Damien George on the [Micro Python Kickstater Page](https://www.kickstarter.com/projects/214379695/micro-python-python-for-microcontrollers/posts/679050).

[Full Micro Python Grammar](http://micropython.org/ks/grammar.html)

Lexer and Parser Details
------------------------

"As for RAM usage in the parser, I have tried to minimise this as well. The
parse nodes are 32-bit words, and use the least significant bit to indicate
a leaf node (LSB is set) or a composite node (LSB is clear). Small integers
and pure tokens (brackets, colon, operators, etc) are stored directly in the
leaf. Large integers, decimals and string constants are stored in the leaf as
pointers to this data. Otherwise, a composite node is a pointer to a structure
containing the type of the node and its children (which could be leaves or more
composite nodes).

The main function that parses the Python code is non-recursive, and instead
maintains a stack of rules that it is currently trying to match, as well as a
stack of results (parse nodes) that it has already matched. The size of the
final parse tree is proportional to the amount of Python code in the source
file.

Keeping the lexer and parser small goes a long way to making Micro Python
compact enough to fit on a microcontroller. " - [Damien George: Micro Python Creator](https://www.kickstarter.com/projects/214379695/micro-python-python-for-microcontrollers/posts/669549)

Example of CPython's expensive integers that Micro Python optimizes for...
--------------------------------------------------------------------------
Say you create an integer in Python3 (a.k.a CPython) and name it "a":

a=1

What regular python *really* does is check if the value you are assigning is in
the range -5 to 256. If so, it says "this is a small integer" so it actually
pre-allocates a whole array of integer objects from -5 to 256, sets a pointer
to the one you asked for in the array and calls it "a". So that means the
call to create this one integer has actually allocated 257 integers + 5 (for
tracking) which is 262 integers in total. 

Each integer in this case is 16bytes. So when you allocate a single integer you
are really fetching 262 * 16 bytes of memory, or 4KB of RAM. When you have a
small system like a microcontroller with 192KB of RAM, that is a
pretty expensive piece of data.

Because the variable is program data (and presumably not a const) it gets
allocated in RAM. So...you have a bit of a problem with running languages like
CPython on a embedded system when it comes to the primary way these languages
use memory. 

RAM is something we usually don't worry about all that much in our
laptops or desktops (which often have gigs and gigs of RAM) but, as mentioned
above, a microcontroller's number one constraint is RAM.

