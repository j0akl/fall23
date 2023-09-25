# Group work

## Which variant of the racket code is most readable?

We think variant 3 is the best. As someone who is not overly familiar with Racket,
it is nice that the function does not use racket-specific for/list type functions.
It defines a function classify-1-element, breaking the operation into a smaller chunk,
then applies that operation to the list. The program flow is clear.

## Which is second most?

We thought 6 was the second most clear. Although it uses racket-specific operations,
it uses them sparingly. It is very short, and the group-by function name is very descriptive.
I think this is close to how the function would be written in another language.

## Which is most performant?

Although it may be too good to be true, we think 6 is the most performant.
It starts with a single linear operation on the whole list, then does a for/list
on a list the size of the number of different classifications, which is <= to the
number of elements in l0. Other functions performed more linear time operations.
