# Lay-Out

1. Introduction
2. Imports
3. Tabs and Spaces
4. Indentation
5. Blank Lines
6. Line Length 

## Introduction
The lay-out of code describes the physical appearance of lines, code blocks, comments, etc. This includes the spacing and delimeters between these sections. Having a standardized code lay-out will help other developers understand one's code. It will also help in the case of checking in code. Removing unnecessary whitespace and blank lines will lower the amount of "diff noise" when comparing checked in code to previous versions. We will focus on 5 main types of code lay-out in this section

## Imports

Lets look at the following "header" of a python script:

`__all__ = ['Cat', 'Dog', 'Fish']
 from foo import bar
 from math import pi
 from math import sin

 import numpy
 from nltk import *

 # Class Pet
 # This class does absolutely nothing
 # ...and the header is hard to read
`