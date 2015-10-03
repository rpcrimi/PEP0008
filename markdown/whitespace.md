# Whitespace

1. [Introduction](#Introduction)
2. [Operators](#Operators)
3. [Arguments](#Arguments)
4. [Defining Variables](#Defining Variables)
Next [Comments] (https://github.com/rpcrimi/PEP0008/blob/master/markdown/comments.md)

<a id="Introduction"></a>
## Introduction

<a id="Operators"></a>
## Operators
Always surround operators with a space on either side. For example, `==`, `<`, `!=`, `in`, `is`, `+=`, `=`, etc. should always be seperated on either side with a blank space.

Bad:
```
if(foo==bar):
	if(1<3 and 1>0):
		print foo
```

Good:
```
if(foo == bar):
	if(1 < 3 and 1 > 0):
		print foo
```

The "Good" example is much more legible than the "Bad" example. Developers will be able to clearly read both `if` statements as the arguments are seperated by whitespace.

## Priority
If there are multiple nested operators in a statement, it is important to use whitespace where priority is higher.

Lets look at the following example:
```
a = (a + b) * (z - y) / b
```

A small fix makes this statement more legible:
```
a = (a+b) * (z-y) / b
```

<a id="Arguments"></a>
## Arguments
When defining a default argument or keyword argument, there should be no space on either side of the `=` operator.

For example,
```
x = foo(bar, n = 1)
```
should be changed to:
```
x = foo(bar, n=1)
```
This more clearly states that the keyword argument `n` will have the value 1 when passed into `foo`.

<a id="Defining Variables"></a>
## Defining Variables
Many experienced developers encourage the use of aligned `=` operators when setting consecutive variables. 

For example:
```
x              = 1
y              = 2
very_long_name = 3
long_name      = True
```

However, when there lots of variables being defined, this can be very difficult to read. Instead, try to order variable names by length, and include only one space on either side of the `=` operator. 

For example, lets fix the above definitions:
```
x = 1
y = 2
long_name = True
very_long_name = 3
```
This makes reading the setting of variables much more legible as the values of short variables names are not far away from the name of the variable.

## Up Next
[Comments] (https://github.com/rpcrimi/PEP0008/blob/master/markdown/comments.md)





