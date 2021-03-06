


graypolarplot
=============

Polar 2D plot of a surface using colors



Calling Sequence
~~~~~~~~~~~~~~~~


::

    graypolarplot(theta,rho,z,[strf,rect])




Arguments
~~~~~~~~~

:theta a vector with size n1, the discretization of the the angle in
  radian.
: :rho a vector with size n2, the discretization of the radius
: :z real matrix of size (n1,n2). `z(i,j)` is the value of the surface
  at the point (theta(i),rho(j)).
: :strf is a string of length 3 `"xy0"`.
    :default The default is `"030"`.
    : :x controls the display of captions.
        :x=0 no captions.
        : :x=1 captions are displayed. They are given by the optional argument
          `leg`.
        :

    : :y controls the computation of the frame.
        :y=0 the current boundaries (set by a previous call to another high
          level plotting function) are used. Useful when superposing multiple
          plots.
        : :y=1 the optional argument `rect` is used to specify the boundaries
          of the plot.
        : :y=2 the boundaries of the plot are computed using min and max
          values of `x` and `y`.
        : :y=3 like `y=1` but produces isoview scaling.
        : :y=4 like `y=2` but produces isoview scaling.
        : :y=5 like `y=1` but `plot2d` can change the boundaries of the plot
          and the ticks of the axes to produce pretty graduations. When the zoom
          button is activated, this mode is used.
        : :y=6 like `y=2` but `plot2d` can change the boundaries of the plot
          and the ticks of the axes to produce pretty graduations. When the zoom
          button is activated, this mode is used.
        : :y=7 like `y=5` but the scale of the new plot is merged with the
          current scale.
        : :y=8 like `y=6` but the scale of the new plot is merged with the
          current scale.
        :

    :

: :leg a string. It is used when the first character x of argument
  `strf` is 1. `leg` has the form `"leg1@leg2@...."` where `leg1`,
  `leg2`, etc. are respectively the captions of the first curve, of the
  second curve, etc. The default is `""`.
: :rect This argument is used when the second character y of argument
  `strf` is 1, 3 or 5. It is a row vector of size 4 and gives the
  dimension of the frame: `rect=[xmin,ymin,xmax,ymax]`.
:



Description
~~~~~~~~~~~

Takes a 2D plot of the surface given by `z` on a polar coordinate grid
defined by `rho` and `theta`. Each grid region if filled with a gray
or color level depending on the average value of `z` on the corners of
the grid.



Sample
~~~~~~



Examples
~~~~~~~~


::

    rho=1:0.1:4;theta=(0:0.02:1)*2*%pi;
    z=30+`round`_(theta'*(1+rho^2));
    f=`gcf`_();
    f.color_map= `hotcolormap`_(128);
    `clf`_();graypolarplot(theta,rho,z)




