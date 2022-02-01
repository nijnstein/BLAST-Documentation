# BLAST Language Reference 

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

```  

        fma, 

        /// <summary>
        /// add all operands in sequence
        /// </summary>
        adda,

        /// <summary>
        /// multiply all operands in sequence
        /// </summary>
        mula,

        /// <summary>
        /// divide all operands by eachother in sequence 
        /// </summary>
        diva,

        /// <summary>
        /// substract all operands from eachother in sequence
        /// </summary>
        suba,

        /// <summary>
        /// returns true if all arguments are true
        /// </summary>
        all,

        /// <summary>
        /// returns true if any argument is true 
        /// </summary>
        any,

        /// <summary>
        /// return absolute value of operand
        /// </summary>
        abs,

        /// <summary>
        /// select instruction 
        /// </summary>
        select,

        /// <summary>
        /// generate a random number 
        /// </summary>
        random,

        /// <summary>
        /// seed the random number generator 
        /// </summary>
        seed,

        /// <summary>
        /// get max value from operands, returns vector of same size as inputs 
        /// </summary>
        max,

        /// <summary>
        /// get min value from operands, returns vector of same size as inputs 
        /// </summary>
        min,

/// = cmax
        maxa,

// = cmin
        mina,

        fmod,

        csum,

        trunc,


        exp,
        exp10,
        log10,
        logn,
        log2,
        cross,
        dot,
        sqrt,
        rsqrt,
        pow,


        sin,
        cos,
        tan,
        atan,
        atan2,
        cosh,
        sinh,

        degrees,
        radians,

        lerp,
        slerp,
        nlerp,
        saturate,        
        clamp,
        normalize,
        ceil,
        floor,
        frac,

        remap,
        unlerp,

        ceillog2,

        floorlog2,

        ceilpow2,


  debugstack
  debug

  [call](call-external.md)
``` 


