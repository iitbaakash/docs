****


alufunctions
============

pixel drawing functions. **This function is obsolete.**



Description
~~~~~~~~~~~

src is the source ie the "value of the pixel" which we want to draw.
dst is the destination ie "value of the pixel" which is already drawn.

:0 clear ie "0"
: :1 and ie "src AND dst"
: :2 and reverse ie "src AND NOT dst"
: :3 copy ie "src"
: :4 and inverted ie "(NOT src) AND dst"
: :5 noop ie "dst"
: :6 xor ie "src XOR dst"
: :7 or ie "src OR dst"
: :8 nor ie "(NOT src) AND (NOT dst)"
: :9 equiv ie "(NOT src) XOR dst"
: :10 invert ie "NOT dst"
: :11 or reverse ie "src OR (NOT dst)"
: :12 copy inverted ie "NOT src"
: :13 or inverted ie "(NOT src) OR dst"
: :14 nand ie "(NOT src) OR (NOT dst)"
: :15 set ie "1"
:



