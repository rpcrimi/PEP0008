# Comments

## Introduction
Commenting is usually the most heated topic when it comes to developers. On one extreme, some believe that comments need to be around every statement while on the other extreme some believe code should be self-describing, needing no comments. In a perfect world, the latter would be prefered. In the real word, there is some level of commenting that needs to take place. That being said, Python code does fairly well as a self-describing language. Many people find it easy to read Python code as it looks similar to psuedocode. Because of this, Python needs a lot less comments to describe code compared to languages like C and Java.

## Commenting Basics

- Comments should be complete sentences with the first letter capitalized (unless the first word is an identifier)
```
# Computes the value of a + b
def foo(a + b)
```
Never alter identifier case:
```
# initDate is incremented to new value
initDate += date
```

- Short comments can ommit an ending `.`, while longer (paragraph) comments should always include a `.` at the end of each sentence.

For example:
```
# This comment does not need a period
```
while:
```
# These comments need periods as there are multiple sentences. It is 
# important to seperate seperate sentences. I like pizza.
```

- Always comment in English
	- This will ensure that anyone will be able to understand your code
	- Programming languages have an English influence so it will only confuse people to see other languages as comments
	- Of course, if are positive that your code will never be seen by anyone else, you are free to write comments the language of preference.