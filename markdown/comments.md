# Comments

## Introduction
Commenting is usually the most heated topic when it comes to developers. On one extreme, some believe that comments need to be around every statement while on the other extreme some believe code should be self-describing, needing no comments. In a perfect world, the latter would be prefered. In the real word, there is some level of commenting that needs to take place. That being said, Python code does fairly well as a self-describing language. Many people find it easy to read Python code as it looks similar to psuedocode. Because of this, Python needs a lot less comments to describe code compared to languages like C and Java.

## Commenting Basics

- Comments should be complete sentences with the first letter capitalized (unless the first word is an identifier)
	```
	# Computes the value of a + b
	def foo(a + b)
	```
	- Never alter identifier case:
	```
	# initDate is incremented to new value
	initDate += date
	```

- Short comments can ommit an ending `.`, while longer (paragraph) comments should always include a `.` at the end of each sentence.

	- For example:
	```
	# This comment does not need a period
	```
	- while:
	```
	# These comments need periods as there are multiple sentences. It is 
	# important to seperate seperate sentences. I like pizza.
	```

- Always comment in English
	- This will ensure that anyone will be able to understand your code
	- Programming languages have an English influence so it will only confuse people to see other languages as comments
	- Of course, if are positive that your code will never be seen by anyone else, you are free to write comments the language of preference.

## Block Comments
- Block comments are comments that appear before a block of code. They should be used to describe the block of code following. 

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
	- The following is an example of a "Bad" block comment:
	```
	def foo(a, b):
	# Add a and b and return square of answer
		c = a + b
		return c * c
	```
	- This should be changed to the following:
	```
	def foo(a, b):
		# Add a and b and return square of answer
		c = a + b
		return c * c
	```

- Multi-Paragraphed comments should include a `#` inbetween paragraphs.


## Inline Comments
- Inline comments are comments that appear in the same line as a statement. 
	- The following is an example of an inline comment:
	```
	numPets = read(file)["numPets"]   # Initiate num pets to value from file
	```
- Inline comments are key for describing confusing code statements. While block comments can usually describe the behavior of a block of code fairly well, there are some individual statements that are too confusing and need to be commented. 

- When using inline comments, try to follow the following guidelines:
	- Use inline comments sparingly
		- Not every statement needs an inline comment.
			- The following does not need the inline comment:
			```
			i = i + 1  # Increment x
			```
			- The following statement should include the inline comment:
			```
			i = i + 1  # Compensate for border
			```
	- Use two spaces between statement and comment. This will help with the distinction between statements and comments.

## Important Note
"Comments that contradict the code are worse than no comments."

This should be a quote every developer should live by. If comments are out of date or do not correctly describe the functionality of code, they will only lessen another developers understanding of your code. While difficult to remember, it is essential to update comments every time a section of code is updated.





