<img width="600" alt="BLAST hdr" src="https://user-images.githubusercontent.com/96932314/151460984-1c8f7bc5-be31-4b5f-9921-536c0092fb72.PNG">

## BLAST
##### Provides a fast scripting language for running statemachines or other decision making processes from bursted code in unity.

[Language Reference](LanguageReference.md) - [Namespace (doxygen)](Namespace/_Sidebar.md) - [Examples](examples.md)

**Disclaimer:** This is a partly experimental package, anything listed in the documentation is guaranteed to be supported indefinately, the rest is under active development and very open for suggestions. Please log any issues at https://github.com/nijnstein/BLAST-Documentation/issues so we can handle them as efficiently as possible.

## SSMD
### Single Script Multiple Data

In many large scale simulations many scripts are mostly the same but with different data. BLAST can execute those with the control flow inverted, meaning that it in essence performs the SIMD equivelent of scripting languages, each operation will translate in a vector operation easily compiled to beautiful packed assembly. This can result in script running faster then native code dueue to the ways memory is forced to be and execution is performed. Usually this kind of optimization is not simply possible in real-life situations with compiled code. In SSMD mode, BLAST can handle scripts faster then native code in single execution. It shows how it becomes possible to optimize otherwise hard to optimize parts, especially if they were entered by a user in an online game were there is no control. 

#### But HOW? 

In many situations things boil down to a handler executing actions, either predefined or defined by configuration. If each action is implemented in .net code then when handling many actions as they occur results in calling each action seperately, in a loop or not. Its whole sequence of operations is executed from start until end. Scripting languages normally do the same and when used to handle states in a statemachine they offer a flexible and configuratable but slow solution. BLAST's SSMD mode takes many equal actions taken on different data and executes them as one. If it encounters a multiplication for example then it handles the multiplication in loop, if available with SIMD instructions, over all datasegments at once before reading the next token. This would not have been possible to do with the code that was written in c# to handle a single action and often is much faster to execute especially when there are many datasegments. Offcoarse, you could hand-optimize each actions's .net code to also have a path to execute many but that adds complexity, mantainance and you loose configurability. Many games these days are defined by configuration and in these blast would allow for higher performance or lower battery use.


### Features 

- Limited datatype support: Numerics and IDs 
- Small memory footprint 
- Code & Data seperated 
- Integrates with DOTS
- Uses BURST function pointers to connect to basic functionality in its environment. 
- Seperation of code, data and stack
- SSMD mode, executes multiple script with simular controlflow but different data at once as if they were vectors. **Current no control flow support**
- Interpretation is BURST compatible.
- Unmatched performance. 


### Example
An equation like a = (3 3) * (4 4) + (1.2 1.2); results in only 18 bytes of code, 4 bytes of data and 8 bytes of stack use, resulting in a block of 30 bytes, easily fitting into a single cache line ensuring maximum performce running this as a kernel over large datasets: 

```csharp
# code
a = (3 3) * (4 4) + (1.2 1.2);

# ssmd assembly 
push vector cf1 #154 #153 #153 #063 csref #006 set a expand_v2 3 * expand_v2 4 + pop 

# bytecode 
000| 035 034 064 154 153 153 063 066 006 001 
010| 128 061 087 011 061 088 008 034  
```
Constant values are used in the script, but in ssmd's view, these are parameters, they are just constant for the current run; resulting in optimizations not normally possible like calculating parts of a script only once for the dataset. From version 1.0.5 these will be made availeble as input parameters for ssmd scripts. 


#### Variables 

Variables dont need to be defined although users might want to force their order in the datasegment using input defines.

All data starts out as a float in BLAST and either grows into vectors or gets converted/defined as something else.  

#### Statements 

A statement is: 
- a collection of operations assigned to a variable terminated with a `;`: `a = 1 * 3 + maxa((1 2 3), (5 6 7));` 
- a procedure call: 'procedure_identifier( maxa(1,2,3));`

Control flows can nest statements:

- If Then Else:  `if ( a | b ) then ( c = 1; ) else ( c = 2; );`
- While loop: `while( i < 100) ( i = i + 1;);`
- For loop: `for( i = 0; i < 100; i = i + 1) ( a = a / 4; );` 
- Switch: `switch (a) (case 3: ( a = 2; ) default: ( a = 3;));`

_The intitial language version will demand use of compounds in all situations. Later version may relax on this constraint. _

#### Compounds 

Everything between  `(` and `)` is called a compound, a compound may have several interpretations: 

- A list of statements: `( a = 1; b = 2; c = a * b; );` 
- Structuring of sequences: `a = a + (a | b);`
- A list of parameters: `(a, b, c);`
- A vector definition: `a = (1 2 3 4);`

#### Data Types & Sizes 

There is limited datatype support, this will change in future versions: 

```csharp Unknown: determined at runtime 

full support: NUMERIC, vectorsize 1-4
partial support: BOOL32 

```

##### External Data Access 

BLAST connects to its enviroment in several ways

- data can be communicated through the packagadata of the script by setting up its values
- data can be mapped to a DOTS IComponentData structure or any other segment of memory
- data can be exchanged through functionpointers registered in BLAST connection data from your simulation with the script engine. 

#### Vectors
Vectors may be defined based on all supported datatypes and functions, constant and functions may be mixed but the number of dataelements must be equal for each element defined in the vector. 

1> Defines a, a vector of 2 constants and 1 pop operation popping 1 numeric or id:
` a = (1 pop 2); `

2> Defines b, a vector of 2 constants of size 3 and a pop3:
` b = ((1 2 3) (pop pop pop) (1 2 3)); ` 

- Vectors can be used in all operations that can be used with other variables of the same datatype (numeric, id)
- Due to restrictions set by the project we will not allow unlimited vector length (see arrays), this depends on a function used to decode the opcodes for functions and that in turn depends on the language version (information follows) 
- The minimal support will (in all languageversions) be: size 1, 2, 3 and 4; other sizes are under discussion as the current encoding schema allows for only 8 different lengths (8 differing lengths, not max 8)

#### Language Versions
Different language versions allow the interpretor(s) to differentiate between very distinct outputs depending on compiler settings. 

#### Script Tokens

Arithmetic operators:   `+ - / *`

Boolean operators:      `& | ^ !` 

Boolean evaluators:     `< > <= >= = ! !=`

Assignment:             `=`

Enclosures:             `( )`

Statement terminator:   `;` 

Value seperator:        `,` 

Decimal seperator:      `.` 

Indexer                 `.`  

Identifier: 	          `[a..z][0..9|a..z]*[.|[][a..z][0..9|a..z]*[]]`

Control Flow:           `if then else` 
                        `while | for loops` 
                        `switch case default`
                        

#### Compiler Defines 

The # is used to define constants, input and output(s) and validations. Any sequence not matching `#[define/input/output/validate]` is considered a comment. 

- A `#[definition]` must appear at the start of the line 
- Defines and inputs must appear in the code BEFORE any other code 
- A comment can be started at any point in the line

##### Compiler Define Examples
```csharp
#define   variable  1234
#input    variable  0 4
#output   variable  4 8 
#validate variable  a 123
``` 

All other text that starts with # is a comment and may start at any point of a line, also after `#[definition]`:

```csharp
#input    variable  [offset] [bytesize]    # comment 123
``` 

#### Compiler Settings 

##### PackageMode
Different package modes for different needs: 

- Normal: code, metadata, data and stack combined
```
        [----CODE----|----METADATA----|----DATA----|----STACK----]
                     1                2            3             4  
```
- SSMD: code and metadata seperated from data & stack in 2 seperate segments, stack can usually best be omitted with the `NoStack` option. 
```
        [----CODE----|----METADATA----]       [----DATA----|----STACK----]
                     1                2                    3             4
``` 
- Entity: code is seperated from metadata, data and stack which are mapped onto an IComponentData 
``` 
         [----CODE----]      [----METADATA----|----DATA----|----STACK----]
                      1                       2            3             4
``` 
- Compiler: mode for internal and debugging purposes, this will maintain a node tree and variable overviews.

#### Data Alignment 

When blast encounters the following equation: a = a * b * 4, the depending on alignment or not the following assembly is executed in burst (only important parts are shown)

**Aligned float * float **

To perform the multiplication between 2 variables in a datasegment that is aligned:

<img width="356" alt="mul_loop_indexed_aligned" src="https://user-images.githubusercontent.com/96932314/163287736-420f3b75-1402-4905-b8e8-e18240ae432a.PNG">

**Register float * constant **
The result is multiplied in a register (of the interpretor) with a constant, blast knows to execute the move only once, undependant of the number of records. In future version the ssmd interpretor will call a value constant if its equal acros the input, it can then apply these optmizations each run based on the data given, this is an optimization that would normally be very difficult to cleanly achieve. 

<img width="304" alt="mul_a_constant" src="https://user-images.githubusercontent.com/96932314/163287954-f37dbd27-9fd5-43fa-aa26-ab3e5a32c280.PNG">

The datasegment and stack are setup as arrays of arrays and are said to be aligned when each basepointer of the subarrays has the same offset to the other. If thats not the case we call the data unaligned and blast has to calculate each base index resuling in un-packed instructions but still very fast code:

<img width="332" alt="mul_loop_indexed_unaligned" src="https://user-images.githubusercontent.com/96932314/163288176-e1880f9d-6521-4319-887d-42c6e4be70a2.PNG">

The effect of alignment on processing speed can be seen in sample 10, after all cubes have gotten different states and thus run different scripts, the interpretor gets datasegment arrays with indices skipping because they are for other scripts. It can be up to 3 times slower to work with unaligned datasegments but it very much depends on the script involved. As a programmer you should know this happens and you can compensate by writing|using your code differently if it gives problems. It still is fast and still uses simd instructions in most cases.

#### HPC Compilation

**Not supported in current release**

Allow BLAST to compile the script into c# burst compatible function pointers, this allows native performance for known scripts while keeping the same workflow in decision libraries. This way there is no performance hit running compile time known scripts at runtime in your simulation. Only runtime compiled scripts will take the performance hit of being interpreted. This will allow the developer to create 1 code path and to not worry too much about performance. Note however, for SSMD operation the compiler will still need bytecode as it is not possible to run in single script multiple data mode using native compiled code. 

- an example of use would be updating behaviour or balancing scripts in multiplayer games on server login, a later binary update of the game might provide the same scripts hardcoded in an update without any alteration in code paths for the developer of that game. 

This should void a big drawback of using a scripting engine to do a lot of tasks in a simulation where every millisecond counts.

**Registration of known scripts from code during development:   **

```csharp
/// <summary>
/// design time definition of a script, any derived class with filled code will be precompiled into a burst function
/// </summary>
class BlastScript1 : BlastScript
{
    bs1() {
        Name = "bs_designtime_1";
        Code = @"
            #input position float3 0 0 0
            position = position + random(-0.01, 0.01);
            position = min((100 100 100), max((-100, -100, -100), position));";
    }
};


/// <summary>
/// any string field, decorated with the BlastScriptAttribute will be precompiled during build into a bursted function 
/// </summary>
class BlastScripts
{

    [BlastScript(Name = "bs_designtime_2")]
    const string bs2 = @"
            #input position float3 0 0 0
            position = position + random(-0.01, 0.01);
            position = min((100 100 100), max((-100, -100, -100), position));";


}
```


#### TLS - PackageOption.PackageNoStack
Dont allocate package memory for stacks, instead use the interpretor's stack. When processing many data records in ssmd mode then memory becomes a serious limitation. If the script is small and the data is small they should be packeged together easily fitting many in cpu cache. When there is more data at some point the cpus cache will be the limiting factor, especially when running multiple threads. If the stack is mapped to the stackmemory of the interpretor the cpu will swap less memory in and out when processing large amounts of records. This is easily seen in the following video (a .net build) https://youtu.be/FnEtQ0tWAto As soon as the stack spans multiple cache lines it becomes very benificial to use the threads stack allowing it to make full use of multithreading. Note that for very small scripts this actually hurts performance as code and data or not on the same cacheline anymore (usually above 64byte|128bytes)


#### Most math functions built in 

Built in functions are directly encoded in opcodes and are made available to blast in the form of a BlastScriptAPI class. Several math functions have been built in and many other functions will follow. 

See (Language Reference)[LanguageReference.md] for an overview of all built in functions. 

```csharp
   f = rsqrt(1.1); 
   g = sqrt(2); 
   h = max(f, g);
``` 

#### External Function Definitions

Blast can call external functions that have been burst compiled and registered in the blast api used during compilation and execution.

An external function example in c#

```csharp
	// the declaration:
	[BurstCompatible]
        static public float ExternalTest(IntPtr blast, IntPtr env, IntPtr caller, float a, float b)
        {
            return a * b; 
        }
	
	// the registration: 
	Blast.ScriptAPI.Register(ExternalTest);
```

Functions can also be identified with BlastFunctionAttributes, blast will enumerate these on startup and registers them as external function calls. 

``` 	
        [BurstCompatible]
        static public float AttributeTest(float b)
        {
            return b * 2; 
        }
```

#### Inline Functions | Macros

Blast also allows the use of inlined functions, albeit with restriction imposed due to blasts memory requirements: 

```csharp
function a(a, b, c)
(
	return a + b + c;	   
)

p0 = 1; 
p1 = 2;
p2 = 3; 

p = a(p1, p2, p3); 
```

The function call is inlined into the callsite, this means there are several limitation or advantages depending on how its used:

- Inlined functions share global scope, only function parameters are scoped to the function defining them.
- Inlined functions may not declare new variables, if you need extra variables, declare them as input, output or as normal variable in the main body.
- Vector size and datatype is propagated, ie, an inlined function is generic, unless the function uses variables from the globalscope that might force vectorsizes onto operations. 
- Inlined functions dont use additional stackmemory due to these restrictions and the fact they are inlined (no jumps, no register pushes to stack, no declarations)

Inline functions could should be viewed as shortcut-macros in algorithms, larger reusable code blocks should be added as external function calls for maximum performance as nativecode will always be faster then interpreted bytecode. 


#### Parameters 
Parameters are identifiers or sequences of operations seperated by a `,` and may be:

- values 
- operation sequences resulting in values
- other functions
- vectors

##### Parameter Indexers
All things resulting in a value can be indexed:

```csharp
	a = 1;     	# declares storage
	b = (4 5 6 7); 
	a = b.x; 
	b.x = 7; 
	
	debug(a);  	# logs 4 
	debug(b);  	# logs 7 5 6 7
```  

Currently the maximum vectorsize in datatypes is 4, so the only allowed indexers are:

`.x|y|z|w and .r|g|b|a`

This will change in future versions.


#### Functioncall Examples 

```csharp
 a = max (1, 2);
 a = max ((1 1), (2 2));
 a = max (a, 1, max(a, 2));
 a = max (a - b, a + max(a, 2)); 
```

### Example Scripts

Validation script as used in some tests: 
```csharp
#define result_1 11111
#define result_2 22222

b = b * 1 * 1 * 1 * (1 / 10) * 1;

a = 1 + 1;
b = 1 * -2 * 3 * 4; 
c = 1 * (2 * 3 / 4) * 5;      # 1.5 * 5 = 7.5

if(a = 1) then ( d = 122 ) else ( d = 100 );

while(a <= d) 
(
    a = a + 1; 
    b = b * 1 * 1 * 1 * 1 / 10 * 1;     
)

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
 
f = 1.1;
g = sqrt(2);  
h = max(f, g);

for(i = 5; i < 15; i = i + 1)
(
	h = h + 1; 
)

#validate e 11111                 
#validate a 101              
#validate c 7.5
#validate h 11.4142       
```


Implementation of a state in a statemachine
```csharp
#
# HOVERTANK STATEMACHINE
#
### Define possible states

#define     IDLE	1
#define     EXPLORE     2
#define     FORTIFY     3
#define     ATTACK	4 
#define     EVADE       5 
#define     EXPLODE     6
#define     DESTROYED   7

# this directly maps to an IComponentData of 5 floats:
#input current_state    0  4
#input explore_cell     4  4  
#input attack_target    8  4
#input counter         12  4
#input current_cell_id 16  4

# every 60 frames:  check for a target in range 
counter = counter + 1;
if(counter < 60) then 
( 
	current_state = EXPLORE; 
	return;
)

counter = 0;
attack_target = FindClosestTarget(); 

# if there is a target attack it
if(attack_target >= 0) then 
(
	current_state = ATTACK; 
	StopMovement();
	return; 
)

# otherwise keep exploring 
current_state = EXPLORE; 

# no current explore target -> select new target and start moving to it 
if(explore_cell <= 0) then
(
	explore_cell = ExploreIsland(); 
	if(explore_cell > 0) then ( MoveToCellId(explore_cell); );
)

current_cell_id = GetCurrentCellId(); 

# if the cell we are exploring became explored -> find another target 
cell_is_explored = CellIsExplored(explore_cell); 
if(cell_is_explored = 1) then 
(
          explore_cell = current_cell_id; 
)

# reached target of exploration or cell already explored -> select new target 
if(explore_cell = current_cell_id) then
(
          explore_cell = ExploreIsland(); 
	if(explore_cell > 0) then ( MoveToCellId(explore_cell); ) 
)

# no target to explore, nothing to attack -> fortify until other goals apply
if(explore_cell < 0) then
(
	current_state = FORTIFY; 
	StopMovement();
)

```


Various operations for testing:
```csharp

a = 1 * -2;						
b = -1 * 2;						
c = a / b;						
d = c * 100;					
e = 1 + 2 * 2; 					
f = 1 + 2 * 2 + 5;				
g = 1 + 2 / 6;					    
h = 1 + -2 / 6;					
i = 1 - 2 * 2 + 5;				 
j = 1 + 2 * 2 - 5;				 
k = 1 +-2 * 2 + 5;				 
l = 1 + 1 + 1;                  # should all optimize to adda or suba
m = 1 - 1 - 1 - 1; 
n = 1 + 1 + 1 + 1 + 1;
o = 1 - 1 - 1 - 1 - 1 + 1 + 1;  # suba and adda 
t = 1 + 1 + 1 + 1 + 1 + 1 + 1;  # 1 more then in patterns  
p = 2 * 2 * 2;		  # should all optimize to mula
q = 2 * 2 * 2 * 2;	
r = 2 * 2 * 2 / 2 * 2;	  # division is inverted by analyser, optimizer converts to mula
s = a * e * j * g * v / 2; 	    
u = 2 * 2 * 2 * 2 * 2 * 2 * 2;  
v = 2 / 2 / 2 / 2 / 2 / 2; 	
w = a / b / c / d;            
x = a * (b / 2) * 2;
y = (a * b) * 2;
z = (a * b) + b * (a + b);
 
aa = 1 + 1 * (1 / 2) * 2;	
ab = 2 * (2 * 2 * 2) * 2;  
ac = 2 - 2 - 2 - 2 - 2 - 2; 
ad = 1 & -2 | 1;        	
ae = 1 & 2 & 3 & 4 & 5;	
ag = 1 * 10 * 3 * (3 + 4 * 2);
```

Vector example with some script debuging features and insights into BLAST's stack usage, it uses less data and code bytes while keeping execution flat for the interpretation allowing it to use less memory on the target cpu. Note difference between ssmd and normal packaging in code and datasegment, in normal mode constant data is allocated in the datasegment while for ssmd constant data is inlined optimizing for many executions of the same code with different data. 
```csharp

 a = maxa((1 2 3), (4 5 6), (7 8 9));
  
 debug(a); 
 debugstack(); 

# compiler node tree (PackageMode == normal|ssmd)
# 
#    root of 6 
#       function push 
#           vector compound statement of 3 
#             constant parameter 7 
#             constant parameter 8 
#             constant parameter 9 
#          /
#       /
#       function push 
#           vector compound statement of 3 
#             constant parameter 4 
#             constant parameter 5 
#             constant parameter 6 
#          /
#       /
#       function push 
#           vector compound statement of 3 
#             constant parameter 1 
#             constant parameter 2 
#             constant parameter 3 
#          /
#       /
#       assignment of a 
#          function maxa 
#             function pop 
#             function pop 
#             function pop 
#          /
#       /
#       compound statement of 1 
#          function debug 
#             parameter a 
#          /
#       /
#       compound statement of 1 
#          function debugstack 
#       /
#    /
# 
# 
# Packagemode == Normal:
# 
# push vector  51 7 8 9 push vector  51 4 5 6 push vector  51 1 2 3 setf a  50 | pop pop pop nop 
#
# 000| 033 051 131 089 132 033 051 088 129 130 
# 010| 033 051 085 086 087 003 128 050 013 032 
# 020| 032 032 000 
# 
# Blast.Debug - codepointer: 29, id: 128, NUMERIC: 9,00, vectorsize: 1
# 
# DATA  0 = 9   1  Numeric        // [0] == numeric[1] assigned by var a 
# DATA  1 = 5   1  Numeric        // [1] == 5 => numeric data, not in constants  ** NOTE HOW VECTORS USE STACK MEMORY **
# DATA  2 = 6   1  Numeric        // [2] == 6 => numeric data, not in constants 
# DATA  3 = 7   1  Numeric        // [3] == 7 => numeric data, not in constants 
# DATA  4 = 9   1  Numeric        // [4] == 8 => numeric data, not in constants    
#
#
#
# Packagemode == SSMD:
#
# push vector  51 cf1h #224 #064 8 cf1h #016 #065 push vector  51 4 cf1h #160 #064 cf1h #192 #064 push vector  51 1 2 3 setf a  50 | pop pop pop nop 
#
# 000| 033 051 064 224 064 089 064 016 065 033 
# 010| 051 088 064 160 064 064 192 064 033 051 
# 020| 085 086 087 003 128 050 013 032 032 032 
# 030| 000 
#
# DATA  0 = 9   1  Numeric        // [0] == numeric[1] assigned by var a 

```



Example output for nested functions, the results are pushed and popped when needed. This ensures no recursion or stacking of register data during interpretation. The script code `debug(max((1 + 2), 2)); ` or `debug(max(1 + 2, 2));` results int the following output:
```csharp
    

   root of 3 
      function pushc 
         constant parameter 1 
         operation Add 
         constant parameter 2 
      /
      function pushf 
         function max 
            function pop 
            constant parameter 2 
         /
      /
      function debug 
         function pop 
      /
   /

000| push compound 1 + 2 nop push function max ^ pop 2 
010| debug pop nop 

000| 030 085 002 086 000 029 042 009 025 086 
010| 255 253 025 000 

Blast.Debug - codepointer: 12, id: 25, NUMERIC: 3,00, vectorsize: 1
```

Example output for nested vector operations with negative constants encoded in bytecode, although the output is flattened into 6 statements which seems more work its actually faster to execute because by pushing stuff on the stack the datatype becomes fixed for the interpretor and it wont need to grow vectors value by value, also not processing nested compounds but instead executing them in a linear fashion ensures less function stack use for the code running the interpretation (more constant memory). 

**Note that for this test the optimizer is disabled as it removes unneeded compounds resulting in less statements to execute but a less usefull test for flattening. **

```csharp
   [InlineData("a = ((2 2 2 2) * (2, -2 2 2)) * (4 4 4 4);", 16)]

   root of 6 
       vector[4]function pushv 
         constant parameter 2 
         constant parameter 2 
         constant parameter 2 
         constant parameter 2 
      /
      function pushc 
         operation Substract 
         constant parameter 2 
      /
       vector[4]function pushv 
         constant parameter 2 
         function pop 
         constant parameter 2 
         constant parameter 2 
      /
       vector[4]function pushc 
          vector[4]function pop 
         operation Multiply 
          vector[4]function pop 
      /
       vector[4]function pushv 
         constant parameter 4 
         constant parameter 4 
         constant parameter 4 
         constant parameter 4 
      /
       vector[4]assignment of a 
          vector[4]function pop 
         operation Multiply 
          vector[4]function pop 
      /
   /
   
000| push vector  68 2 2 2 2 push compound - 2 nop 
010| push vector  68 2 pop 2 2 push compound pop * pop 
020| nop push vector  68 4 4 4 4 set a pop 
030| * pop nop nop 

000| 026 068 086 086 086 086 030 003 086 000 
010| 026 068 086 025 086 086 030 025 005 025 
020| 000 026 068 088 088 088 088 001 128 025 
030| 005 025 000 000 


```

#### Basic optimizer features: 

This demonstrates inverse replacements on division by constants followed by remapping the multiplication sequence into a function call.

Input code segment: `a = 1 / 2.1 / 3.2 / 4.3;`

Resulting nodes and bytecode: 

```csharp 
   root of 1 
      assignment of a 
         function mula 
            constant parameter 1 
            constant parameter 0,4761905 
            constant parameter 0,3125 
            constant parameter 0,23255813 
         /
      /
   /

000| set a mula yield 1 0,4761905 0,3125 0,23255813 nop

000| 001 128 033 017 085 129 130 131 000 
``` 

For now the optimizer will only look at single nodes and will mainly perform replacements of operation sequences. A string of additions is better executed as a function where more information is known about its result and it reduces control flow in the interpretor. 


