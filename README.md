# Structure and Interpretation of Classical Mechanics

## What is this project?

At its core, it is an implementation of the book *Structure and Interpretation of Classical Mechanics* by Gerald Jay Sussman and Jack Wisdom.

This involves creating a Haskell implementation of the Scheme library *scmutils*, which includes toolboxes for symbolic algebra, differentiation and integration.

A key feature is that the routines for differentation and integration are agnostic to the underlying type - the same functions are overloaded to work with symbolic expressions or with numerical quantities. For example, we could define a polynomial function

    >>> let f a = (1+a)^3

which applies equally to numbers and symbolic expressions:

    >>> f 2
    27
    >>> f x
    1.0 + 3.0x + 3.0x² + x³

We can also find the first four derivates both numerically and symbolically:

    >>> dTake 4 $ f (dVar 2)
    [27,27,18,6]
    >>> dTake 4 $ f (dVar x)
    [1.0 + 3.0x + 3.0x² + x³,3.0 + 6.0x + 3.0x²,6.0 + 6.0x,6.0]

Eventually the library will include type-agnostic integration routines as well.

Get the book [here](http://mitpress.mit.edu/sicm/).

## Authors
Initially authored by Chris Taylor.

Version 2.1.1 under construnction by Ojaswy Akella.


