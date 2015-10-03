# Lay-Out

1. Introduction
2. Imports
3. Indentation
4. Blank Lines
5. Line Length


## Introduction
The lay-out of code describes the physical appearance of lines, code blocks, comments, etc. This includes the spacing and delimeters between these sections. Having a standardized code lay-out will help other developers understand one's code. It will also help in the case of checking in code. Removing unnecessary whitespace and blank lines will lower the amount of "diff noise" when comparing checked in code to previous versions. We will focus on 5 main types of code lay-out in this section

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

As you can probably tell, this would very difficult to parse for another developer reading. For example, the developer cannot tell the difference between standard library imports and local imports. Another problem is the unstructured importing of common libraries. For example, the classes pi and sin are imported two seperate ways on two different lines. Since these classes come from the same library, it would be better to have them grouped together.

Here are a few basic lay-out guidelines when it comes to imports:

- Imports should be on seperate lines unless the imports come from the same package
	- This clarifies which packages contain which classes and seperates conflicting names
- Absolute imports are preferred
	- Instead of `import math.sin ` use `from math import sin `
- Stay away from wildcard imports
	- These types of imports make it unclear what names are in the namespace. Also, for larger packages, this may slow down performance as lots of code must be read into memory.
- Ordering of imports should be in the following order which a blank line inbetween
	- Standard Library
	- Third Party
	- Local/Library Specific
- Imports should be after any module comments and before any globals or constants.
	- This makes it clear that the comments are descibing the usage of the module and that the globals and constants belong to the modules scope.

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

__all__ = ['Cat', 'Dog', 'Fish']

isPet = True
canFly = False
currentPets = []
```

Now, a developer trying to read this code can easily tell what is going on. For example, the developer can tell that `sys`, `os`, `numpy`, and `math` are standard library modules while `nltk` is a third party module and `foo` is a local module. The comments at the top clearly state the usage of the module and the gobals at the bottom are clearly meant to be used within the module.

## Indentation

Indentation is one of the most important aspects of Python code lay-out. Since Python uses tabs as statement delimiters, it is import to maintain structure when defining functions, seperating single lines, etc.

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

This function is very difficult to read. For example, it is very difficult to tell the difference between the function definition and the code within the function. The most important rule when dealing with indentation in Python is to align continuation lines vertically. This will help clearly distinguish code blocks from one another. 

Lets try to fix the function above with this rule:
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
It is now clear to recognize where the definition ends and the functional part starts. Since the function definition adheres to the max line length (see section below) the arguments can be put on the same line. To make the function call to `get_list` more readable, we can vertically align the arguments.  

## Blank Lines


