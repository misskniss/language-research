Joey Mazzarelli
===============

PHP
---

> PHP is a popular general-purpose scripting language that is especially
> suited to web development.
> 
> Fast, flexible and pragmatic, PHP powers everything
> from your blog to the most popular websites in the world.

http://www.php.net

---

TODO


It's a dynamically typed interpreted language


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


