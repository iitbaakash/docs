


riccati
=======

Riccati equation



Calling Sequence
~~~~~~~~~~~~~~~~


::

    X=riccati(A,B,C,dom,[typ])
    [X1,X2]=riccati(A,B,C,dom,[typ])




Arguments
~~~~~~~~~

:A,B,C real matrices nxn, `B` and `C` symmetric.
: :dom `'c'` or `'d'` for the time domain (continuous or discrete)
: :typ string : `'eigen'` for block diagonalization or `schur'` for
  Schur method.
: :X1,X2,X square real matrices (X2 invertible), X symmetric
:



Description
~~~~~~~~~~~

`X=riccati(A,B,C,dom,[typ])` solves the Riccati equation:


::

    A'*X+X*A-X*B*X+C=0


in continuous time case, or:


::

    A'*X*A-(A'*X*B1/(B2+B1'*X*B1))*(B1'*X*A)+C-X


with `B=B1/B2*B1'` in the discrete time case. If called with two
output arguments, `riccati` returns `X1,X2` such that `X=X1/X2`.



See Also
~~~~~~~~


+ `ricc`_ Riccati equation
+ `ric_desc`_ Riccati equation


.. _ric_desc: ric_desc.html
.. _ricc: ricc.html


