


h_inf
=====

Continuous time H-infinity (central) controller



Calling Sequence
~~~~~~~~~~~~~~~~


::

    [Sk,ro]=h_inf(P,r,romin,romax,nmax)
    [Sk,rk,ro]=h_inf(P,r,romin,romax,nmax)




Arguments
~~~~~~~~~

:P a continuous-time linear dynamical system ("augmented" plant given
  in state-space form or in transfer form)
: :r size of the `P22` plant i.e. 2-vector `[#outputs,#inputs]`
: :romin,romax a priori bounds on `ro` with `ro=1/gama^2`; ( `romin=0`
  usually)
: :nmax integer, maximum number of iterations in the gama-iteration.
:



Description
~~~~~~~~~~~

`h_inf` computes H-infinity optimal controller for the continuous-time
plant `P`.

The partition of `P` into four sub-plants is given through the
2-vector `r` which is the size of the `22` part of `P`.

`P` is given in state-space e.g. `P=syslin('c',A,B,C,D)` with
`A,B,C,D` = constant matrices or `P=syslin('c',H)` with `H` a transfer
matrix.

`[Sk,ro]=H_inf(P,r,romin,romax,nmax)` returns `ro` in `[romin,romax]`
and the central controller `Sk` in the same representation as `P`.

(All calculations are made in state-space, i.e conversion to state-
space is done by the function, if necessary).

Invoked with three LHS parameters,

`[Sk,rk,ro]=H_inf(P,r,romin,romax,nmax)` returns `ro` and the
Parameterization of all stabilizing controllers:

a stabilizing controller `K` is obtained by `K=lft(Sk,r,PHI)` where
`PHI` is a linear system with dimensions `r'` and satisfy:

`H_norm(PHI) < gamma`. `rk (=r)` is the size of the `Sk22` block and
`ro = 1/gama^2` after `nmax` iterations.

Algorithm is adapted from Safonov-Limebeer. Note that `P` is assumed
to be a continuous-time plant.



See Also
~~~~~~~~


+ `gamitg`_ H-infinity gamma iterations for continuous time systems
+ `ccontrg`_ Central H-infinity continuous time controller
+ `leqr`_ H-infinity LQ gain (full state)




Authors
~~~~~~~

F.Delebecque INRIA (1990)



History
~~~~~~~
Version Description 5.4.0 `Sl` is now checked for continuous time
linear dynamical system. This modification has been introduced by this
`commit`_
.. _gamitg: gamitg.html
.. _commit: http://gitweb.scilab.org/?p=scilab.git;a=commit;h=3d7083daae3339813ba747c8adcda1f9599bb80d
.. _leqr: leqr.html
.. _ccontrg: ccontrg.html


