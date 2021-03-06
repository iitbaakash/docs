


ffilt
=====

coefficients of FIR low-pass



Calling Sequence
~~~~~~~~~~~~~~~~


::

    [x]=ffilt(ft,n,fl,fh)




Arguments
~~~~~~~~~

:ft filter type where `ft` can take the values
    :"lp" for low-pass filter
    : :"hp" for high-pass filter
    : :"bp" for band-pass filter
    : :"sb" for stop-band filter
    :

: :n integer (number of filter samples desired)
: :fl real (low frequency cut-off)
: :fh real (high frequency cut-off)
: :x vector of filter coefficients
:



Description
~~~~~~~~~~~

Get `n` coefficients of a FIR low-pass, high-pass, band-pass, or stop-
band filter. For low and high-pass filters one cut-off frequency must
be specified whose value is given in `fl`. For band-pass and stop-band
filters two cut-off frequencies must be specified for which the lower
value is in `fl` and the higher value is in `fh`



