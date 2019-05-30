```python
a, b = 0, 1
a, b = b, a

# multi-line string
print('''first line
second line
third line''')
# multi-line string without newline(\n)
print('''no newline1\
no newline2\
nonewline3''')
# better
print('no newline1'
'no newline2'
'nonewline3')

# string format
name='Mike'
age=18
value = {'name': name, 'age': age}
print('Hello %s, your age is %s !' % (name, age))
print('Hello %(name)s, your age is %(age)s !' % value)
print('Hello {name}, your age is {age} !'.format(**value))
print('Hello {}, your age is {} !'.format(name, age))
# needed python >= 3.6
# print(f'Hello {name}, your age is {age} !')

print('hex %x' % 15)

with open('/tmp/in') as fr, open('/tmp/out') as fw:
    pass
    

# while with else
a = 0
while a < 3:
    print('a =', a)
    a += 1
    continue    # will reach else block
else:
    print('else')
```