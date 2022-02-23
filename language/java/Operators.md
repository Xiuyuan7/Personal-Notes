## Bitwise Operators

### Bitwise OR (|)

```
a = 5 = 0101 (In Binary)
b = 7 = 0111 (In Binary)

Bitwise OR Operation of 5 and 7
  0101
| 0111
________
0111  = 7 (In decimal) 
```

### Bitwise AND (&)

```
a = 5 = 0101 (In Binary)
b = 7 = 0111 (In Binary)

Bitwise AND Operation of 5 and 7
  0101
& 0111
________
0101  = 5 (In decimal) 
```

### Bitwise XOR (^)

```
a = 5 = 0101 (In Binary)
b = 7 = 0111 (In Binary)

Bitwise XOR Operation of 5 and 7
  0101
^ 0111
________
0010  = 2 (In decimal) 
```

### Bitwise Complement (~)

```
a = 5 = 0101 (In Binary)

Bitwise Complement Operation of 5

~ 0101
________
1010  = 10 (In decimal) 
```

### Bitwise Signed Left Shift (<<)

Left shift a number by 1 is equivalent to multiplying it by 2.

```
a = 5 = 0101 (In Binary)

Bitwise Left Shift of 5

5 << 1
 ________
1010  = 10 (In decimal) 
```

```
a = -5 = 10101 (In Binary)

Bitwise Left Shift of 5

5 << 1
 ________
11010  = -10 (In decimal) 
```

### Bitwise Signed Right Shift (>>)

Right shift a number by 1 is equivalent to dividing it by 2.

```
a = 12 = 01100 (In Binary)

Bitwise Right Shift of 12

12 >> 2
________
00011 = 2 (In decimal)
```

```
a = -12 = 11100 (In Binary)

Bitwise Right Shift of 12

-12 >> 2
________
11111 = -3 (In decimal)
```

### Complex

```
a |= b	a = a | b
a &= b	a = a & b
a ^= b	a = a ^ b
a >>= b	a = a >> b
a <<= b	a = a << b
```



