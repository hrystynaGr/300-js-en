### How do assignment/comparison/string/arithmetic/bitwise operators work?

**Assignment operator (=)**
1. Allocates memory for the variable. The amount of memory is the same for all types because at this step, we are not aware of what type will be assigned to the variable.
2. Resolves the 'right hand' expression and creates a value from it.
3. Puts the value into the memory cell previously allocated.
4. Assigns an address of the variable to point to that cell.

**Comparison operators**
1. `==` - checks for equality and perfors type coersion.
2. `===` - checks for equality without performing type coersion.
3. `!=` - checks for *non* equality and performs type coersion.
4. `!==` - checks for non equality without performing type coersion.
5. `<=, >=, <, >` - compare values. Type coercion occurs, and JavaScript attempts to convert the operands to numbers. Then, it performs the comparison.

**Bitwise operators**
1. `>>` - shift right for n bits, fills the vacant positions on the left with 0 por positive and 1 for negative numbers.
```
3 // 0000 0000 0000 0000 0000 0000 0000 0011
3>>2 // 0000 0000 0000 0000 0000 0000 0000 0000

```
2. `<<` - shift left for n bits, fills the vacant positions on the right with 0.
```
3 // 0000 0000 0000 0000 0000 0000 0000 0011
3>>2 // 0000 0000 0000 0000 0000 0000 0000 1100

```
3. `& (AND)` - compare numbers bit by bit and results into 1, only if values at the same positions are 1s, otherwise it puts 0.
Lets take a look at the example:
1. Convert `3` and `11` to binary:
```
3/2 = 1 with the reminder of 1.
1/2 = 0 with the reminder of 1.
```
Binary value for `3` is `11`.
> JS stores binary values as 64-bit values with floating comma, but bitwise operators treats all values as 32-bit with floating comma.
Thus desimal `3` is `0000 0000 0000 0000 0000 0000 0000 0011`  in binary 32-bit.
Let's convert `11` as well:
```
11/2 = 5 with reminder of 1.
5/2 = 2 with reminder of 1.
2/2 = 1 with reminder of 0.
1/2 = 0 with reminder of 1.
```
Binary value for `11` is `1011` or `0000 0000 0000 0000 0000 0000 0000 1011` in binary 32-bit.
So let's apply `&` operator to those numbers:
```
3 // 0000 0000 0000 0000 0000 0000 0000 0011
11// 0000 0000 0000 0000 0000 0000 0000 1011

3&11= 0000 0000 0000 0000 0000 0000 0000 0011
```
Lets convert the result to desimal:
```
1*pow(2,0) + 1*pow(2,1) + 0*pow(2,2) + 0*pow(2,3) +...+ 0*pow(2,31) =
=1*1+1*2+0*4+0*8+...+0*214748e49 =
=1+2+0+0+...+0=3.
```
So the result of `3&11` is `3`.
4. `^ (XOR)` - compare numbers bit by bit and results into 1 at positions where bits are different.
```
3 // 0000 0000 0000 0000 0000 0000 0000 0011
11// 0000 0000 0000 0000 0000 0000 0000 1011

3|11= 0000 0000 0000 0000 0000 0000 0000 1000
```
Lets convert the result to desimal:
```
0*pow(2,0) + 0*pow(2,1) + 0*pow(2,2) + 1*pow(2,3) +...+ 0*pow(2,31) =
=0*1+0*2+0*4+1*8+...+0*214748e49 =
=0+0+0+8+...+0=8.
```
So the result of `31^1` is `8`.
5. `| (OR)` - compare numbers bit by bit and results into 1 in at least one value at the position is 1.
```
3 // 0000 0000 0000 0000 0000 0000 0000 0011
11// 0000 0000 0000 0000 0000 0000 0000 1011

3|11= 0000 0000 0000 0000 0000 0000 0000 1011
```
Lets convert the result to desimal:
```
1*pow(2,0) + 1*pow(2,1) + 0*pow(2,2) + 1*pow(2,3) +...+ 0*pow(2,31) =
=1*1+1*2+0*4+1*8+...+0*214748e49 =
=1+2+0+8+...+0=11.
```
So the result of `3|11` is `11`.
6. `~` - inverts bits.
```
3 // 0000 0000 0000 0000 0000 0000 0000 0011
11// 0000 0000 0000 0000 0000 0000 0000 1011

~3= 1111 1111 1111 1111 1111 1111 1111 1100
~11= 1111 1111 1111 1111 1111 1111 1111 0100
```
Lets convert the `~3` to desimal using `signed 2s method`:
1. Check if left most bit is 1 (negative number) or 0 (positive number).
2. Invert all bits `1111 1111 1111 1111 1111 1111 1111 1100` -> `0000 0000 0000 0000 0000 0000 0000 0011`.
3. Add `1` to the number. 
```
0000 0000 0000 0000 0000 0000 0000 0011
                                      1
---------------------------------------
0000 0000 0000 0000 0000 0000 0000 0100

```
Lets put this to decimal and apply the sign.
```
0*pow(2,0) + 0*pow(2,1) + 1*pow(2,2) + 0*pow(2,3) +...+ 0*pow(2,31) =
=0*1+0*2+1*4+0*8+...+0*214748e49 =
=0+0+4+0+...+0=4. (-4)
```
So the result of `~3` is `-4`.

> Where bitwise operators can be used in real life?
> 1. Data encription. Some simple data encripting algorithsms could use bitwise operations.
> 2. Data compression/decompression. Using Huffman or Run-Length algirithms.
> 3. Working with Images. Using Biwise operators you can work with pixels. For example, chamge the color of a single pixel or apply masks.