# Blast
##### Provides a fast scripting language for running statemachines or other decision making processes from bursted code in unity.

Scripts can be compiled at runtime from any text source and they can be store in a repository. Any script known at compiletime can also be transpiled into burst c# function pointers for optimal performance and seamless integration of fast native code and scripted segments. This takes away the complexity of seperate code paths usually used for optimal performance and lets the developer focus on other parts. This also means that the performance penalty of script can be completely mitigated if its known at compile time without changes to the code base other then autogenerated code from blast. The game could download scripts between binary updates to provide updated responses and then after releasing an updated game assembly use those same scripts with the same calling code but then backed by pure bursted code.

## SSMD
### Single Script Multiple Data

In many large scale simulations many scripts are mostly the same but with different data. BLAST can execute those with the control flow inverted, meaning that it in essence performs the SIMD equivelent of scripting languages, each operation will translate in a vector operation easily compiled to beautiful packed assembly. This can result in script running faster then native code dueue to the ways memory is forced to be and execution is performed. Usually this kind of optimization is not simply possible in real-life situations with compiled code. In SSMD mode, BLAST can handle scripts faster then native code in single execution. It shows how it becomes possible to optimize otherwise hard to optimize parts, especially if they were entered by a user in an online game were there is no control. 

### Features 

- Limited datatype support: Numerics and IDs 
- Small memory footprint 
- Code & Data seperated 
- Integrates with DOTS
- Uses BURST function pointers to connect to basic functionality in its environment. 
- Seperation of code, data and stack
- Editor/Build time functionality to convert scripts into bursted function pointers with no difference in usage to the developer but with native performance.
- SSMD mode, executes multiple script with simular controlflow but different data at once as if they were vectors
- Hybrid register/stackbased interpretor 
- Interpretation is BURST compatible.
- Unmatched performance. 

<img width="80%" alt="BLAST with BURST" src="https://user-images.githubusercontent.com/96932314/149854610-540e2ae4-2cb8-4502-8db4-b3b3ed9a4c71.PNG">

### Code Structure 

#### Variables 

Variables dont need to be defined although users might want to force usage of the ID datatype. All data starts out as a float in BLAST and either grows into vectors or gets converted/defined as an ID. For blast its assumed that float is the prefered datatype.

Currently a variable is promoted to an id by use of a function: `a_as_id = ID64;  a_as_id = ID64(value); `, functions in blast may convert datatypes and allow us to cleanly configure datatypes used outside the interpretor. Leveraging this we could release float or ID only interpretors for maximum speed in the future. 

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

There is limited datatype support: 

```Unknown: determined at runtime 

Numeric: 1.0 etc

ID: Integers

Vectors:  ID(n) and NUMERIC(n) up until n = 16, 
          id(3)       => (1 2 3)
          NUMERIC(3)  =>  (1.2 2.3 2.45)
```

##### External Data Access 

BLAST connects to its enviroment in several ways

- data can be communicated through the packagadata of the script by setting up its values
- data can be mapped to a DOTS IComponentData structure
- data can be exchanged through functionpointers registered in BLAST connection data from your simulation with the script engine. 

##### No Native Array Support

BLAST will not directly support arrays or pointers as datatypes. Instead it expects users to create an api to their simulation to query by the script. Its straightforward to devise functions in unity and connect them to blast and to end up like so: 

```
 while(i < get_actor_count())
 (
     m1 = get_actor_data(i); 
 )

```

_ This will also allow us to cache data efficiently in future versions. _


#### Vectors
Vectors may be defined based on all supported datatypes and functions, constant and functions may be mixed but the number of dataelements must be equal for each element defined in the vector. 

1> Defines a, a vector of 2 constants and 1 pop operation popping 1 numeric or id:
` a = (1 pop 2); `

2> Defines b, a vector of 2 constants of size 3 and a pop3:
` b = ((1 2 3) (pop pop pop) (1 2 3)); ` 

- Vectors can be used in all operations that can be used with other variables of the same datatype (numeric, id)
- Due to restrictions set by the project we will not allow unlimited vector length (see arrays), this depends on a function used to decode the opcodes for functions and that in turn depends on the language version (information follows) 
- The minimal support will (in all languageversions) be: size 1, 2, 3 and 4; other sizes are under discussion as the current encoding schema allows for only 8 different lengths (8 differing lengths, not max 8)

##### Vector mapping assumptions
Vectors map automatically to matrices of the same element size: n(9) => m(3x3), n(12) => m(3x4) | m(4x3) etc. 

#### Language Versions
Different language versions allow the interpretor(s) to differntiate between very distinct outputs depending on compiler settings. 


##### BS1 



##### BS2



##### HPC



#### Script Tokens

Arithmetic operators:   `+ - / *`

Boolean operators:      `& | ^ !` 

Boolean evaluators:     `< > <= >= = ! !=`

Ternary operator:       `[condition] ? [true] : [false]`   **BS2**

Assignment:             `=`

Enclosures:             `( )`

Statement terminator:   `;` 

Value seperator:        `,` 

Decimal seperator:      `.` 

Indexer                 `.`  

IndexOpen               `[`   **BS2**

IndexClose              `]`   **BS2**

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
``` 
#define   variable  1234
#input    variable  0 4
#output   variable  4 8 
#validate variable  a 123
``` 

All other text that starts with # is a comment and may start at any point of a line, also after `#[definition]`:

``` 
#input    variable  [offset] [bytesize]    # comment 123
``` 

#### Compiler Settings 

##### Optimizer 
Enable the optimizing functions of the compiler:
- for now only bytecode pattern recognition is used
- 
##### PackageMode
Different package modes for different needs: 

- Normal: code, metadata, data and stack combined
- SSMD: code and metadata seperated from data & stack in 2 seperate segments, stack can usually best be omitted with the `NoStack` option. 
- Entity: code is seperated from metadata, data and stack which are mapped onto an IComponentData 
- Compiler: mode for internal and debugging purposes, this will maintain a node tree and variable overviews.

##### HPC Compilation
Allow BLAST to compile the script into c# burst compatible function pointers, this allows native performance for known scripts while keeping the same workflow in decision libraries. This way there is no performance hit running compile time known scripts at runtime in your simulation. Only runtime compiled scripts will take the performance hit of being interpreted. This will allow the developer to create 1 code path and to not worry too much about performance. Note however, for SSMD operation the compiler will still need bytecode as it is not possible to run in single script multiple data mode using native compiled code. 

- an example of use would be updating behaviour or balancing scripts in multiplayer games on server login, a later binary update of the game might provide the same scripts hardcoded in an update without any alteration in code paths for the developer of that game. 

This should void a big drawback of using a scripting engine to do a lot of tasks in a simulation where every millisecond counts.

##### NoStack 
Dont allocate package memory for stacks, instead uses interpretor's stack.

#### Data Access 

##### Direct Data|Stack Access

##### Mapping to IComponentData

##### Communication through external fucntions


#### Interpretor 

##### SSMD Operation

#### Error Handling 



### Example Scripts

Validation script as used in some tests: 
```
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
```
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
```

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

Vector example with some script debuging features:
```

 a = maxa((1 2 3), (4 5 6), (7 8 9));
  
 debug(a); 
 debugstack(); 

# compiler node tree
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
# 000  024 018 131 089 132 019 024 018 088 129 
# 010  130 019 024 018 085 086 087 019 001 128 
# 020  049 013 025 025 025 000 018 255 244 128 
# 030  019 018 255 243 019 000      
# 
# Blast.Debug - codepointer: 29, id: 128, NUMERIC: 9,00, vectorsize: 1
# 
# DATA  0 = 9   1  Numeric        // [0] == numeric[1] assigned by var a 
# DATA  1 = 5   1  Numeric        // [1] == 5 => numeric data, not in constants  
# DATA  2 = 6   1  Numeric        // [2] == 6 => numeric data, not in constants 
# DATA  3 = 7   1  Numeric        // [3] == 7 => numeric data, not in constants 
# DATA  4 = 9   1  Numeric        // [4] == 8 => numeric data, not in constants    
```
