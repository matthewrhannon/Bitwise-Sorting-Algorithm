# Bitwise-Sorting-Algorithm
Bitwise sort works on the principal of how different sized binary numbers require different amount of bits to store. Language C++.

# Bitwise Sort Theory
This is a sorting algorithm which tests the individual bits of the unsorted data, and determines
where to sort the item based on what bits are active and inactive. For example say you have two 8-bit
unsigned integers which means they can take on any value in the range from 0 to 255. Say the first
integer has a value of 128, and the second integer has a value of 127. The binary representation for each
number is shown below.

Integer 1 Value Decimal: 128 Value Binary: 1000 0000

Integer 2 Value Decimal: 127 Value Binary: 0111 1111

The Bitwise sorting algorithm will determine the most significant bit (MSb) that is active for both
integers. Integer 1 has a MSb of 8, and integer 2 has a MSb of 7. Therefore immediately you know which
integer is larger based on the MSb. Saying this in a different way: integer 1 with its MSb of 8 only knows
that its value will be at least 128 because the other active bits comprising integer 1’s value have not yet
been tested. Integer 2 with its MSb of 7 only knows that it can have a maximum value of 127 if all the
other bits comprising it are also active which they are for integer 2. Knowing that integer 2 doesn’t have
an active bit at position 8 says that it cannot possibly be equal to or larger than a value with an active bit
in position 8. This is the principal that Bitwise sort operates from.

Utilizing Bitwise sort to sort a large array of items using only the method just explained results in
high sorting times which should be avoided. Therefore Bitwise sort was developed to work alone, or
incorporate another sorting algorithm within it to sort the remaining items which have not yet been
isolated using a single or multiple passes with Bitwise sort. The sorting algorithms which were
incorporated into Bitwise sort are a Bucket sort and an in place Comb sort. These were found to have
the highest gain in speed over other sorting algorithms tested.

Much improvement can be done to speed up these algorithms such as not using deques as a
storage object for the unsorted data, and to use additional ‘bithacks’ to optimize the bit operations
inside of the program.
