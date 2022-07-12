# %-formatting

```python
>>> name = "Eric"
>>> "Hello, %s." % name
'Hello, Eric.'
```

```python
>>> name = "Eric"
>>> age = 74
>>> "Hello, %s. You are %s." % (name, age)
'Hello Eric. You are 74.'
```

This formatting is verbose and leads to errors, like not displaying tuples or dictionaries correctly.

# str.format()

```python
>>> "Hello, {}. You are {}.".format(name, age)
'Hello, Eric. You are 74.'
```

```python
>>> "Hello, {1}. You are {0}.".format(age, name)
'Hello, Eric. You are 74.'
```

```python
>>> person = {'name': 'Eric', 'age': 74}
>>> "Hello, {name}. You are {age}.".format(name=person['name'], age=person['age'])
'Hello, Eric. You are 74.'
```

```python
>>> person = {'name': 'Eric', 'age': 74}
>>> "Hello, {name}. You are {age}.".format(**person)
'Hello, Eric. You are 74.'
```

This formatting is still verbose when dealing with multiple parameters and longer strings.

# f-Strings

```python
>>> name = "Eric"
>>> age = 74

>>> f"Hello, {name}. You are {age}."
'Hello, Eric. You are 74.'

>>> F"Hello, {name}. You are {age}."

'Hello, Eric. You are 74.'
```

```python
>>> f"{2 * 37}"
'74'
```

```python
>>> def to_lowercase(input):
...     return input.lower()

>>> name = "Eric Idle"
>>> f"{to_lowercase(name)} is funny."
'eric idle is funny.'

>>> f"{name.lower()} is funny."
'eric idle is funny.'
```

```python
class Comedian:
    def __init__(self, first_name, last_name, age):
        self.first_name = first_name
        self.last_name = last_name
        self.age = age

    def __str__(self):
        return f"{self.first_name} {self.last_name} is {self.age}."

    def __repr__(self):
        return f"{self.first_name} {self.last_name} is {self.age}. Surprise!"
    
>>> new_comedian = Comedian("Eric", "Idle", "74")

# f-strings use __str__() by default
>>> f"{new_comedian}"
'Eric Idle is 74.'

# f-strings use  __repr__() with !r flag
>>> f"{new_comedian!r}"
'Eric Idle is 74. Surprise!'
```

```python
# multiline f-Strings
>>> name = "Eric"
>>> profession = "comedian"
>>> affiliation = "Monty Python"
>>> message = (
...     f"Hi {name}. "
...     f"You are a {profession}. "
...     f"You were in {affiliation}."
... )
>>> message
'Hi Eric. You are a comedian. You were in Monty Python.'

# spread strings over multiple lines with \
>>> message = f"Hi {name}. " \
...           f"You are a {profession}. " \
...           f"You were in {affiliation}."
...
>>> message
'Hi Eric. You are a comedian. You were in Monty Python.'
```

```python
# quotation marks
>>> f"{'Eric Idle'}"
'Eric Idle'

>>> f'{"Eric Idle"}'
'Eric Idle'

>>> f"""Eric Idle"""
'Eric Idle'

>>> f'''Eric Idle'''
'Eric Idle'

>>> f"The \"comedian\" is {name}, aged {age}."
'The "comedian" is Eric Idle, aged 74.'
```

```python
# working with dictionaries
>>> comedian = {'name': 'Eric Idle', 'age': 74}
>>> f"The comedian is {comedian['name']}, aged {comedian['age']}."
The comedian is Eric Idle, aged 74.
```

```python
# braces
>>> f"{{70 + 4}}"
'{70 + 4}'

>>> f"{{{70 + 4}}}"
'{74}'

>>> f"{{{{70 + 4}}}}"
'{{70 + 4}}'
```

```python
# backslashes
>>> f"{\"Eric Idle\"}"
  File "<stdin>", line 1
    f"{\"Eric Idle\"}"
                      ^
SyntaxError: f-string expression part cannot include a backslash
    
>>> name = "Eric Idle"
>>> f"{name}"
'Eric Idle'
```

1. joined in Python 3.6.
2. f-strings are faster than both %-formatting and `str.format()`.