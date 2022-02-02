# BLAST Language Reference 

Script API functions: [Functions]     
Data Sunchronization: [DataSync]  

### Statement Keywords

|keyword|description|
|-------|-----------|
|[case](ref/switch.md)|switch case compound|
|[default](ref/switch.md)|default switch case compound|
|[else](ref/ifthenelse.md)|else compound of if then else statement sequence|
|[if](ref/ifthenelse.md)|if statement
|[input](ref/inputs.md)|defines an input to the script|
|[for](ref/for.md)|for loop|
|[output](ref/outputs.md)|defines an output of the script|
|[return](ref/return.md)|return; terminate execution|
|[switch](ref/switch.md)|switch statement|
|[then](ref/ifthenelse.md)|then compound of if then else statement sequence|
|[while](ref/while.md)|while loop|
|[yield](ref/yield.md)|yield execution|
|[function](ref/function.md)|inline functions|


### Literal Keywords 

|Keyword|Value|
|-------|-----|
|[false](ref/booleans.md)|0.0|
|[true](ref/booleans.md)|default: 1.0, anything other then 0.0 matches to true|


### Operators 

Seperators: ; , ( )

Arithmetic:  `+  -  *  /` 

Boolean: `&  |  ^ !  ` 

Assingment: `=`

Comparisons: ` = < <= > >= != `

### Assignments | Expressions

An expression is a set of literals and identifiers combined with operators. Parenthesis can be used to influence the order of operation. 

```
// numeric expressions
f = 1 * 10 * 3 * (3 + 4 * 2); 
f = 10 + 5 / 1 * 2;
f = 1 * 4 + 3;
f = 4 * -9.3

// boolean expressions:
b = 1 & 0 | 1; 
b = -1 & 0 | 123.22;
b = true & false | true; 
``` 

Vectors are defined as sets of values enclosed in parenthesis without operators combining them. A comma is used to seperate elements to remove any ambiguity when using negative constants.

Inline vector definition: `(1.2 2.1, -3.3)` 

```
a = (1 2 3 4) * (5 6 7, -8); 
```

### Built in functions 
   [Functions]: /url "Script API Functions"
* note: the optimizer will replace sequences with its equivevalent function whenever possible providing shorter code and faster execution due to reduced control flow. 
  

|function|description|parameters|returns|examples|
|--------|-----------|----------|-------|--------|
|abs|get absolute value of operand| 1 numeric vector | vector  | |
|adda|add all operands in sequence| n numerics of equal vectorsize | vector | |
|all|returns true if all arguments are true| n value of n vectorsizes | scalar | |
|any|returns true if any argument is true|n values of n vectorsizes | scalar | | 
|atan|unity.mathematics.atan|any vectorsize|vector| |
|atan2|unity.mathematics.atan2|any vectorsize|vector| |
|ceil||||
|clamp||||
|ceillog2||||
|ceilpow2||||
|cos|unity.mathematics.cos|any vectorsize|vector ||
|cosh|unity.mathematics.cos|any vectorsize|vector ||
|cross|unity.mathematics.cross|vector 3|vector 3||
|csum|unity.mathematics.csum|any vectorsize|scalar| |
|call|explicetly call a function||[call](call-external.md)|
|debug||||
|debugstack||||
|degrees||||
|diva|divide all operands by eachother in sequence|any vectorsize|vector||
|dot||||
|exp||||
|exp10||||
|floor||||
|floorlog2||||
|fma||||
|fmod||||
|frac||||
|lerp||||
|log10||||
|log2||||
|logn||||
|max|||||
|maxa|get max value from operands|any vectorsize|vector||
|min||||
|mina||||
|mula|multiply all operands in sequence|any vectorsize|vector||
|nlerp||||
|normalize||||
|pow||||
|radians||||
|random|generate a random number|||
|remap||||
|rsqrt||||
|saturate||||
|seed|seed the random number generator|||
|select||||
|sin||||
|sinh||||
|slerp||||
|sqrt||||
|suba|substract all operands from eachother in sequence|any vectorsize|vector||
|tan||||
|trunc||||
|unlerp||||



### Inline Functions

Blast allows the user to define inline functions, a function consists of the function keyword, a parameterlist (that even if empty may not be ommited) and a body: 

```
function f1(a, b) 
(
   c = a + b;  
   return (a + b) / c; 
);
```
Blast functions will however work differently then in for example C#. There is NO scope. Although its possible to use the stack, blast pushes only its current code-pointer to the stack, jumps to the function and then returns back to the location popped from stack. It operates directly on the used variables and it does not make any data copies, making all parameters passed by reference. Returning data will also work directly on the same data elements. Assigning `c` within a function assigns `c` in global scope.

Functions may call other inline functions.

This should be viewed as a utility function, for recurring needs please consider implementing user defined external function calls that can be called natively. 

### External Function Calls 

Blast uses function pointers to connect to other parts of its environment, these will be supplied with the following data by the BLAST engine:

|data|source|description|
|----|------|-----------|
|engine|blast|pointer to engine data, contains constants, functionpointers and randomizer root.|
|environment|user|optional pointer to native data containing data to be used by all scripts|
|caller|user|optional pointer to native data containing all data supplied by the callsite|
|parameters|blast|blast will call the external function using the parameters supplied to it by script|


### Data Synchronization
   [DataSync]: /url "Data Synchronization"
Blast uses the input and output keywords to define input or output variables. These will be prepared in the compiled package for fast IO syncs, the sync method however depends heavily on the packaging mode and its usage. Samples for each mode (Normal, SSMD, Entity) will be provided shortly;


### Data Validation
During development we have the need to test a lot and there is some support for automatic testing in the form of validation script defines: `#validate a 1` These allow the script to set values that blast can match to the output of the script given default input.

Blast can (depending on compilersettings) then validate the script during compilation in the same run it uses to determine the stackspace it needs to reserve in the compiled package. It proved extremely usefull during development and it possibly can catch bugs early in deployment.

**Example script with validation defines:**
```
#define result_1 11111
#define result_2 22222

a = 10; 
b = 2; 

switch(a > b)
(
  case 1:
  (
    e = result_1; 
  )
  default:
  (
    e = result_2;
  )
);
 
#validate e 11111                 
```




