# Naming Conventions

1. [Introduction](#Introduction)
2. [Prescriptive](#Prescriptive)
3. [Descriptive](#Descriptive)
4. [Other Notes](#Other Notes)

<a id="Introduction"></a>
## Introduction
Naming conventions is another critical part of a development teams coding style. Naming conventions will help readers distinguish between different data structures and layers of code. For example, functions should have a different naming convention than variables so that a reader can clearly tell the difference when reading the code. There are two styles of naming conventions we will discuss here: Descriptive and Prescriptive.

<a id="Prescriptive"></a>
## Prescriptive
Prescriptive naming conventions are ones that describe how a data structure should be named. You can think of prescriptive naming conventions as "names to avoid". For example, most style guides tend to steer developers away from using `I` (uppercase eye), `O` (uppercase oh), and `l` (lowercase el) as names to data structures as they look very similar to `0` (zero) and `1` (one). 

Most prescriptive naming conventions are set by the development team. For example, a team may decide to include a leading term to every method in a module. This will allow users to easily determine the name of a method. 

For example, lets say a team is writing a module to handle strings. The team may decide to add a leading `str_` to all method names in the module.

This would look as so:
```
Class StringHandler():
	def __init__(self):
		return

	def str_get(self):
		return self.s

	def str_update(self, s):
		self.s = s

	def str_format(self, s, type):
		return format(s, type)
```
If a developer would like to use this module, he will soon find out that all methods that work with a string have the leading `str_`. Now the developer can basically guess the name of functions.

While prescriptive naming conventions are usually left up to the team, it is essential to stick to the determined conventions. For example, the team may decide to stay away from all single letter names (`i`, `x`, `y`). While this may be difficult for developers used to using these names, it is important to stick to the teams convetions.

<a id="Descriptive"></a>
## Descriptive
Descriptive naming conventions are the way in which developers structure a name. This includes character case, name length, underscores, etc.

Here are a few descriptive naming conventions and their typical use:
- Single lowercase letter
	- ex. `i`, `x`, `y`
	- Used for:
		- Iterators (ex. `for i in range(10)`)
		- Variables that correspond to the letter (ex `(x, y)` point)
- Lowercase word
	- ex. `start`, `time`, `length`
	- Used for: 
		- Basic variable names that need little description
		- Module names (can include underscore if long)
		- Package names
- Lowercase words with underscores
	- ex. `start_counter`, `format_string`, `can_fly()`, `_private_var`
	- Used for:
		- Function names
			- ex. `format_string_to_int(s)` is easier to read than `formatStringToInt(s)`
		- Global variables (to the module)
		- Longer module names
		- Longer package names
	- Use leading underscore for non-public methods and instance variables
		- ex. `Cat._increase_size()`, `Dog._private_var`
- Uppercase word
	- ex. `MAX_BUFFER_SIZE`, `TOTAL`
	- Used for:
		- Constants
- Capitalized words
	- ex. `Cat`, `CanFly`, `FastCar`
	- Used for:
		- Class names
		- Exceptions
- Mixed case words
	- ex. `canFly`, `timeLeft`
	- Should not be used unless their is a prevailing style.
		- For example, the development team has written thousands of lines of code using mixed case variables
	- Used for:
		- Longer variable names
		- Longer function names

<a id="Other Notes"></a>
## Other Notes
- Public attributes should never include a leading underscore as this is the convention for non-public attributes. If a public attribute interferes with a reserved word, use a trailing underscore. For example, `min_size` should be changed to `min_size_`.

- Always use `self` as the first argument to an instance method.

Bad: 
```
Class Cat(Pet):
	def __init__(self):
		return

	def change_type(t, self):
		self.type = t

	def add_sizes(size1, size2, self):
		self.size = size1 + size2
```
Good:
```
Class Cat(Pet):
	def __init__(self):
		return

	def change_type(self, t):
		self.type = t

	def add_sizes(self, size1, size2):
		self.size = size1 + size2
```
- It is best not to abbreviate words to make shorter names. This is usually done when a name conflicts with a reserved keyword. For example, 'pet_type' shortened to `pet_typ`. This will confuse readers as to which of the terms they are looking at. Instead, use a trailing underscore (`pet_type_`). This will let a reader know that they are looking at a local version of the name rather than the keyword.


