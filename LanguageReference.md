<img width="600" alt="BLAST hdr" src="https://user-images.githubusercontent.com/96932314/151460984-1c8f7bc5-be31-4b5f-9921-536c0092fb72.PNG">

# BLAST Language Reference 

**DISCLAIMER** BLAST is new, partly experimental and under active development, bugs are to be expected and please create an issue for any issue there might be so we can handle it as quickly as possible. 

Issues: https://github.com/nijnstein/BLAST-Documentation/issues

[BLAST Overview](README.md) - [Examples](examples.md)

### BlastScript 

-A blast script is a collection of statements seperated by dotcomma's and grouped by parenthesis.

Blastscript sample:
```csharp
#input position float3 0 0 0                   
position.x = min(100, position.x + 0.001);                    
```

Full C# GameObject example:
```csharp
public class Single2 : MonoBehaviour
{
    BlastScript script;

    void Start()
    {
        Blast.Initialize();

        // prepare the script once 
        script = BlastScript.FromText("#input position float3 0 0 0\n position.x = min(100, position.x + 0.001);");

        BlastError result = script.Prepare();
        if (result != BlastError.success)
        {
            Debug.LogError($"Error during script compilation: {result}");
            script = null; 
        }
    }

    void Update()
    {
        if (script == null) return; 

        // the each frame, update current position 
        script["position"] = (float3)transform.position;

        // execute the script
        BlastError result = script.Execute(); 
        if (result == BlastError.success)
        {
            // and set value 
            transform.position = (float3)script["position"];
        }
        else
        {
            Debug.LogError($"Error during script execution: {result}"); 
        }
       
    }
}
```



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

Indexing: .[x|y|z|w|r|g|b|a] 


### Constant data 
First off, there is no constant analysis used for removing unneeded constant statements, future versions might decide to remove constant statements leading to unused values but for now blast wont botter.

Blast uses bytecode operations to index a datasegment for variable and stack data. Any constant value that is not internally mapped to a bytecode will be packaged in the datasegment. Blast map's several often used values like 0, 1, 2, pi and others to byte sized opcodes.

#### Inlined constant data:
In SSMD packaging mode constants are inlined into the code segment to avoid duplicate data in many datasegments at the cost of some performance while in normal packaging mode constant data is always referenced as if it was a data element. Any constant referenced multiple times is defined once in the code segment after which it is referenced by instructions: `constant_ref | constant_long_ref`

This has the benefit that constant data elements dont substract from the usable variable element count in the script. 

#### Named constants:

|constant|source|value|
|--------|------|-----|
|framecount|UnityEngine.Time.frameCount|frame count since start|
|fixedtime|UnityEngine.Time.fixedTime|fixed time at start of interval|
|time|UnityEngine.Time.time|time at start of interval|
|fixeddeltatime|UnityEngine.Time.fixedDeltaTime|delta of fixed interval|
|deltatime|UnityEngine.Time.deltaTime|delta of normal interval = frametime|
|epsilon|math.EPSILON||
|infinity|math.INFINITY||
|negative_infinity|-math.INFINITY||
|nan|math.NAN||
|min_value|math.FLT_MIN_NORMAL||

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

// bit operations:
flags = 00100000_00000000_00000000_00000000;  
if(get_bits(flags, mask)) then (set_bit(flags, 2, 0);); 

``` 

Vectors are defined as sets of values enclosed in parenthesis without operators combining them. A comma is used to seperate elements to remove any ambiguity when using negative constants.

Inline vector definition: `(1.2 2.1, -3.3)` 

```
a = (1 2 3 4) * (5 6 7, -8); 
```

To get the component of a vector it can be indexed: `a.x` 

### Datatypes 

The only datatype fully supported is the float of vectorsize 1 to 4. There is partial support for bool32 operations which index a single dataelement as 32 bit flags.

- Future versions will add integer datatypes.

#### CDATA Sections 
supported from v1.0.4

CData isnt a real datatype but just constant length data that later can be interpreted to be a fixed array of the requested type. CDATA sections will provide backing memory for constantly sized arrays. When located in the code segment they are assumed to be constant during the current frame and shared among all executions of that script. 

** v1.1 ** Later versions will allow CDATA sections in the datasegment (restricted to max 127 elements) or externally pointed to by a native pointer.

** v1.0.5 ** The SSMD interpretor will be able to loop over CDATA sections as they are constantly sized as long as the iterator is not conditionally increased and the loop condition itself is constant. As the data is expected to be constant during the current frame large optimizations become possible for the ssmd interpretor as it can expand its results over all components in vectors that result in constant operations based on the fact that CDATA is constant for the current calculation frame. (ie: deltatime is the same in all scripts during the whole frame)


Scriptcode: 
```csharp
#cdata a 14.42 344.4 54444.345 22190 
#cdata msg 'cmd_or_msg_or_log' 

b = size(a) - 1;     # as float is the default datatype, size returns 5 while the bytesize is 20 
b = a[b];            # again, float = default, and a is indexed as float[]

if(b = 22190) then 
(
    send(msg);       # send data to some sink, for now the log 
)
```

Bytecode: 
```
000| 028 040 074 000 016 082 184 102 065 051 
010| 051 172 067 088 172 084 071 000 092 173 
020| 070 074 000 017 099 109 100 095 111 114  
030| 095 109 115 103 095 111 114 095 108 111 
040| 103 001 128 073 075 000 043 009 085 000 
050| 003 128 060 075 000 052 128 026 012 024 
060| 128 020 129 025 024 076 075 000 046 025 
```

Somewhat readable assembly
```
jump 40 cdata[16] #082 #184 #102 #065 #051 #051 #172 #067 
#088 #172 #084 #071 #000 #092 #173 #070 cdata[17] #099 
#109 #100 #095 #111 #114 #095 #109 #115 #103 #095 #111
#114 #095 #108 #111 #103 set b size cdataref #000 #043
- 1 nop setf b idx_N #075 #000  52 b jz 12 ( b = 22190 ) 
( send cdataref #000 #046 )
```

CData can be defined in 2 distinct ways:

**Constant CDATA**
**v1.0.4**
Constant cdata is data that is inlined into the codesegment and for normal use should be constant: 

```
#cdata a 14.42 344.4 54444.345 22190 
#cdata a 'abcd'
#cdata a 11110111_11101110_10111111_00110011 11110111_11101110_10111111_00110011 
```

**Variable CDATA**
**v1.0.5**
Variable cdata is data that is allocated in the datasegment and can be set as parameter to the script through input defines.
``` 
#input msg cdata 'some message for exceptional events'
```

##### CDATA backing memory 
**v1.0.5** 
CDATA arrays are stored in the smallest bytesize allowed without losing precision beyond the constantepsilon value configurable through compiler options. During compilation the compiler will decide the lowest usable bytesize for the values in the constant data. Users an also type cdata as to avoid this behaviour. 

Encoding types: 
|name|backing|variable type|
|----|-------|-------------|
|None|float32|-------------|
|u8_fp32|unsigned byte|float32|
|s8_fp32|signed byte|float32| 
|fp8_fp32|8 bit floating point|float32|
|fp16_fp32|16 half|float32|
|fp32_fp32|float32|float32| 
|u8_i32|unsigned byte|int32|
|i8_i32|signed byte|int32|
|i16_i32|signed short|int32|
|i32_i32|signed int32|int32|

##### Shared CDATA
**v1.0.4**

CData defined to be inlined as constant is actually shared among all executions of that script using the same scriptpackage. 

For now this is allowed by default but we might decide to force the user to enable this behaviour through compileroptions|defines.

### Built in functions 
   [Functions]: /url "Script API Functions"
* note: the optimizer will replace sequences with its equivevalent function whenever possible providing shorter code and faster execution due to reduced control flow. 
  

 Index    FID   FunctionName                     Operation    Extended Op  
--------------------------------------------------------------------------------
     3      3   yield                            yield        nop         
     4      4   pop                              pop          nop         
     5      5   peek                             peek         nop         
     6      6   seed                             ex_op        seed        
     7      7   push                             push         nop         
     8      8   pushf                            pushf        nop         
     9      9   pushc                            pushc        nop         
    10     10   pushv                            pushv        nop         
    11     11   debug                            ex_op        debug       
    12     12   debugstack                       ex_op        debugstack  
    13     13   validate                         ex_op        validate    
    32     32   return                           ret          nop         
    33     33   abs                              abs          nop         
    34     34   min                              min          nop         
    35     35   max                              max          nop         
    36     36   mina                             mina         nop         
    37     37   maxa                             maxa         nop         
    38     38   any                              any          nop         
    39     39   all                              all          nop         
    40     40   adda                             adda         nop         
    41     41   suba                             suba         nop         
    42     42   diva                             diva         nop         
    43     43   mula                             mula         nop         
    44     44   fma                              fma          nop         
    45     45   fmod                             ex_op        fmod        
    46     46   trunc                            trunc        nop         
    47     47   csum                             csum         nop         
    48     48   select                           select       nop         
    49     49   random                           random       nop         
    50     50   idx                              index_x      nop         
    51     51   idy                              index_y      nop         
    52     52   idz                              index_z      nop         
    53     53   idw                              index_w      nop         
    54     54   idxn                             index_n      nop         
    55     55   expand2                          expand_v2    nop         
    56     56   expand3                          expand_v3    nop         
    57     57   expand4                          expand_v4    nop         
    58     58   sin                              ex_op        sin         
    59     59   cos                              ex_op        cos         
    60     60   tan                              ex_op        tan         
    61     61   atan                             ex_op        atan        
    62     62   atan2                            ex_op        atan2       
    63     63   cosh                             ex_op        cosh        
    64     64   sinh                             ex_op        sinh        
    65     65   degrees                          ex_op        degrees     
    66     66   rad                              ex_op        radians     
    67     67   sqrt                             ex_op        sqrt        
    68     68   rsqrt                            ex_op        rsqrt       
    69     69   pow                              ex_op        pow         
    70     70   normalize                        ex_op        normalize   
    71     71   saturate                         ex_op        saturate    
    72     72   clamp                            ex_op        clamp       
    73     73   log2                             ex_op        log2        
    74     74   log10                            ex_op        log10       
    75     75   log                              ex_op        logn        
    76     76   exp                              ex_op        exp         
    77     77   exp10                            ex_op        exp10       
    78     78   cross                            ex_op        cross       
    79     79   dot                              ex_op        dot         
    80     80   ceil                             ex_op        ceil        
    81     81   floor                            ex_op        floor       
    82     82   frac                             ex_op        frac        
    83     83   lerp                             ex_op        lerp        
    84     84   slerp                            ex_op        slerp       
    85     85   nlerp                            ex_op        nlerp       
    86     86   unlerp                           ex_op        unlerp      
    87     87   remap                            ex_op        remap       
    88     88   ceillog2                         ex_op        ceillog2    
    89     89   floorlog2                        ex_op        floorlog2   
    90     90   ceilpow2                         ex_op        ceilpow2    
    91     91   set_bits                         ex_op        set_bits    
    92     92   set_bit                          ex_op        set_bit     
    93     93   get_bits                         ex_op        get_bits    
    94     94   get_bit                          ex_op        get_bit     
    95     95   count_bits                       ex_op        count_bits  
    96     96   reverse_bits                     ex_op        reverse_bits
    97     97   shl                              ex_op        shl         
    98     98   shr                              ex_op        shr         
    99     99   rol                              ex_op        rol         
   100    100   ror                              ex_op        ror         
   101    101   lzcnt                            ex_op        lzcnt       
   102    102   tzcnt                            ex_op        tzcnt       
   103    103   zero                             zero         nop         
   104    104   clear_bits                       zero         nop         
   105    105   reinterpret_int32                ex_op        reinterpret_int32
   106    106   reinterpret_bool32               ex_op        reinterpret_bool32
   107    107   reinterpret_float32              ex_op        reinterpret_float
   108    108   send                             ex_op        send        
   109    109   size                             size         nop         
   110    110   length                           ex_op        length      
   111    111   lengthsq                         ex_op        lengthsq    
   112    112   square                           ex_op        square      
   113    113   distance                         ex_op        distance    
   114    114   distancesq                       ex_op        distancesq  
   115    115   reflect                          ex_op        reflect     
   116    116   project                          ex_op        project     
   117    117   up                               ex_op        up          
   118    118   down                             ex_op        down        
   119    119   forward                          ex_op        forward     
   120    120   back                             ex_op        back        
   121    121   left                             ex_op        left        
   122    122   right                            ex_op        right       
   123    123   eulerxyz                         ex_op        EulerXYZ    
   124    124   eulerxzy                         ex_op        EulerXZY    
   125    125   euleryxz                         ex_op        EulerYXZ    
   126    126   euleryzx                         ex_op        EulerYZX    
   127    127   eulerzxy                         ex_op        EulerZXY    
   128    128   eulerzyx                         ex_op        EulerZYX    
   129    129   euler                            ex_op        Euler       
   130    130   quaternionxyz                    ex_op        QuaternionXYZ
   131    131   quaternionxzy                    ex_op        QuaternionXZY
   132    132   quaternionyxz                    ex_op        QuaternionYXZ
   133    133   quaternionyzx                    ex_op        QuaternionYZX
   134    134   quaternionzxy                    ex_op        QuaternionZXY
   135    135   quaternionzyx                    ex_op        QuaternionZYX
   136    136   quaternion                       ex_op        Quaternion  
   137    137   lookrotation                     ex_op        LookRotation
   138    138   lookrotationsafe                 ex_op        LookRotationSafe
   139    139   rotate                           ex_op        Rotate      
   140    140   angle                            ex_op        Angle       
   141    141   mul                              ex_op        Mul         


### Bit|Bool32 Operations 

```csharp

#input flags bool32 11001100_11001100_11001100_11001100; 

# operations that return true|false 
a = count_bits(flags); 
a = lzcnt(flags);
a = tzcnt(flags); 
a = get_bit(flags, 1); 
a = get_bits(flags, 11111111_00000000_11111111_00000000, true);

# both any and all support multiple parameters as long as all are bool32
a = any(flags);  
a = all(flags); 

# operations that work in place
set_bit(flags, 1, true); 
set_bit(flags, 2, a);
set_bits(flags, 11111111_00000000_11111111_00000000, true);
reverse_bits(flags); 
rol(flags, 1); 
ror(flags, 1); 
shr(flags, 1); 
shl(flags, 1); 

# reinterpret the data at a as a bool32, set metadata of a to type Bool32 and vectorsize 1
reinterpret_bool32(a);

``` 



### Inline Functions

Blast allows the user to define inline functions, a function consists of the function keyword, a parameterlist (that even if empty may not be ommited) and a body: 

```csharp
function f1(a, b) 
(
   c = a + b;  
   return (a + b) / c; 
);
```

Blast functions will however work differently then in for example C#. There is NO scope as the function is inlined at the callsite. It operates directly on the used variables and it does not make any data copies, making all parameters passed by reference. Returning data will also work directly on the same data elements. Assigning `c` within a function assigns `c` in global scope.

Inlined Functions may call other inline functions.

Inlined Functions may not declare new variables 


This should be viewed as a utility function, for recurring needs please consider implementing user defined external function calls that can be called natively. 

### External Function Calls 

Blast uses function pointers to connect to other parts of its environment, these will be supplied with the following data by the BLAST engine:

|data|source|description|
|----|------|-----------|
|engine|blast|pointer to engine data, contains constants, functionpointers and randomizer root.|
|environment|user|optional pointer to native data containing data to be used by all scripts|
|caller|user|optional pointer to native data containing all data supplied by the callsite|
|parameters|blast|blast will call the external function using the parameters supplied to it by script|

***supports only single floats, future versions will expand on this***

Blast will use all components of the supplied input parameters to satify the functions parameter list:

```csharp
 a = (1 1 1);
 external(a); 
```

Is equivalent to: 
```csharp
 a = (1 1 1);
 external(a.x, a.y, a.z); 
```

#### [BS1] Supported prototypes

```csharp 
    // full paramater list (including enviroment data), up until 16 float params
    public delegate float BlastDelegate_f1(IntPtr engine, IntPtr data, IntPtr caller, float a);
    public delegate float BlastDelegate_f11(IntPtr engine, IntPtr data, IntPtr caller, float a, float b);
    public delegate float BlastDelegate_f111(IntPtr engine, IntPtr data, IntPtr caller, float a, float b, float c);
    // ......
    public delegate float BlastDelegate_f1111(IntPtr engine, IntPtr data, IntPtr caller, float a, float b, float c, float d...... , float 16);
    
    // short external defines without environment pointers 
    public delegate float BlastDelegate_f0_s();
    public delegate float BlastDelegate_f1_s(float a);
    public delegate float BlastDelegate_f11_s(float a, float b);

``` 

### Data Synchronization
   [DataSync]: /url "Data Synchronization"
Blast uses the input and output keywords to define input or output variables. These will be prepared in the compiled package for fast IO syncs, the sync method however depends heavily on the packaging mode and its usage. Samples for each mode (Normal, SSMD) will be provided with the package.
 
<img width="476" alt="packagemode" src="https://user-images.githubusercontent.com/96932314/159478223-43b28385-b8a3-4761-b8e6-aab1e247660c.PNG">

### Stacksize Determination
Blast determines the size of the stack to allocate as follows:

- First; if **stack_size** is defined as:  `#define stack_size 12` blast will fix the stacksize to 12 bytes, additional space will be added if yield is to be supported.
- Second; if compileroptions specify **EstimateStack** then during compilation the package is executed once using default data and the stack size is determined from analysis of the stack. Note that this will force an extra compilation step if the packagemode is ssmd as currently stack estimation is only supported by the normal package mode which will always use more stack then the ssmd packager. (which should not matter too much if the no-stack option is used to use the threadlocal stack in the interpretor and not actually package the stack in the package memory) 
- Third; if by now no stacksize is known, blast will count overlapping pairs of push-pop pairs and estimates stack from that. If no push command is used then the stacksize will be set to 0; If Yield is used in the package, 20 bytes are additionally allocated to support stacking internal state on yield.

### Basic Use 

Use methods provided by the BlastScript class to read or write to script variables exposed via input and/or output, it is not necessary to use input nor output defines but doing so forces their memoryorder regardless the code written and should be considered good practice, the can be omitted but you will have to directly write to the datasegments to set variables by name.

BlastScript:
```csharp
#input a float3 3 3 3
#input b float 3

a = b * a; 
``` 

Unity:
```csharp

// create script, set a 
BlastScript script = BlastScript.FromResource("/bs"); 
script.Set("a", new Vector3(4, 4, 4));
script.Set("b", 8);
script.Execute(); 

Vector3 result = (Vector3)script["a"];

``` 

#### Entity/IComponentData

The script's datasegment is directly mapped against an IComponentData record: 

For a script defined as: 
```csharp
#input a float3 3 3 3
#input b float 3

a = b * a; 
``` 

The IComponentData should be like:
```csharp
public struct data : IComponentData 
{
  public float3 ValueA;
  public float ValueB;   
}
```

The script can then very efficiently use this as a datasegment.

##### Yield and Entities 

If yield is used, all memory used for script execution must map to the IComponentData struct. This includes any stackmemory that is used: yield reserves 20 bytes in each segment to allow it to store its internal execution state.  

#### SSMD 

The scripts datasegment is packed as with entities but not matched to any structure, it might also not be complete depending on any constant data in it. In SSMD mode there is no stack allocated in the datasegment and it can inline any constant data in the code datastream to maximize memory efficiency when running many billions of scripts each second.

##### Yield
Yield is not supported yet. 


### Data Validation
During development we have the need to test a lot and there is some support for automatic testing in the form of validation script defines: `#validate a 1` These allow the script to set values that blast can match to the output of the script given default input.

Blast can (depending on compilersettings) then validate the script during compilation in the same run it uses to determine the stackspace it needs to reserve in the compiled package. It proved extremely usefull during development and it possibly can catch bugs early in deployment.

**Example script with validation defines:**
```csharp
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

#### Runtime validation 
To validate values in runtime use the Validate(id, value) function. This will compare the value to the value of the id and if different it will raise an error during interpretation in TRACE and DEBUG modes. This function will not be compiled in release mode.

**A typical testing script in our unittests using Validate()**
```
#input a float 0
b = 00000001_00000000_00000000_00000000;
a = get_bit(b, 7); 
debug(a); 
debug(b); 
validate(a, 1);
```




