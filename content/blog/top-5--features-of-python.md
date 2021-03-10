---
title: "5 Python Features That You May Not Be Familiar With"
date: 2020-07-13T12:49:27+06:00
featureImage: images/allpost/allPost-9.jpg
postImage: images/single-blog/feature-image.jpg
---

Python, for all its ease of learning, has some pockets of real complexity. If you’ve ever read through the programming language’s documentation, you’ve probably gotten a sense of that. If you’re new to the language, here are some features you might not be familiar with, but could nonetheless prove useful (or at least fun to experiment with).
## Negative Strides on Slices

Slices are a fairly modern innovation in several computer languages. In Python, we can use them on lists, tuples and strings to get a subset of a particular sequence. You might be familiar with slices in that context… but did you know you can also use them to reverse a sequence? What do you think this code outputs:

```
alphabet = [chr(c) for c in range(ord('a'), ord('z')+1)]  # 'a'..'z'
print(alphabet[::-5])
```

That first line puts the entire alphabet into the alphabet variable. The -5, the third parameter of the slice, is stride, an interval. Because it’s negative, it runs backwards.

```
['z', 'u', 'p', 'k', 'f', 'a']
```

### An Alternative Way to Do Multiple Assignments

You may be familiar with multiple assignments where you assign values to several variables in one statement, like this:

```
a = b =9
print(f'a={a} b= {b}')
```

But you can also do multiple assignments this way:

```
a,b = 5,4
print(f'a={a} b={b}')

This outputs: a=5 b = 4.
```

### Using the Walrus Operator

This was only recently introduced in Python 3.8. In C, it’s not uncommon to assign a value to a variable in ab (an expression). Now, Python has it with the := operator.

(This one I had to test using a repl online, as none of the Python versions I had installed on Windows or Ubuntu were version 3.8.)

```
a= 9
b =-3.4
print(c := a*a+b)
print(c)
```

The output was 77.6 twice, with C being assigned the value 77.6 in the first print statement.
### ‘Else’ Blocks On ‘For’ and ‘While’

This is something that doesn’t happen with other programming languages. I personally find using them confusing and have never used them, but if you want to impress your friends or colleagues….

After a for or while loop you can have an else. The else branch only runs if there was no break in the loop body.

Here’s an example. What do you think it will print out?

```
for i in range(5):
    print(f'loop index={i}')
else:
    print(f'else i={i}')
```

This is the output:

```
loop index=0
loop index=1
loop index=2
loop index=3
loop index=4
else i=4
```

It’s pretty confusing! If we try it this way, code below the else never runs, but it’s just as easy to not use else.

```
for i in range(5):
    print(f'loop index={i}')
    if i==4:
        break;
else:
    print(f'else i={i}')
```

My suggestion: Don’t use it, just be aware of it so you won’t end up scratching your head if you see it used.

Else is useful, though, in a try/except, when comes after the except and lets you handle code if the specified exceptions don’t occur.

In this somewhat contrived example with two user-defined exceptions, the guess function returns exceptions if the value is too small or too large. Only if the value is correct does the else get hit:

```
class Error(Exception):
    """Base class for other exceptions"""
    pass

class ValueTooSmallError(Error):
    """Raised when the input value is too small"""
    pass

class ValueTooLargeError(Error):
    """Raised when the input value is too large"""
    pass

def guess(value):
    if value <5:
        raise ValueTooSmallError
    elif value >15:
        raise ValueTooLargeError
    return value
try:
    answer=guess(5)
except ValueTooSmallError:
    print("Too small")
except ValueTooLargeError:
    print("Too large")
else:
    print("Good guess")
```

### Position ‘Only’ Parameters in Functions

This is another 3.8 feature. When you call a function, you can specify parameters by position or with the name of the parameter. If the parameter list includes a parameter / and _, then whether a parameter is positional only, positional or keyword, or keyword only depends upon where the parameter is relative to / and _. Note both / and _ are optional and _ was already used in Python 3.7.

This diagram is taken from PEP 5470:

```
def f(pos1, pos2, /, pos_or_kwd, *, kwd1, kwd2):
      -----------    ----------     ----------
        |             		|                  	|
        |        Positional or keyword  	|
        |                                - Keyword only
         -- Positional only
```

The various cases are defined in more detailed in the 3.8 documentation on defining functions.
