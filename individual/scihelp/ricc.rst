


ricc
====

Riccati equation



Calling Sequence
~~~~~~~~~~~~~~~~


::

    [X,RCOND,FERR]=ricc(A,B,C,"cont""method")
    [X,RCOND,FERR]=ricc(F,G,H,"disc","method")




Arguments
~~~~~~~~~

:A,B,C real matrices of appropriate dimensions
: :F,G,H real matrices of appropriate dimensions
: :X real matrix
: :"cont","disc"' imposed string (flag for continuous or discrete)
: :method 'schr' or 'sign' for continuous-time systems and 'schr' or
  'invf' for discrete-tyme systems
:



Description
~~~~~~~~~~~

Riccati solver.

Continuous time:


::

    X=ricc(A,B,C,'cont')


gives a solution to the continuous time ARE


::

    A'*X+X*A-X*B*X+C=0 .


`B` and `C` are assumed to be nonnegative definite. `(A,G)` is assumed
to be stabilizable with `G*G'` a full rank factorization of `B`.

`(A,H)` is assumed to be detectable with `H*H'` a full rank
factorization of `C`.

Discrete time:


::

    X=ricc(F,G,H,'disc')


gives a solution to the discrete time ARE


::

    X=F'*X*F-F'*X*G1*((G2+G1'*X*G1)^-1)*G1'*X*F+H


`F` is assumed invertible and `G = G1*inv(G2)*G1'`.

One assumes `(F,G1)` stabilizable and `(C,F)` detectable with `C'*C`
full rank factorization of `H`. Use preferably `ric_desc`.

C, D are symmetric .It is assumed that the matrices A, C and D are
such that the corresponding matrix pencil has N eigenvalues with
moduli less than one.

Error bound on the solution and a condition estimate are also
provided. It is assumed that the matrices A, C and D are such that the
corresponding Hamiltonian matrix has N eigenvalues with negative real
parts.



Examples
~~~~~~~~


::

    //Standard formulas to compute Riccati solutions
    A=`rand`_(3,3);B=`rand`_(3,2);C=`rand`_(3,3);C=C*C';R=`rand`_(2,2);R=R*R'+`eye`_();
    B=B*`inv`_(R)*B';
    X=ricc(A,B,C,'cont');
    `norm`_(A'*X+X*A-X*B*X+C,1)
    H=[A -B;-C -A'];
    [T,d]=`schur`_(`eye`_(H),H,'cont');T=T(:,1:d);
    X1=T(4:6,:)/T(1:3,:);
    `norm`_(X1-X,1)
    [T,d]=`schur`_(H,'cont');T=T(:,1:d);
    X2=T(4:6,:)/T(1:3,:);
    `norm`_(X2-X,1)
    //       Discrete time case
    F=A;B=`rand`_(3,2);G1=B;G2=R;G=G1/G2*G1';H=C;
    X=ricc(F,G,H,'disc');
    `norm`_(F'*X*F-(F'*X*G1/(G2+G1'*X*G1))*(G1'*X*F)+H-X)
    H1=[`eye`_(3,3) G;`zeros`_(3,3) F'];
    H2=[F `zeros`_(3,3);-H `eye`_(3,3)];
    [T,d]=`schur`_(H2,H1,'disc');T=T(:,1:d);X1=T(4:6,:)/T(1:3,:);
    `norm`_(X1-X,1)
    Fi=`inv`_(F);
    Hami=[Fi Fi*G;H*Fi F'+H*Fi*G];
    [T,d]=`schur`_(Hami,'d');T=T(:,1:d);
    Fit=`inv`_(F');
    Ham=[F+G*Fit*H -G*Fit;-Fit*H Fit];
    [T,d]=`schur`_(Ham,'d');T=T(:,1:d);X2=T(4:6,:)/T(1:3,:);
    `norm`_(X2-X,1)




See Also
~~~~~~~~


+ `riccati`_ Riccati equation
+ `ric_desc`_ Riccati equation
+ `schur`_ [ordered] Schur decomposition of matrix and pencils




Used Functions
~~~~~~~~~~~~~~

See SCI/modules/cacsd/src/slicot/riccpack.f

.. _ric_desc: ric_desc.html
.. _riccati: riccati.html
.. _schur: schur.html


