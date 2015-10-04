# Comments

1. [Introduction](#Introduction)
2. [Commenting Basics](#Commenting Basics)
3. [Block Comments](#Block Comments)
4. [Inline Comments](#Inline Comments)
5. [Important Note](#Important Note)

<a id="Introduction"></a>
## Introduction
Commenting is often the most heated topic among developers. On one extreme, some believe that comments need to be around every statement. On the other extreme, others believe code should be self-describing, needing no comments. In a perfect world, the latter is preferred. In the real word, some level of commenting is always required. That being said, Python code does relatively well as a self-describing language. Many people find it easy to read Python code as it looks similar to psuedocode. Because of this, Python code usually requires less commenting compared to more cryptic languages such as C and Java.

<a id="Commenting Basics"></a>
## Commenting Basics
- Comments should be complete sentences with the first letter capitalized (unless the first word is an identifier)
	```
	# Compute the value of a + b
	x = foo(a, b)
	```
	- Never alter identifier case:
	```
	# initDate is incremented to new value
	initDate += date
	```

- Short comments can omit an ending period (`.`), while longer (paragraph) comments should always include one at the end of each sentence.

	- Does not need period:
	```
	# This comment does not need a period
	```
	- Needs period:
	```
	# These comments need periods as there are multiple sentences. It is 
	# important to separate seperate sentences. I like pizza.
	```

- Always comment in English
	- This will ensure that any developer in the world will be able to understand your code, as English is the common language used by developers worldwide
	- Programming languages themselves are English based, so it only confuses people to see other languages as comments
	- If you are 100% certain your code will never be seen by anyone else, you are free to write comments in the language of your preference. However, remember that this is rarely the case.

<a id="Block Comments"></a>
## Block Comments
- Block comments are comments that appear before a block of code to describe its functionality. 

	- The following is an example of a block comment:
	```
	# A function to compute a^b
	def pow(a, b):
		total = 1
		for i in range(b):
			total *= a
		return total
	```

- Block comments should be indented at the same level of the code it describes.
	- Here is an example of a poorly indented block comment. It is not clear what part of the code the comment refers to:
	```
	def foo(a, b):
	# Add a and b and return square of answer
		c = a + b
		return c * c
	```
	- This version clearly shows that the comment referes to the code that follows it:
	```
	def foo(a, b):
		# Add a and b and return square of answer
		c = a + b
		return c * c
	```

- Multi-Paragraphed comments should include a `#` in-between paragraphs.

<a id="Inline Comments"></a>
## Inline Comments
While block comments can usually describe the behavior of a block of code fairly well, there are occasionally situations in which a statement needs to be clarified individually with an inline comment. Inline comments are comments that appear in the same line as a statement. 

For example:
```
numPets = read(file)["numPets"]   # Initiate num pets to value from file
```

### Inline Comment Guidelines
- Use inline comments sparingly.
	- Not every statement needs an inline comment. For example, the comment used in this case is obvious and adds no value:
	```
	i = i + 1  # Increment x
	```
	- However, the comment below helps the reader better understand the same code's functionality in the context of the application, so it is useful and should be included:
	```
	i = i + 1  # Compensate for border
	```
- Use two spaces between statement and comment. This will help with the distinction between statements and comments.

- Avoid inline comments at the end of statements longer than the max line length (79). Instead include a block comment above the statement.

<a id="Important Note"></a>
## Important Note
"Comments that contradict the code are worse than no comments."

This is a quote every developer should live by. If comments are out of date or do not correctly describe the functionality of code, they will only lessen another developers understanding of your code. While difficult to remember, it is essential to update comments every time a section of code is updated.

## Up Next
[Naming Conventions] (https://github.com/rpcrimi/PEP0008/blob/master/markdown/namingconventions.md)





