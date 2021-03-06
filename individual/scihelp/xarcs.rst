


xarcs
=====

draw parts of a set of ellipses



Calling Sequence
~~~~~~~~~~~~~~~~


::

    xarcs(arcs,[style])




Arguments
~~~~~~~~~

:arcs matrix of size (6,n) describing the ellipses.
: :style row vector of size n giving the style to use.
:



Description
~~~~~~~~~~~

`xarcs` draws parts of a set of ellipses described by `arcs`: `arcs=[x
y w h a1 a2;x y w h a1 a2;...]'` where each ellipse is defined by the
6 parameters `(x,y,w,h,a1,a2)` (see `xarc`).

`x, y, w, h` parameters are specified in user coordinates.

`style(i)` gives the color used to draw ellipse number `i`.



Sample
~~~~~~



Examples
~~~~~~~~


::

    `plot2d`_(0,0,-1,"031"," ",[-1,-1,1,1])
    arcs=[-1.0 0.0 0.5; // upper left x
           1.0 0.0 0.5; // upper left y
           0.5 1.0 0.5; // width
           0.5 0.5 1.0; // height
           0.0 0.0 0.0; // angle 1
           180*64 360*64 90*64]; // angle 2
    xarcs(arcs,[1,2,3])




See Also
~~~~~~~~


+ `xarc`_ draw a part of an ellipse
+ `xfarc`_ Fill a part of an ellipse
+ `xfarcs`_ Fill parts of a set of ellipses


.. _xfarc: xfarc.html
.. _xarc: xarc.html
.. _xfarcs: xfarcs.html


