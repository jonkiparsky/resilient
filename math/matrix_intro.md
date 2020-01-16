An Overview of Matrices And Their Multiplication 
(Review of Math Club, Jan 15 2020)

Definition: A matrix is a rectangular array of numbers. In general, we say
M is an "i by j matrix" if M has i rows and j columns, and we refer to the 
elements of the matrix as Mij, meaning the element in the ith row and the jth 
column of M. Matrix elements are generally one-indexed, and M11 is found in 
the top left corner. (thus, Mij is found in the lower right)

Matrices can be added to and subtracted from each other in the obvious way: 
If A and B are i by j matrices, then C = A + B has C11 = A11+B11, 
C12 = A12+B12, and so forth. (This is not a particularly interesting operation)

Matrices can be transposed. If A is an i by j matrix, and AT is the transposition
of A, then ATij = Aji. Note that this means the elements in the descending diagonal 
from the top left corner are unchanged, and the other elements are "flipped" around
that diagonal. 

Matrices can also be multiplied together, which is usually the operation that 
we are interested in. Multiplication "combines" the elements in the rows and 
columns of the two matrices in a very particular way. To understand this, we should
first say a few words about vectors. 

Vectors, briefly, can be conceived as one-dimensional arrays. Contrariwise, an 
array can be conceived as a collection of one or more arrays, all having the same 
length. In fact, we can have this conception twice: once as a collection of 
"row vectors" running horizontally, and again as a collection of "column vectors" 
running vertically. 

While vectors have many interesting properties and implications, we mention them 
here only to say that two vectors of the same - hm.  Well, "length" is awkward, for 
reasons I won't go into, so we'll say "dimension", but we mean "the same number 
of elements". Start again: two vectors of the same dimension can be multiplied 
together. I'm playing loose with terminology here, we're really taking a "linear
combination", but multiplication is as good a word, so we'll go with it. To 
multiply two vectors V and W, both having n elements, we multiply the elements 
together pairwise and take the sum:
VW = V1 * W1 + V2 * W2 + ... + V(n-1) * W(n-1) + Vn * Wn

Important: Notice that this produces a single number, *not* a new vector. 

So if V = (1,2,3) and W = (2,3,4) then VW = 1*2 + 2*3 + 3*4 = 144.

Returning to matrices, we multiply two matrices A and B together by taking the 
rows of A and the columns of B as vectors, to produce a new matrix C, where each 
element Cij is the product ("linear combination") of the ith row of A and the jth 
column of B. 

That is, if A = 
| 1 | 2 |
| 3 | 4 |

and B = 
| 2 | 3 | 
| 4 | 5 |

then C = 

| 1 * 2 + 2 * 4 | 1 * 2 + 2 * 5 |
| 3 * 2 + 4 * 4 | 3 * 4 + 4 * 5 |

which is equal to 

| 10 | 12 |
| 22 | 32 |



Compatibility: Not all matrices can be multiplied together. Consider the problem
of trying to multiply a 2 X 4 matrix by a 3 X 2 matrix. Concretely, consider A =

| 1 | 2 | 3 | 4 | 
| 2 | 3 | 4 | 5 |

and B = 

| 3 | 5 | 
| 5 | 7 | 
| 7 | 9 | 

If we tried to multiply A * B, we would have to take the linear combination of
(1, 2, 3, 4) and (3, 5, 7), which is not allowed under our definition. 

However, B * A would be allowable, since the linear combination of (3, 5) and (1, 2) is
well-defined. (It is 13, as it happens)

From the above we can see that two matrices can be multiplied together ("are 
compatible") if the number of columns of A is equal to the number of rows of 
B. It would probably be more revealing to say "if the dimension of a row vector 
of A is equal to the dimension of a column vector of B"; the two statements are 
equivalent. 

Further reflection will confirm that the dimensions of the product vector C = AB 
are determined by the number of _rows_ of A and the number of _columns_ of B. If 
it is not obvious why this is, try multiplying some matrices together. Be aware that 
multiplication of matrices by hand gets quite tedious if any dimension gets above, 
say, 6. 

The Identity Matrix: A special matrix I can be constructed by filling a square
matrix with zeros except for the descending diagonal from top left to bottom right. 
This matrix is called the "identity matrix", and is has the property that when 
multiplied by any compatible matrix M (from left or right), the result is always the 
same matrix M. If you are interested in practicing proofs, you can try proving that
(a) I * M or M * I always has the same dimensions as M and 
(b) IMij is equal to M ij for all i and j. (that is, every element of IM is the same
as the corresponding element in M)






