<head>
    <link rel="stylesheet" href="styles.css">
</head>

<h1 align="center">A Wicked Object-Oriented Python Crash Course For Bootcampers</h1>

If you search for object-oriented programming articles, you're likely to see words like abstraction, encapsulation, inheritance, and polymorphism. You'll probably see a lot of things framed for software engineers, things written in rigid languages like Java, or old examples written in Python 2.

What if, for now, you only want to know enough to be dangerous? What if you're trying to figure something out, and only intend to skim this, because all you want to know is

<h4 align="center">How do I understand enough of this Stack Overflow answer I'm currently reading to implement it in my situation?</h4>

I'll leave the theory and detail to your instructors. Nothing here is going to be useful for your next interview - sorry! And in the name of practicality, let's make sure we're on the same page

```python
from platform import python_version
print(python_version())
```
That reads <c-s>3.7.9</c-s> in the environment I currently have loaded, and <c-s>3.7.10</c-s> in Google Colab.

### What Is The Simplest Class I Might Find Useful?

#### Custom Exceptions
For now, when you see the word <c-s>class</c-s>, think you're about to read the recipe for an object. It's like that object's DNA (clearly, I know nothing about DNA). Some recipes are really short; the shortest classes I write are custom exceptions:

```python
class CurtainError(RuntimeError):
    pass
    
raise CurtainError('Pay no attention to the person behind the curtain')
```

In this case, <c-s>CurtainError</c-s> can do everything <c-s>RuntimeError</c-s> can do, and I haven't added any functionality. When raised, <c-s>CurtainError</c-s> can be caught when it's specified:

```python
class CurtainError(RuntimeError):
    pass

try:
    raise CurtainError('Pay no attention to the person behind the curtain')
except CurtainError:
    print('What to do if they look behind the curtain?')

print('Greetings')
```

Python does not stop; it prints both <c-s>What to do if they look behind the curtain?</c-s> and <c-s>Greetings</c-s>. If <c-s>RuntimeError</c-s> is specified instead,

```python
class CurtainError(RuntimeError):
    pass

try:
    raise CurtainError('Pay no attention to the person behind the curtain')
except RuntimeError:
    print('What to do if they look behind the curtain?')

print('Greetings')
```

the same things are printed. But if the two get flipped,

```python
class CurtainError(RuntimeError):
    pass

try:
    raise RuntimeError('Pay no attention to the person behind the curtain')
except CurtainError:
    print('What to do if they look behind the curtain?')

print('Greetings')
```

Python stops/<c-s>RuntimeError</c-s> is not caught because <c-s>CurtainError</c-s> is a type of <c-s>RuntimeError</c-s>, but <c-s>RuntimeError</c-s> is not a type of <c-s>CurtainError</c-s>. As simple as that recipe is, a custom exception can be a great way to raise awareness about special conditions and/or make your code easier to understand.

#### Dot Access
