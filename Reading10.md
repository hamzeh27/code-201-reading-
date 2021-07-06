# Error Handling & Debugging
## EXECUTION CONTEXT
Every statement in a script lives in one of three
execution contexts:
- GLOBAL CONTEXT
*Code that is in the script, but not in a function.
There is only one global context in any page.*
- FUNCTION CONTEXT
*Code that is being run within a function.
Each function has its own function context.*
- EVAL CONTEXT (NOT SHOWN)
*Text is executed like code in an internal function
called eva l {) (which is not covered in this book*
## ARIABLE SCOPE
The first two execution contexts correspond with the
notion of scope (which you met on p98):
- GLOBAL SCOPE
*If a variable is declared outside a function, it can
be used anywhere because it has global scope.
If you do not use the var keyword when creating
a variable, it is placed in global scope.*
- FUNCTION-LEVEL SCOPE
*When a variable is declared within a function,
it can only be used within that function. This is
because it has function-level scope.*
### Syntax Error
**SYNTAX IS NOT CORRECT
**This is caused by incorrect use of the rules of the
language. It is often the result of a simple typo.
- MISMATCHING OR UNCLOSED QUOTES
document .write ("Howdyl );
SyntaxError: Unexp ec t ed EOF
- MISSING CLOSING BRACKET
document .getElementByid('page' I
SyntaxErr or : Expected token ' ) '
- MISSING COMMA IN ARRAY
Would be same for missing] at the end
var l ist = ['Item 1', 'Item 2 ' l 'rtem 3'];
SyntaxError: Expected token ']'
- MALFORMED PROPERTY NAME
It has a space but is not surrounded by quote marks
user = { f i rstl name: "Ben", lastName: "Lee"};
Synt axError: Expected an identifier but
found 'name ' instead

### Ref erenceError
- VARIABLE DOES NOT EXIST
This is caused by a variable that is not declared or is
out of scope.
- VARIABLE IS UNDECLARED
var width = 12 ;
var area = width * llt!ftNU! ;
ReferenceError: Can ' t find vari able:
height
- NAMED FUNCTION IS UNDEFINED
document.write ( randomFunction() ) ;
ReferenceError: Can't find variable :
randomFunction
URI
### EvalError
*INCORRECT USE OF eval() FUNCTION
The eva l () function evaluates text through the
interpreter and runs it as code (it is not discussed
in this book). It is rare that you would see this type
of error, as browsers often throw other errors when
they are supposed to throw an Eva 1 Error.
### URI Error
INCORRECT USE OF URI FUNCTIONS
If these characters are not escaped in URls, they will
cause an error: / ? & I : ;
CHARACTERS ARE NOT ESCAPED
decodeURI('http: //bbc . com/ news . phplla=l') ;
URlError: URI error
### Type Error
VALUE IS UNEXPECTED DATA TYPE
This is often caused by trying to use an object or
method that does not exist.
INCORRECT CASE FOR document OBJECT
l!J ocument.wri te ( 'Oops! ');
TypeError: 'undefined' is not a funct ion
(eval uating 'Document.write('Oops! ')')
INCORRECT CASE FOR write() METHOD
document. eJrite('Oops ! ') ;
TypeError: 'undefined' is not a function
(evaluating 'document.Write( 'Oops! ') ')
METHOD DOES NOT EXIST
var box = {};
box .@Mi}id;
II Create empty object
II Try to access getArea()
TypeError: 'undefined ' is not a function
(evaluating 'box.getArea()')
DOM NODE DOES NOT EXIST
var el = document .getElementByid( llll) ;
el.innerHTML = 'Mango';
TypeError: 'null' is not an object
(evaluating 'el .innerHTML = 'Mango'')
### RangeError
- NUMBER OUTSIDE OF RANGE
If you call a function using numbers outside of its
accepted range.
- CANNOT CREATE ARRAY WITH -1 ITEMS
var anArray = new Array(~);
RangeError : Array si ze is not a smal l
enough positive integer
- NUMBER OF DIGITS AFTER DECIMAL IN
tofhed() CAN ONLY BE 0-20
var price = 9.99;
price.toFixed( fJI);
RangeError: toFixed() argument must be
between 0 and 20
- NUMBER OF DIGITS IN toPrecision() CAN
ONLY BE 1-21
num = 2.3456;
num.toPrecisi on(flJ ) ;
RangeError: toPrecision() argument must
be between 1 and 21
## HOW TO DEAL WITH ERRORS
- DEBUG THE SCRIPT TO FIX ERRORS
- HANDLE ERRORS GRACEFULLY
