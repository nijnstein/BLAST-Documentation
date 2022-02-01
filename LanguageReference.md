# BLAST Language Reference 

### Statement Keywords

[case](ref/switch.md)

[default](ref/switch.md)

[else](ref/ifthenelse.md)

[if](ref/ifthenelse.md)

[input](ref/inputs.md)

[for](ref/for.md)

[output](ref/outputs.md)

[return](ref/return.md)

[switch](ref/switch.md)

[then](ref/ifthenelse.md)

[while](ref/while.md)

[yield](ref/yield.md)


### Literal Keywords 

[false](ref/booleans.md)

[true](ref/booleans.md)

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


