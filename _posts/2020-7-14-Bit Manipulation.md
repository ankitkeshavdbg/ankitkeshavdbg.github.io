<!-- Copy and paste the converted output. -->

<!-----
NEW: Check the "Suppress top comment" option to remove this info from the output.

Conversion time: 3.776 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β29
* Thu Jul 16 2020 03:36:14 GMT-0700 (PDT)
* Source doc: Bit Manipulation:
----->


Bit Manipulation:

In some cases, a programmer needs to go beyond this - that is to say that in a deeper level where the importance of bits is realized.

Operations with bits are used in **Data compression** (data is compressed by converting it from one representation to another, to reduce the space) ,**Exclusive-Or Encryption** (an algorithm to encrypt the data for safety issues). In order to encode, decode or compress files we have to extract the data at bit level. **Bitwise Operations are faster and closer to the system** and sometimes optimize the program to a good level.

We all know that 1 byte comprises 8 bits and any integer or character can be represented using bits in computers, which we call its binary form(contains only 1 or 0) or in its base 2 form.

Example:

1) 14 = {1110 }<sub>2</sub>

= 1 * 2<sup>3</sup> + 1 * 2<sup>2</sup> + 1 * 2<sup>1</sup> + 0 * 2<sup>0</sup>

= 14.

2) 20 = {10100 }<sub>2</sub>

= 1 * 2<sup>4</sup> + 0 * 2<sup>3</sup> + 1 * 2<sup>2</sup> + 0 * 2<sup>1</sup> + 0 * 2<sup>0</sup>

= 20.

For characters, we use ASCII representation, which are in the form of integers which again can be represented using bits as explained above.

Bitwise Operators:

There are different bitwise operations used in the bit manipulation. These bit operations operate on the individual bits of the bit patterns. Bit operations are fast and can be used in optimizing time complexity. Some common bit operators are:

NOT ( ~ ): Bitwise NOT is an unary operator that flips the bits of the number i.e., if the ith bit is 0, it will change it to 1 and vice versa. Bitwise NOT is nothing but simply the one’s complement of a number. Lets take an example.

N = 5 = (101)<sub>2</sub>

~N = ~5 = ~(101)<sub>2</sub> = (010)<sub>2</sub> = 2

AND ( & ): Bitwise AND is a binary operator that operates on two equal-length bit patterns. If both bits in the compared position of the bit patterns are 1, the bit in the resulting bit pattern is 1, otherwise 0.

A = 5 = (101)<sub>2</sub> , B = 3 = (011)<sub>2</sub> A & B = (101)<sub>2</sub> & (011)<sub>2</sub>= (001)<sub>2</sub> = 1

OR ( | ): Bitwise OR is also a binary operator that operates on two equal-length bit patterns, similar to bitwise AND. If both bits in the compared position of the bit patterns are 0, the bit in the resulting bit pattern is 0, otherwise 1.

A = 5 = (101)<sub>2</sub> , B = 3 = (011)<sub>2</sub>

A | B = (101)<sub>2</sub> | (011)<sub>2</sub> = (111)<sub>2</sub> = 7

XOR ( ^ ): Bitwise XOR also takes two equal-length bit patterns. If both bits in the compared position of the bit patterns are 0 or 1, the bit in the resulting bit pattern is 0, otherwise 1.

A = 5 = (101)<sub>2</sub> , B = 3 = (011)<sub>2</sub>

A ^ B = (101)<sub>2</sub> ^ (011)<sub>2</sub> = (110)<sub>2</sub> = 6

Left Shift ( &lt;< ): Left shift operator is a binary operator which shifts the some number of bits, in the given bit pattern, to the left and appends 0 at the end. Left shift is equivalent to multiplying the bit pattern with 

2k

 ( if we are shifting k bits ).

1 &lt;< 1 = 2 = 2<sup>1</sup>

1 &lt;< 2 = 4 = 2<sup>2</sup> 1 &lt;< 3 = 8 = 2<sup>3</sup>

1 &lt;< 4 = 16 = 2<sup>4</sup>

<sup> </sup>

<sup><strong>Just look into video if you don’t understand: <a href="https://www.youtube.com/watch?v=nSKT6Ph8u9Q">https://www.youtube.com/watch?v=nSKT6Ph8u9Q</a></strong></sup>

…

1 &lt;< n = 2<sup>n</sup>

Right Shift ( >> ): Right shift operator is a binary operator which shifts the some number of bits, in the given bit pattern, to the right and appends 1 at the end. Right shift is equivalent to dividing the bit pattern with 2k ( if we are shifting k bits ).

4 >> 1 = 2

6 >> 1 = 3

5 >> 1 = 2

16 >> 4 = 1

**1) How to check if a given number is a power of 2 ?**

bool isPowerOfTwo(int x)

    {

        if(x == 0)

            return false;

        else

        {

            while(x % 2 == 0) x /= 2;

            return (x == 1);

            }

    }

Time complexity of the above code is O(logN).

Now think about 

. x & (x-1) will have all the bits equal to the x except for the rightmost 1 in x.

Let, x = 4 = (100)<sub>2</sub>

x - 1 = 3 = (011)<sub>2</sub>

x & (x-1) = 4 & 3 = (100)<sub>2</sub> & (011)<sub>2</sub> = (000)<sub>2</sub>

Let, x = 6 = (110)<sub>2</sub>

x - 1 = 5 = (101)<sub>2</sub>

x & (x-1) = 6 & 5 = (110)<sub>2</sub> & (101)<sub>2</sub> = (100)<sub>2</sub>

Properties for numbers which are powers of 2, is that **they have one and only one bit set in their binary representation**. If the number is neither zero nor a power of two, it will have 1 in more than one place. So if x is a power of 2 then **x & (x-1)** will be 0.

**2) Count the number of ones in the binary representation of the given number.**

Example:

n = 23 = {10111}<sub>2</sub> .

1. Initially, count = 0.

2. Now, n will change to n&(n-1). As n-1 = 22 = {10110}<sub>2</sub> , then n&(n-1) will be {10111<sub>2</sub> & {10110}<sub>2</sub>, which will be {10110}<sub>2</sub> which is equal to 22. Therefore n will change to 22 and count to 1.

3. As n-1 = 21 = {10101}<sub>2</sub> , then n&(n-1) will be {10110}<sub>2</sub> & {10101}<sub>2</sub>, which will be {10100}<sub>2</sub> which is equal to 20. Therefore n will change to 20 and count to 2.

4. As n-1 = 19 = {10011}<sub>2</sub> , then n&(n-1) will be {10100}<sub>2</sub> & {10011}<sub>2</sub>, which will be {10000}<sub>2</sub> which is equal to 16. Therefore n will change to 16 and count to 3.

5. As n-1 = 15 = {01111}<sub>2</sub> , then n&(n-1) will be {10000}<sub>2</sub> & {01111}<sub>2</sub>, which will be {00000}<sub>2</sub> which is equal to 0. Therefore n will change to 0 and count to 4.

6. As n = 0, the loop will terminate and gives the result as 4.

Complexity: O(K), where K is the number of ones present in the binary form of the given number.

**3) Check if the i<sup>th</sup>** **bit is set in the binary form of the given number.**

bool check (int N)

    {

        if( N & (1 <&lt; i) )

            return true;

        else

            return false;

    }

**4) How to generate all the possible subsets of a set ?**

A big advantage of bit manipulation is that it can help to iterate over all the subsets of an N-element set. As we all know there are 2<sup>N</sup> possible subsets of any given set with N elements. What if we represent each element in a subset with a bit. A bit can be either 0 or 1, thus we can use this to denote whether the corresponding element belongs to this given subset or not. So each bit pattern will represent a subset.

Consider a set A of 3 elements.

A = {a, b, c}

Now, we need 3 bits, one bit for each element. 1 represents that the corresponding element is present in the subset, whereas 0 represents the corresponding element is not in the subset. Let’s write all the possible combinations of these 3 bits.

0 = (000)<sub>2</sub> = {}

1 = (001)<sub>2</sub> = {c}

2 = (010)<sub>2</sub> = {b}

3 = (011)<sub>2</sub> = {b, c}

4 = (100)<sub>2</sub> = {a}

5 = (101)<sub>2</sub> = {a, c}

6 = (110)<sub>2</sub> = {a, b}

7 = (111)<sub>2</sub> = {a, b, c}

Pseudo Code:

possibleSubsets(A, N):

        for i = 0 to 2^N:

            for j = 0 to N:

                if jth bit is set in i:

                    print A[j]

            print ‘\n’

Implementation:

 void possibleSubsets(char A[], int N)

    {

        for(int i = 0;i &lt; (1 <&lt; N); ++i)

        {

            for(int j = 0;j &lt; N;++j)

                if(i & (1 <&lt; j))

                    cout <&lt; A[j] <&lt; ‘ ‘;

            cout <&lt; endl;

    }

    }

**Tricks with Bits:**

1) x ^ ( x & (x-1)) : Returns the rightmost 1 in binary representation of x.

As explained above, (x & (x - 1)) will have all the bits equal to the x except for the rightmost 1 in x. So if we do bitwise XOR of x and (x & (x-1)), it will simply return the rightmost 1. Let’s see an example.

x = 10 = (1010)<sub>2</sub> ` x & (x-1) = (1010)<sub>2</sub> & (1001)<sub>2</sub> = (1000)<sub>2</sub>

x ^ (x & (x-1)) = (1010)<sub>2</sub> ^ (1000)<sub>2</sub> = (0010)<sub>2</sub>

2) x & (-x) : Returns the rightmost 1 in binary representation of x

(-x) is the two’s complement of x. (-x) will be equal to one’s complement of x plus 1.

Therefore (-x) will have all the bits flipped that are on the left of the rightmost 1 in x. So x & (-x) will return rightmost 1.

x = 10 = (1010)<sub>2</sub>

(-x) = -10 = (0110)<sub>2</sub>

x & (-x) = (1010)<sub>2</sub> & (0110)<sub>2</sub> = (0010)<sub>2</sub>

3) x | (1 &lt;< n) : Returns the number x with the nth bit set.

(1 &lt;< n) will return a number with only a nth bit set. So if we OR it with x it will set the nth bit of x.

x = 10 = (1010)<sub>2</sub> n = 2

1 &lt;< n = (0100)<sub>2</sub>

x | (1 &lt;< n) = (1010)<sub>2</sub> | (0100)<sub>2</sub> = (1110)<sub>2</sub>

**Applications of bit operations:**

1) They are widely used in areas of graphics ,especially XOR(Exclusive OR) operations.

2) They are widely used in the embedded systems, in situations, where we need to set/clear/toggle just one single bit of a specific register without modifying the other contents. We can do OR/AND/XOR operations with the appropriate mask for the bit position.

3) Data structures like n-bitmap can be used to allocate n-size resource pools to represent the current status.

4) Bits are used in networking, framing the packets of numerous bits which are sent to another system generally through any type of serial interface.

**Problems:**



*   **Swap two nibbles in a byte**

A [nibble ](http://en.wikipedia.org/wiki/Nibble)is a four-bit aggregation, or half an octet. There are two nibbles in a byte.

Given a byte, swap the two nibbles in it. For example 100 is represented as 01100100 in a byte (or 8 bits). The two nibbles are (0110) and (0100). If we swap the two nibbles, we get 01000110 which is 70 in decimal.

100 is 01100100 in binary. The operation can be split mainly in two parts

**1)** The expression “**x & 0x0F**” gives us last 4 bits of x. For x = 100, the result is 00000100. Using bitwise ‘&lt;<' operator, we shift the last four bits to the left 4 times and make the new last four bits as 0. The result after shift is 01000000.

**2)** The expression “**x & 0xF0**” gives us first four bits of x. For x = 100, the result is 01100000. Using bitwise ‘>>’ operator, we shift the digit to the right 4 times and make the first four bits as 0. The result after shift is 00000110.

**int swapNibbles(int x) **

**{ **

**	return ( (x & 0x0F) &lt;< 4 | (x & 0xF0) >> 4 ); **

**} **



*   **Program to Reverse Bits of a Number**

Given an unsigned integer, reverse all bits of it and return the number with reversed bits.

Input : n = 1

Output : 2147483648  

On a machine with size of unsigned

bit as 32. Reverse of 0....001 is

100....0.

Input : n = 2147483648

Output : 1

  
