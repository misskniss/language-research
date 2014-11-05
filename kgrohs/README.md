Konrad Grohs
===============

Ruby
---

> Ruby is a dynamic, reflective, object-oriented, general-purpose programming language. 
> It was designed and developed in the mid-1990s by Yukihiro "Matz" Matsumoto in Japan.
>
> According to its authors, Ruby was influenced by Perl, Smalltalk, Eiffel, Ada, and Lisp.
> It supports multiple programming paradigms, including functional, object-oriented, and imperative.
> It also has a dynamic type system and automatic memory management.

https://www.ruby-lang.org/en/

---

> Variables in Ruby
> $		A global variable
> @		An instance variable
> [a-z] 	or _	A local variable
> [A-Z]	A constant
> @@		A class variable


Describe language


---
### Code Samples

```php
# arrays in old php
$colors = array("red", "orange", "blue");

# and in new php
$colors = ["red", "orange", "blue"];

# there are also array objects
$obj = new ArrayObject($colors);

# you can loop with for , foreach
for ($i=0; $i<length($colors); $i++) {
  print($colors[i]);
}

# access through indices starting from 0
$colors[0] = "pink";

foreach ($colors as $color) {
  print($color);
}

```

TODO

more code samples


