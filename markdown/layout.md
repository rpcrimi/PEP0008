# Lay-Out

1. [Introduction](#Introduction)
2. [Imports](#Imports)
3. [Indentation](#Indentation)
4. [Blank Lines](#Blank Lines)
5. [Line Length](#Line Length)

<a id="Introduction"></a>
## Introduction
The lay-out of code describes the physical appearance of lines, code blocks, comments, and spacing and delimeters between sections of code. Having a standardized code lay-out will help other developers understand one's code. It will also help in the case of checking in code. Removing unnecessary whitespace and blank lines will lower the amount of "diff noise" when comparing checked in code to previous versions. We will focus on 5 main types of code lay-out in this section

<a id="Imports"></a>
## Imports
Lets look at the following "header" of a python script:

```
__all__ = ['Cat', 'Dog', 'Fish', 'Bird']
from foo import bar
from math import pi
import sys, os
import numpy
from nltk import *
import math.sin

isPet = True
canFly = False
currentPets = []
# Class Pet
# This class does absolutely nothing
# ...and the header is hard to read
```

The style used may be very difficult to parse for another developer. It shows no clear difference between standard library imports and local imports. It also has unstructured importing of common libraries. For example, the classes `pi` and `sin` are imported two seperate ways on two different lines. Since these classes come from the same library, it would be better to have them grouped together.

Here are several basic lay-out guidelines for imports:

- Imports should be on separate lines unless the imports come from the same package
	- This clarifies which classes each package contains and also separates conflicting names
- Absolute imports are preferred.
	- For example, instead of `import math.sin ` use `from math import sin `
- Stay away from wildcard imports.
	- These types of imports make it unclear as to the classes in the namespace. Also, for larger packages, this may slow down performance as more code than necessary must be read into memory.
- Ordering of imports should be in the following order, separated by a blank line
	- Standard Library
	- Third Party
	- Local/Library Specific
- Imports should occur after any module comments and before any globals or constants.
	- This makes it clear that the comments are describing the usage of the module and that the globals and constants belong to the modules scope.

Lets fix the messy code to adhere to these guidelines:
```
# Class Pet
# This class does absolutely nothing
# ...but the header is easy to read

import sys
import os
import numpy
from math import pi,sin

from nltk import brown

from foo import bar

__all__ = ['Cat', 'Dog', 'Fish', 'Bird']

isPet = True
canFly = False
currentPets = []
```

Now, a developer trying to read this code can easily tell what is going on. For example, the developer can tell that `sys`, `os`, `numpy`, and `math` are standard library modules while `nltk` is a third party module and `foo` is a local module. The comments at the top clearly state the usage of the module and the globals at the bottom are clearly meant to be used within the module.

<a id="Indentation"></a>
## Indentation

Indentation is one of the most important aspects of Python code lay-out. Since Python uses tabs as statement delimiters, it is import to maintain structure when defining functions and separating lines.

Lets take the following function as an example:
```
def add_4_nums_n_times(n, 
	num1, num2, num3, num4):
	l = get_list(num1, num2,
	  num3, num4)
	sum = 0
	for i in range(n):
		for el in l:
			sum += el
	return sum
```

This function is very difficult to read. It is very difficult to tell the difference between the function definition from the code within the function. Aligning continuation lines vertically solves this problem, clearly distinguishing code blocks from one another. 

Lets fix the function above with this rule:
```
def add_4_nums_n_times(n, num1, num2, num3, num4):
	l = get_list(
		num1, num2,
	  	num3, num4
	  	)
	sum = 0
	for i in range(n):
		for el in l:
			sum += el
	return sum
```
It is now clear to recognize where the definition ends and the functional part starts. Since the function definition adheres to the max line length (see section below) the arguments can be put on the same line. To make the function call to `get_list` more readable, we vertically align the arguments.  

<a id="Blank Lines"></a>
## Blank Lines
Lets take a look at the following class:
```
# A class that does basically nothing
class Foo():
	def init(x, y):
		self.x = x
		self.y = y
	# A method that messes with arguments a and b for a while
	def bar(a, b):	
		total = 0
		while(total < 100):
			total += a*b
		return total
	# A method that returns a^2
	def square(a):
		return a*a
	# A method that raises a to the power b
	def pow(a, b):
		total = 1
		for i in range(b):
			total *= a
		return total
```
There is no spacing between functions or comments. Also, the code inside each function has no spacing between code segments, making distinguishing between them difficult. To facilitate readability, it is important to put a blank line between consecutive functions and classes. It is also important to leave blank lines between different sections of an algorithm.

Lets fix the class above to follow these rules:
```
# A class that does basically nothing
class Foo():

	def init(x, y):
		self.x = x
		self.y = y

	# A method that messes with arguments a and b for a while
	def bar(a, b):	
		total = 0

		while(total < 100):
			total += a*b

		return total

	# A method that returns a^2
	def square(a):
		return a*a

	# A method that raises a to the power b
	def pow(a, b):
		total = 1

		for i in range(b):
			total *= a

		return total
``` 
This class is much easier for developers to read. The spacing between functions clearly separates their functionality. While blank lines should be used, multiple blank lines should be used sparingly. For example, a developer may think putting multiple blank lines between statements improves readability. However, it actually makes the code more illegible. The reader may assume that the large separation between code segments means that the segments do functionally different things. Thus, it is recommended to only use one blank line between code segments. Save multiple blank lines for delineating truly separate function entities.

<a id="Line Length"></a>
## Line Length
There are times when a single line of code can stretch beyond the width of the screen, which is inconvenient for the reader. In these cases, it is important to break up the line into multiple structured lines. It is recommended to limit lines to 79 characters, the standard width of most IDE's. This helps when code must be transferred between machines. It ensures that any developer will be able to view an entire line of code on any screen.


## Up Next
[Whitespace] (https://github.com/rpcrimi/PEP0008/blob/master/markdown/whitespace.md)