# Naming Conventions

## Introduction
Naming conventions is another critical part of a development teams coding style. Naming conventions will help readers distinguish between different data structures and layers of code. For example, functions should have a different naming convention than variables so that a reader can clearly tell the difference when reading the code. There are two styles of naming conventions we will discuss here: Descriptive and Prescriptive.

# Descriptive
Descriptive naming conventions are the way in which developers structure a name. This includes character case, name length, underscores, etc.

Here are a few descriptive naming conventions and their typical use:
- Single lowercase letter
	- ex. `i`, `x`, `y`
	- Used for:
		- Iterators and variables that correspond to the letter (ex `(x, y)` point)
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
