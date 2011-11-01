Home assignment 1 in Cryptography TDA351
Arash Rouhani
rarash@student.chalmers.se
901117-1213

+ Question 1

1/256

+ Question 2

sum(i=1..8 inclusive)
  (1/256^i)

+ Question 3

Let (x) denote the answer from "Question x"

(1)/(2) = (uses excel) ~= 0.99609375

+ Question 4

The question is to show 
  D(C) + R_i + C' = P + R_i
knowing
  C = E(P + C')

Ok, so
  D(C) = D(E(P + C'))
       = P + C'

Then
  D(C) + R_i + C' = P + C' + R_i + C'
                  = P + R_i + (C' + C')
                  = P + R_i

Done.

+ Question 5

Let LBO be short for "last byte of"

LBO R_i = i (definition)
LBO P + R_i = 0 (assumption)
LBO P = LBO P + R_i + R_i (mathematical identity)
      = LBO 0       + R_i ()
      = i

Ans: LBO P is 1

+ Question 6

We need to keep in mind that the whole attack
uses details of the padding and relies on that
the interesting block P is also the last padding
block.

So, our mini message should only be prepended to,
not appended to, as that would ruin the padding
properties. Ok, more concretly, we add random
blocks to the beginning of our previous message.
Also we must take care to not alter the actual
padding, so we add only whole blocks (8tuples of bytes).

So old message
  (R_i + C')||C
becomes
  A_1||A_2||..||A_x||(R_i + C')||C
where A_i is a random valud block, and
x is a big enough number of blocks that
will cause the server to respond with significant
delay when padding is correct.

+ Question 7

b_7 = 1 + i

It comes with the exact same reasoning as with Q5,
only we now state
  padding correct => P + S_i = <?,?,?,?,?,?,1,1>

+ Question 8

T = <r_1, .. ,r_5, i, b_7+2, b_8+2>

END OF ASSIGNMENT 1
1 NOV 2011
