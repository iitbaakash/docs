


get_function_path
=================

get source file path of a library function



Calling Sequence
~~~~~~~~~~~~~~~~


::

    path=get_function_path(fun_name)




Arguments
~~~~~~~~~

:fun_name a string, the name of the function
: :path a string, the absolute pathname of the function source file
  (.sci) or [].
:



Description
~~~~~~~~~~~

Given the name of a function get_function_path returns the absolute
pathname of the function source file if the function is defined in a
Scilab library (see lib) or [] if name does not match any library
function.



Examples
~~~~~~~~


::

    get_function_path('median')




See Also
~~~~~~~~


+ `lib`_ library definition
+ `string`_ conversion to string


.. _lib: lib.html
.. _string: string.html


