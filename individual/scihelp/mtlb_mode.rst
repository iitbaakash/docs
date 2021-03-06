


mtlb_mode
=========

switch Matlab like operations



Calling Sequence
~~~~~~~~~~~~~~~~


::

    mmode=mtlb_mode()
    mtlb_mode(mmode)




Arguments
~~~~~~~~~

:mmode boolean
:



Description
~~~~~~~~~~~

Scilab and Matlab additions and substractions work differently when
used with empty matrices:

:Scilab

::

    a+[] -->a
    a-[] -->a
    []+a -->a
    []-a -->-a


: :Matlab

::

    a+[] -->[]
    a-[] -->[]
    []+a -->[]
    []-a -->[]


:

`mtlb_mode(%t)` switches to Matlab evaluation mode for additions and
substractions. `mtlb_mode(%f)` switches back to Scilab mode.

`mtlb_mode()` return the current mmode' value



See Also
~~~~~~~~


+ `empty`_ ([]) empty matrix


.. _empty: empty.html


