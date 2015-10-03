# Whitespace

- Always surround operators with a space on either side
	- For example `==`, `<`, `!=`, `in`, `is`, `+=`, `=`, etc. should always be seperated on either side with a blank space

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