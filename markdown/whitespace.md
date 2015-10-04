# Whitespace

1. [Introduction](#Introduction)
2. [Operators](#Operators)
3. [Arguments](#Arguments)
4. [Defining Variables](#Defining Variables)

<a id="Introduction"></a>
## Introduction

<a id="Operators"></a>
## Operators
Always surround operators with a space on either side. For example, `==`, `<`, `!=`, `in`, `is`, `+=`, `=`, etc. should always be separated on either side with a blank space.

For example, this code is functional, but hard to read:
```
if(foo==bar):
	if(1<3 and 1>0):
		print foo
```

This is much better:
```
if(foo == bar):
	if(1 < 3 and 1 > 0):
		print foo
```

The conditions of the `if` statement are now easier to read.

## Priority
If there are multiple nested operators in a statement, use whitespace where priority is higher.

For example:
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
This more clearly shows that the keyword argument `n` will have the value 1 when passed into `foo`.

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

However, when many variables are being defined, this technique can make some of them difficult to distinguish. Instead, order variable names by length, and include only one space on either side of the `=` operator. 

For example, lets fix the above definitions:
```
x = 1
y = 2
long_name = True
very_long_name = 3
```
The setting of variables are now much more legible as the values all of the variables are close to their names.

## Up Next
[Comments] (https://github.com/rpcrimi/PEP0008/blob/master/markdown/comments.md)