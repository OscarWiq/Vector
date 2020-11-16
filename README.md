# Vector

## 3-dimensional Vector class which that works with multiple assignment, supports equality and inequality operators.

```
>>> v = Vector(1, 2, 3)
>>> x, y, z = v
>>> print(x, y, z)
1 2 3
>>> v == Vector(1, 2, 4)
False
>>> v == Vector(1, 2, 3)
True
```

### Uses __slots__ for efficient attribute lookups, meaning other attributes won't be able to be assigned to it and it won't have a __dict__.

```
>>> v.a = 4
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Vector' object has no attribute 'a'
>>> v.__dict__
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: 'Vector' object has no attribute '__dict__'
```

### Supports addition and subtraction with other Vector objects:

```
>>> Vector(1, 2, 3) + Vector(4, 5, 6) == Vector(5, 7, 9)
True
>>> Vector(5, 7, 9) - Vector(3, 1, 2) == Vector(2, 6, 7)
True
```

Note that addition and subtraction shouldn't work in-place: they should return a new Vector object.

### Supports multiplication and division by numbers (this should return a new scaled vector):

```
>>> 3 * Vector(1, 2, 3) == Vector(3, 6, 9)
True
>>> Vector(1, 2, 3) * 2 == Vector(2, 4, 6)
True
>>> Vector(1, 2, 3) / 2 == Vector(0.5, 1, 1.5)
True
```

### Immutable:

```
>>> v = Vector(1, 2, 3)
>>> v.x = 4
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
    raise AttributeError("Vectors are immutable")
AttributeError: Vectors are immutable
```
