# BLAST

<table>
<tbody>
<tr>
<td><a href="#blast">Blast</a></td>
<td><a href="#blast_operation">blast_operation</a></td>
</tr>
<tr>
<td><a href="#blastexecute">BlastExecute</a></td>
<td><a href="#blastcompileroptions">BlastCompilerOptions</a></td>
</tr>
<tr>
<td><a href="#blastcompilerstagetype">BlastCompilerStageType</a></td>
<td><a href="#blastenginedata">BlastEngineData</a></td>
</tr>
<tr>
<td><a href="#blastenginedataptr">BlastEngineDataPtr</a></td>
<td><a href="#blasterror">BlastError</a></td>
</tr>
<tr>
<td><a href="#blastlanguageversion">BlastLanguageVersion</a></td>
<td><a href="#blastmetadatastack">BlastMetaDataStack</a></td>
</tr>
<tr>
<td><a href="#blastpackagedata">BlastPackageData</a></td>
<td><a href="#blastpackageflags">BlastPackageFlags</a></td>
</tr>
<tr>
<td><a href="#blastpackagemode">BlastPackageMode</a></td>
<td><a href="#blastruntimeversions">BlastRuntimeVersions</a></td>
</tr>
<tr>
<td><a href="#blastscript">BlastScript</a></td>
<td><a href="#blastscriptapi">BlastScriptAPI</a></td>
</tr>
<tr>
<td><a href="#blastscriptfunction">BlastScriptFunction</a></td>
<td><a href="#blastscriptfunctionflag">BlastScriptFunctionFlag</a></td>
</tr>
<tr>
<td><a href="#blastscriptfunctioninfo">BlastScriptFunctionInfo</a></td>
<td><a href="#blastscriptpackage">BlastScriptPackage</a></td>
</tr>
<tr>
<td><a href="#blastscripttokendefinition">BlastScriptTokenDefinition</a></td>
<td><a href="#blastssmddatastack">BlastSSMDDataStack</a></td>
</tr>
<tr>
<td><a href="#blastvariable">BlastVariable</a></td>
<td><a href="#blastvariabledatatype">BlastVariableDataType</a></td>
</tr>
<tr>
<td><a href="#blastvariablemapping">BlastVariableMapping</a></td>
<td><a href="#blastvectorsizes">BlastVectorSizes</a></td>
</tr>
<tr>
<td><a href="#blastvectortypes">BlastVectorTypes</a></td>
<td><a href="#castutil">CastUtil</a></td>
</tr>
<tr>
<td><a href="#blastcompiler">BlastCompiler</a></td>
<td><a href="#blastintermediate">BlastIntermediate</a></td>
</tr>
<tr>
<td><a href="#compilationdata">CompilationData</a></td>
<td><a href="#message">Message</a></td>
</tr>
<tr>
<td><a href="#cscompilationdata">CSCompilationData</a></td>
<td><a href="#hpccompilationdata">HPCCompilationData</a></td>
</tr>
<tr>
<td><a href="#iblastcompilationdata">IBlastCompilationData</a></td>
<td><a href="#node">node</a></td>
</tr>
<tr>
<td><a href="#nodetype">nodetype</a></td>
<td><a href="#blastanalysis">BlastAnalysis</a></td>
</tr>
<tr>
<td><a href="#blastbytecodecompiler">BlastBytecodeCompiler</a></td>
<td><a href="#blastbytecodeoptimizer">BlastBytecodeOptimizer</a></td>
</tr>
<tr>
<td><a href="#blastflatten">BlastFlatten</a></td>
<td><a href="#blasthpccompiler">BlastHPCCompiler</a></td>
</tr>
<tr>
<td><a href="#blasthpcstackresolver">BlastHPCStackResolver</a></td>
<td><a href="#blastjumpresolver">BlastJumpResolver</a></td>
</tr>
<tr>
<td><a href="#blastoptimizer">BlastOptimizer</a></td>
<td><a href="#blastpackaging">BlastPackaging</a></td>
</tr>
<tr>
<td><a href="#blastparameteranalysis">BlastParameterAnalysis</a></td>
<td><a href="#blastparser">BlastParser</a></td>
</tr>
<tr>
<td><a href="#blastprecompilecleanup">BlastPreCompileCleanup</a></td>
<td><a href="#blasttokenizer">BlastTokenizer</a></td>
</tr>
<tr>
<td><a href="#blasttransform">BlastTransform</a></td>
<td><a href="#imbytecode">IMByteCode</a></td>
</tr>
<tr>
<td><a href="#imbytecodelist">IMByteCodeList</a></td>
<td><a href="#imjumplabel">IMJumpLabel</a></td>
</tr>
<tr>
<td><a href="#compiletimeblastscript">CompileTimeBlastScript</a></td>
<td><a href="#coreapi">CoreAPI</a></td>
</tr>
<tr>
<td><a href="#iblastcompilerstage">IBlastCompilerStage</a></td>
<td><a href="#blastinterpretor">BlastInterpretor</a></td>
</tr>
<tr>
<td><a href="#blastreflect">BlastReflect</a></td>
<td><a href="#blastscriptregistry">BlastScriptRegistry</a></td>
</tr>
<tr>
<td><a href="#reservedblastscriptfunctionids">ReservedBlastScriptFunctionIds</a></td>
<td><a href="#blastssmdinterpretor">BlastSSMDInterpretor</a></td>
</tr>
<tr>
<td><a href="#stringbuildercache">StringBuilderCache</a></td>
</tr>
</tbody>
</table>


## Blast

Blast Engine


## blast_operation

instruction set

### add

Operatations from add until not_equals MUST be in sequence for quick matches

### NSS.Blast.Blast.API

the current set of script accessible functions, check OwnScriptAPIMemory to see if this instance of blast is the owner of the memory used in the API


## BlastExecute

delegate used to execute scripts

| Name | Description |
| ---- | ----------- |
| scriptid | *Unknown type*<br>the id of the script |
| p_stack | *Unknown type*<br>the stack pointer |
| data | *Unknown type*<br>environment data |
| caller | *Unknown type*<br>caller data |

#### Returns



### NSS.Blast.Blast.Comment

the comment character

### NSS.Blast.Blast.CompileIntoDesignTimeRegistry(blast, script, script_directory)

compile the script into the designtime registry

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br>blast engine data |
| script | *NSS.Blast.BlastScript*<br>the script to compile |
| script_directory | *System.String*<br>the directory to place the script in |

#### Returns

true on success

### NSS.Blast.Blast.Create(api, allocator)

create a new instance of blast using a customized api

| Name | Description |
| ---- | ----------- |
| api | *NSS.Blast.BlastScriptAPI*<br>function api to use |
| allocator | *Unity.Collections.Allocator*<br>allocator to use, dont use temp allocator for bursted code |

#### Returns

the blast struct|class should refactor TODO

### NSS.Blast.Blast.Create(allocator)

create a new instance of BLAST use the core scriptfunction api

| Name | Description |
| ---- | ----------- |
| allocator | *Unity.Collections.Allocator*<br>allocator to use, dont use temp allocator for bursted code |

#### Returns

the blast struct

### NSS.Blast.Blast.data

Pointer to native memory holding data used during interpretation: - function pointers - constant data

### NSS.Blast.Blast.Destroy

release all memory allocated by this instance of blast

### NSS.Blast.Blast.Engine

IntPtr to global data object used by interpretor, it holds references to constant values and function pointers

### NSS.Blast.Blast.Execute(blast, package, environment, ssmd_data, ssmd_count)

Execute a Package in ssmd mode

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr@*<br> |
| package | *NSS.Blast.BlastPackageData@*<br>the package data to execute |
| environment | *System.IntPtr*<br>the environment data to use |
| ssmd_data | *System.IntPtr*<br>data for each entity|script|component |
| ssmd_count | *System.Int32*<br>the number of data elements |

#### Returns

succes or an error code

### NSS.Blast.Blast.Execute(blast, package, environment, caller)

Execute a Package

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr@*<br>Blast engine data |
| package | *NSS.Blast.BlastPackageData@*<br>the package data to execute |
| environment | *System.IntPtr*<br>the environment data to use |
| caller | *System.IntPtr*<br> |

#### Returns

succes or an error code

### NSS.Blast.Blast.Execute(package, ssmd_data, ssmd_count)

Execute a Package in ssmd mode

| Name | Description |
| ---- | ----------- |
| package | *NSS.Blast.BlastPackageData@*<br>the package data to execute |
| ssmd_data | *System.IntPtr*<br>data for each entity|script|component |
| ssmd_count | *System.Int32*<br>the number of data elements |

#### Returns

succes or an error code

### NSS.Blast.Blast.Execute(package, environment, ssmd_data, ssmd_count)

Execute a Package in ssmd mode

| Name | Description |
| ---- | ----------- |
| package | *NSS.Blast.BlastPackageData@*<br>the package data to execute |
| environment | *System.IntPtr*<br>the environment data to use |
| ssmd_data | *System.IntPtr*<br>data for each entity|script|component |
| ssmd_count | *System.Int32*<br>the number of data elements |

#### Returns

succes or an error code

### NSS.Blast.Blast.Execute(package, environment, caller)

Execute a Package

| Name | Description |
| ---- | ----------- |
| package | *NSS.Blast.BlastPackageData@*<br>the package data to execute |
| environment | *System.IntPtr*<br>the environment data to use |
| caller | *System.IntPtr*<br>the caller data to use |

#### Returns

succes or an error code

### NSS.Blast.Blast.Execute(package, environment)

Execute a Package

| Name | Description |
| ---- | ----------- |
| package | *NSS.Blast.BlastPackageData@*<br>the package data to execute |
| environment | *System.IntPtr*<br>the environment data to use |

#### Returns

succes or an error code

### NSS.Blast.Blast.Execute(package)

Execute a Package

| Name | Description |
| ---- | ----------- |
| package | *NSS.Blast.BlastPackageData@*<br>the package data |

#### Returns

succes or an error code

### NSS.Blast.Blast.Execute(package, ssmd_data, ssmd_count)

Execute a Package in ssmd mode

| Name | Description |
| ---- | ----------- |
| package | *NSS.Blast.BlastScriptPackage@*<br>the package data to execute |
| ssmd_data | *System.IntPtr*<br>data for each entity|script|component |
| ssmd_count | *System.Int32*<br>the number of data elements |

#### Returns

succes or an error code

### NSS.Blast.Blast.Execute(package, environment, ssmd_data, ssmd_count)

Execute a Package in ssmd mode

| Name | Description |
| ---- | ----------- |
| package | *NSS.Blast.BlastScriptPackage@*<br>the package data to execute |
| environment | *System.IntPtr*<br>the environment data to use |
| ssmd_data | *System.IntPtr*<br>data for each entity|script|component |
| ssmd_count | *System.Int32*<br>the number of data elements |

#### Returns

succes or an error code

### NSS.Blast.Blast.Execute(package, environment, caller)

Execute a Package

| Name | Description |
| ---- | ----------- |
| package | *NSS.Blast.BlastScriptPackage@*<br>the package data to execute |
| environment | *System.IntPtr*<br>the environment data to use |
| caller | *System.IntPtr*<br>the caller data to use |

#### Returns

succes or an error code

### NSS.Blast.Blast.Execute(package, environment)

Execute a Package

| Name | Description |
| ---- | ----------- |
| package | *NSS.Blast.BlastScriptPackage@*<br>the package data to execute |
| environment | *System.IntPtr*<br>the environment data to use |

#### Returns

succes or an error code

### NSS.Blast.Blast.Execute(package)

Execute a Package

| Name | Description |
| ---- | ----------- |
| package | *NSS.Blast.BlastScriptPackage@*<br>the package data to execute |

#### Returns

succes or an error code

### NSS.Blast.Blast.GetBlastOperationFromToken(token)

get the corresponding operation opcode from a given script token

| Name | Description |
| ---- | ----------- |
| token | *NSS.Blast.BlastScriptToken*<br>the script token |

#### Returns

corresponding opcode

### NSS.Blast.Blast.GetConstantValue(op)

get the constant numeric value of the operation

| Name | Description |
| ---- | ----------- |
| op | *NSS.Blast.blast_operation*<br>the operation to return the constant for |

#### Returns

a constant float value

### NSS.Blast.Blast.GetConstantValueOperation(value, constant_epsilon)

get the script_op belonging to a constant value, eiter by name or value

| Name | Description |
| ---- | ----------- |
| value | *System.String*<br>the value to match |
| constant_epsilon | *System.Single*<br>the epsilon to use matching constant values |

#### Returns

nop on no match, nan of not a string match and no float, operation on match

### NSS.Blast.Blast.GetNamedSystemConstantValue(System.String)

get the value of a named system constant

### NSS.Blast.Blast.GetReadableByteCode(bytes, length)

get somewhat readable assembly from bytes

| Name | Description |
| ---- | ----------- |
| bytes | *System.Byte*@*<br> |
| length | *System.Int32@*<br> |

#### Returns



### NSS.Blast.Blast.GetSequenceOperation(NSS.Blast.blast_operation)

get the function for a sequence of op, add -> adda

### NSS.Blast.Blast.HasSequenceOperation(NSS.Blast.blast_operation)

return if there is a sequence function for the operation

### NSS.Blast.Blast.Intermediate(blast, script, options)

compile the compiler intermediate

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br>blast engine data |
| script | *NSS.Blast.BlastScript*<br>script |
| options | *NSS.Blast.BlastCompilerOptions*<br>compiler options |

#### Returns



### NSS.Blast.Blast.InvalidNumeric

the value used for invalid numerics

### NSS.Blast.Blast.IsCreated

true if the structure is initialized and memory is allocated

### NSS.Blast.Blast.IsError(res)

return if an error (!yield and !success)

| Name | Description |
| ---- | ----------- |
| res | *NSS.Blast.BlastError*<br> |

#### Returns



### NSS.Blast.Blast.IsJumpOperation(op)

check if the operation is a jump (jz, jnz, jump, jump_back)

| Name | Description |
| ---- | ----------- |
| op | *NSS.Blast.blast_operation*<br>operation to check |

#### Returns

true if a jump

### NSS.Blast.Blast.IsNamedSystemConstant(System.String)

check if name matches a named system constant like 'PI' or 'NaN'

### NSS.Blast.Blast.IsSuccess(NSS.Blast.BlastError)

return if an error code actually means success

### NSS.Blast.Blast.MaximumFunctionNameLength

the maximum length of a function name in number of ASCII characters

### NSS.Blast.Blast.mt_lock

simple object/lock method for some threadsafety

### NSS.Blast.Blast.OwnScriptAPIMemory

true if memory is owned by this instance of blast and should be destroyed with it

### NSS.Blast.Blast.Package(blast, script, options)

Compile and package script code

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br>blast engine data |
| script | *NSS.Blast.BlastScript*<br>script code to compile |
| options | *NSS.Blast.BlastCompilerOptions*<br>compiler options |

#### Returns

the code packaged and ready to execute

### NSS.Blast.Blast.Package(blast, code, options)

Compile and package script code

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br>blast engine data |
| code | *System.String*<br>script code to compile |
| options | *NSS.Blast.BlastCompilerOptions*<br>compiler options |

#### Returns

the code packaged and ready to execute

### NSS.Blast.Blast.Package(script, options)

Compile and package the script

| Name | Description |
| ---- | ----------- |
| script | *NSS.Blast.BlastScript*<br>the script to compile |
| options | *NSS.Blast.BlastCompilerOptions*<br>compiler options |

#### Returns

the blastscript package

### NSS.Blast.Blast.Package(code, options)

Complile the code and package into blastscriptpackage

| Name | Description |
| ---- | ----------- |
| code | *System.String*<br>the script code |
| options | *NSS.Blast.BlastCompilerOptions*<br>compiler options |

#### Returns

the blastscript package

### NSS.Blast.Blast.Scripts

Enumerates all scripts known by blast

### NSS.Blast.Blast.StackFillPattern

The fill pattern for stack on initialize, easier to spot bugs if stack is filled with a pattern instead of zeros or random which might have different causes, something bugged setting all bytes to 101 should be very suspicious

### NSS.Blast.Blast.Tokens

defines tokens that can be used in script

### NSS.Blast.Blast.ValueOperations

list all value operations, these operations directly encode constant values -> burst should be able to access this if needed..

### NSS.Blast.Blast.VisualizeTokens(tokens, idx, idx_max)

visualize a list of tokens and identifiers into a somewhat readable string

| Name | Description |
| ---- | ----------- |
| tokens | *System.Collections.Generic.List{System.Tuple{NSS.Blast.BlastScriptToken,System.String}}*<br>the tuples with token and identifier |
| idx | *System.Int32*<br>start of range to view |
| idx_max | *System.Int32*<br>end of range to view |

#### Returns

a single line string with token descriptions


## BlastCompilerOptions

Options for compiling and packaging scripts

### Constructor

initialize with default options

### Constructor(packagemode)

initilize default options in given packaging mode

| Name | Description |
| ---- | ----------- |
| packagemode | *NSS.Blast.BlastPackageMode*<br>the package mode to set |

### Constructor(stack_size, packagemode)

initialize default options in given packagemode with a pre-determined stack size

| Name | Description |
| ---- | ----------- |
| stack_size | *System.Int32*<br>stacksize, stack estimation will be turned off |
| packagemode | *NSS.Blast.BlastPackageMode*<br>packaging mode |

### Constructor(stack_size)

initialize default options with given stacksize

| Name | Description |
| ---- | ----------- |
| stack_size | *System.Int32*<br>stacksize, stack estimation will be turned off |

### AddDefine(key, value, allow_overwrite_existing)

add a compiled define

| Name | Description |
| ---- | ----------- |
| key | *System.String*<br>defined name |
| value | *System.String*<br>value |
| allow_overwrite_existing | *System.Boolean*<br> |

#### Returns

compiler options

### AutoValidate

run validation if set in script

### ClearDefines

remove all defines from compiler options

### CompileDebug

compile the debug function only if enabled

### CompileWithSystemConstants

compile script using constant data fields

### ConstantEpsilon

compare epsilon for constants, on fast float mode it wont match on float.epsilon

### ConstantPrecision

constant precision expressed as a string value

### Default

Default compiler options: BS1 - Normal - Optimizing

### DefaultStackSize

default stack size in number of bytes - overridden if the script defines a stack size

### Defines

additional compiler defines

### DisableOptimisations

disable compiler optimisations, default = enabled

#### Returns

compiler options

### EnableOptimisations

enable compiler optimizations, default == enabled

#### Returns

compiler options

### EnableValidation(run_auto_validation)

enable validation (default = off)

| Name | Description |
| ---- | ----------- |
| run_auto_validation | *System.Boolean*<br>true to enable validation |

#### Returns

options

### Entity

Default compiler options for packaging entities: BS1 - Entity Packagemode - Optimizing

### EstimateStackSize

estimate stack size using input, output and validation parameters - overridden if the script defines a stack size

### Experimental

dont touch if you need to ask

### IsDefined(key)

Check if the key is defined in compiler options

| Name | Description |
| ---- | ----------- |
| key | *System.String*<br>the case insensitive key to check |

#### Returns

true if its defined

### Language

The languageversion to use for the output of the compilation. Packagemode and language version are coupled but there may be deviations: - You can execute BS1 language version files with SSMD package modes if you guarentee that the code doesnt branch (the interpretor wont check this) - You can exectue BS1SSMD compiled packages with the normal interpretor in normal package mode

### Optimize

run code optimizer

### PackageAllocator

Allocator for data package

### PackageMode

the package mode for the output, this determines how code and data is organized in memory

### PackageStack

packages include stackdata

### PackageWithoutStack

package without a stack segment, use stackmemory in the interpretor

#### Returns

compiler options

### ParallelCompilation

enable for partially parallel compilation [forcebly disabled]

### RemoveDefine(key)

Remove any value possibly assosiated with the key

| Name | Description |
| ---- | ----------- |
| key | *System.String*<br>case insensitive key |

#### Returns

true if the key was defined and subsequently removed

### SetAllocator(allocator)

Set allocation mode for packages, use temp with caution in combination with bursted code

| Name | Description |
| ---- | ----------- |
| allocator | *Unity.Collections.Allocator*<br>the unity memory allocation type |

#### Returns

compiler options

### SetLanguage(language)

Set language target

| Name | Description |
| ---- | ----------- |
| language | *NSS.Blast.BlastLanguageVersion*<br>Supported language: BS1 | BSSSMD1 | HPC |

#### Returns

compiler options

### SetPackageMode(packagemode)

Set packaging mode

| Name | Description |
| ---- | ----------- |
| packagemode | *NSS.Blast.BlastPackageMode*<br>Packagemode: Normal, SSMD or Entity |

#### Returns

compiler options

### SetStackSize(stack_size)

set the size of the stack, if 0 is set stack is estimated during compilation

| Name | Description |
| ---- | ----------- |
| stack_size | *System.Int32*<br> |

#### Returns

compiler options

### Silent

disable all logging, fails silently

#### Returns

compiler options

### SSMD

Default SSMD compiler options: BS1 - SSMD Packagemode - Optimizing

### SupportYield

if yield is not emitted we can save 20 bytes on the stack, with very small stuff that might be handy not implemented .. todo

### Trace

set trace logging

#### Returns

compiler options

### TraceLogging

enable trace level logging -> will generate a massive report

### TryGetDefine(key, value)

Try to lookup a key and get its value

| Name | Description |
| ---- | ----------- |
| key | *System.String*<br>case insensitive key |
| value | *System.String*<br>the value if present |

#### Returns

true if the key was defined

### Verbose

set verbose logging

#### Returns

compiler options

### VerboseLogging

verbose report logging, log is also blitted to unity


## BlastCompilerStageType

the types of compiler stages that run in sequence to produce the output

### Analysis

analyze ast structure - basic removal of some useless structures - rules of multiplication

### BytecodeOptimizer

post-compile: bytecode optimizer

### Cleanup

pre compile cleanup

### Compile

a [bytecode/hpc/cs] compiler

### Flatten

flatten execution path

### JumpResolver

post-compile: resolve jumps

### Optimization

optimize ast structure - transform expensive constructs into less expensive ones - this should be done after flattening the tree, any optimization that reduces compounds should happen in analysis

### Packaging

post-compile: package result

### ParameterAnalysis

analyse parameter use - determine vectors - enforce multiplication rules

### Parser

parses the tokens into an ast-tree and identifies identifiers

### StackResolver

resolve stack operations into stack-variables (HPC/CS only)

### Tokenizer

convert input script into a list of tokens

### Transform

transform constructs in the ast: switch -> ifthen, while,for, etc -> ifthen making later stages having less to worry about


## BlastEngineData

BLAST execution data - used during execution of scripts - shared by all threads

### CanBeAValidFunctionId(id)

return if the id is in the correct range and its pointer is not null

| Name | Description |
| ---- | ----------- |
| id | *System.Int32*<br>the index/id |

#### Returns

true if possibly valid

### constants

constant values selected by opcodes and shared among threads - these are set by the constant value operations and they can be replaced with other values... if you are mad

### FunctionCount

number of function pointers in the fp array. function id's dont match indices..... - TODO this means each function call needs a lookup...

### FunctionPointers

function pointer data

### Functions

external function info array. these provide api access to the script

### GetFunction(op)

lookup function attached to operation, this assumes the function exists - TODO -> we could update this to a tableindexer instead of a scan by building a lookuptable[operation] == function

| Name | Description |
| ---- | ----------- |
| op | *NSS.Blast.blast_operation*<br>the operation to lookup the function for |

#### Returns

function record

### GetFunction(name_match)

get the function matching to the name

| Name | Description |
| ---- | ----------- |
| name_match | *System.String*<br>name to match |

#### Returns

the function struct, note that it returns the default zero'd struct on matching failure

### IsVariableParamFunction(op)

lookup a function mapping to the given operation, performs a linear scan through the function table

| Name | Description |
| ---- | ----------- |
| op | *NSS.Blast.blast_operation*<br>the operation to lookup |

#### Returns

returns true if the function is found and can have a variable parameter count

### random

base random number generator, all random actions have their origin in this random number generator

### Seed(i)

seed the base random number generator, altering the origen for all random actions in blast

| Name | Description |
| ---- | ----------- |
| i | *System.UInt32*<br>the new seed value |

### TryGetFunctionByName(name_match, function)

lookup a function using its name, this uses string input so wont be burst compiled

| Name | Description |
| ---- | ----------- |
| name_match | *System.String*<br>function name to match |
| function | *NSS.Blast.BlastScriptFunction@*<br>returned function |

#### Returns

true if found


## BlastEngineDataPtr

abstraction for enginedata pointer

### Data

unsafe casted BlastEngineData pointer

### IsCreated

returns if the pointer is not null / it doesnt actually track creation

### op_Implicit(p)~NSS.Blast.BlastEngineDataPtr

implicit conversion of this to an intptr

| Name | Description |
| ---- | ----------- |
| p | *System.IntPtr*<br> |

### ptr

pointer to engine data


## BlastError

Errorcodes that can be returned by blast

### compile_packaging_error

the compiler failed to package the compiled bytecode

### datasegment_size_larger_then_target

the datasegment is too large to be mapped to the target buffer

### error

a generic error occured

### error_already_packaged

package alread created, usually means that 'Prepare' is called while the script is already prepared

### error_assign_vector_size_mismatch

a vector is assigned to a variable of differnt vectorsize and no automatic conversion is possible or implemented

### error_begin_end_sequence_in_root

a begin-end opcode sequence is found in root while that should not be possible

### error_blast_not_initialized

blast engine data is not initialized (use: Blast.Create()

### error_compilation_failure

generic error during compilation of the script, the log could contain more data depending on compilation options

### error_cs_compiler_not_supported_on_platform

the c-sharp compiler is only supported in .Net Framework builds on windows.

### error_execute_package_not_correctly_set

package not correctly set to interpretor, use interpretor.SetPackage();

### error_failed_to_compile_function_parameters

1 or more function parameters failed to be compiled

### error_failed_to_flatten_function_parameters

the flatten operation failed on parameters of the target function node

### error_failed_to_translate_offset_into_index

failed to translate a dataoffset into a variable index, the bytecode uses offsets instead of id;s voiding the need for some checks

### error_invalid_nodetype

the node type is invalid in the current context

### error_invalid_nodetype_in_root

the ast nodetype is not allowed in the root, this indicates compiler errors

### error_invalid_script_id

the given script id is invalid in the current context

### error_language_version_not_supported

language version not supported in given context

### error_max_iterations

the interpretor reached the maximum number of iterations, this is an indication of scripts running in an endless loop

### error_node_function_unknown

the ast node encodes an unknown function

### error_node_not_flat

the node has not been sufficiently flattened for execution

### error_nothing_to_execute

there is nothing to execute

### error_optimizer_failed_to_replace_sequence

the optimizer failed to replace a sequence it targetted to optimize

### error_optimizer_operation_mismatch

the optimizer failed to match operations

### error_optimizer_parameter_mismatch

the optimizer failed to match parameters

### error_package_not_allocated

the given package doesnt have any allocated code or data segments

### error_packagemode_not_supported_for_direct_execution

the packagemode is not supported in the given execution method

### error_pushv_vector_size_not_supported

the currentvector size is not supported to be pushed to the stack

### error_too_many_parameters

a function is used with too many parameters

### error_unknown_op

an unknown operation was found

### error_unsupported_operation

the operation is not supported in the current context

### error_unsupported_operation_in_root

an operation is encountered that is not supported while executing root level nodes

### error_unsupported_operation_in_ssmd_root

the current operation is not supported at the root level during ssmd interpretation

### error_update_vector_fail

failed to update a vector

### error_variable_vector_compound_not_supported

a variably sized compound is not supported in the current sequence of operations

### error_variable_vector_op_not_supported

a variable vector operation is not supported by the current sequence of operations

### error_vector_size_not_supported

the given vectorsize is not supported by the target operation

### script_id_not_found

the given script id could not be found

### ssmd_error_expecting_value

the ssmd interpretor expected a value but received something else

### ssmd_error_unsupported_vector_size

the current vectorsize is not supported in the current sequence of operations

### ssmd_invalid_packagemode

invalid packagemode set in package for ssmd execution - packages need to be compiled in SSMD mode for SSMD interpretation (it can still run normal interpretation on ssmd packages though)

### stack_error_peek

error peeking stack information

### stack_error_pop

error taking values from stack

### stack_error_pop_multi_from_root

a pop instruction is found where it doesnt belong

### stack_error_variable_pop_not_supported

a variable sized pop is not supported

### success

everything went OK

### validate_error_stack_too_small

the allocated space for the stack is too small (to few stack memory locations)

### yield

execution returned back to caller


## BlastLanguageVersion

the different compiler outputs / language targets

### BS1

BLAST Script, default script / bytecode

### BSSMD1

BLAST Single Script Multiple Data

### CS

Runtime compiled c# code, .net framework and windows only

### HPC

Burstable C# code packed in functions for burst to compile at designtime

### None

unknown language version


## BlastMetaDataStack

a pointer to meta-data-stack memory


## BlastPackageData

the bare minimum data (28 bytes) to package a script for execution

### AllocatedDataSegmentSize

the size with stack included depending on flags

### Allocator

Package memory allocator

### CloneData(System.Int32,NSS.Blast.BlastMetaDataStack*)

clone n segments into 1 memory block and index it with pointers - the first block contains the root pointer to free later

### CloneData(System.Int32,Unity.Collections.Allocator)

clone n segments into 1 memory block and index it with pointers - the first block contains the root pointer to free later

### CloneData(n)

clone n data segments into 1 block and index it with pointers - the first block contains the root pointer which can be freed

| Name | Description |
| ---- | ----------- |
| n | *System.Int32*<br> |

#### Returns



### CloneDataStack(System.Int32,NSS.Blast.BlastSSMDDataStack*)

clone n segments into 1 memory block and index it with pointers - the first block contains the root pointer to free later

### CloneDataStack(System.Int32,Unity.Collections.Allocator)

clone n segments into 1 memory block and index it with pointers - the first block contains the root pointer to free later

### CloneDataStack(n)

clone n data segments into 1 block and index it with pointers - the first block contains the root pointer which can be freed

| Name | Description |
| ---- | ----------- |
| n | *System.Int32*<br> |

#### Returns



### Code

Code[] pointer

### CodeSegmentPtr

points to codesegment, may be shared with other segments, see packagemode

### CodeSegmentSize

the allocated datasize in bytes of the codesegment pointer

### CodeSize

size of code in bytes, maps to O1 in all package modes

### Data

data[] pointer

### DataSegmentPtr

pointer to data segment as calculated from package configuration

### DataSegmentSize

the size if stack would be included, while on normal packaging mode there is no seperate buffer there is a size

### DataSegmentStackOffset

stack offset in bytes as seen from the start of datasegment - stack and datasegment MUST ALWAYS be in the same segment so that Data[last] == Stack[-1] - when using .Stack[] offset is 0

### DataSize

data size in bytes, may include alignment bytes

### Flags

Package flags, see flags enumeration

### Free

free any memory allocated

### FreeData(NSS.Blast.BlastMetaDataStack*,Unity.Collections.Allocator)

free memory used by an ssmd data block

### FreeData(NSS.Blast.BlastSSMDDataStack*,Unity.Collections.Allocator)

free memory used by an ssmd data block

### HasStack

true if memory for stack is allocated, false if not: - yield not possible without persistant stack - we call it TLS, thread level stack/storage - Faster in small multithreaded bursts, benefit fades in very large bursts

### IsAllocated

true if memory has been allocated for this object

### LanguageVersion

Package languageversion, determines feature support

### Metadata

metadata[], 1 byte of metadata for each dataelement in stack and datasegment

### MetadataPtr

Calculated pointer to metadata

### MetadataSize

metadata size in bytes, may include alignment bytes in normal and SSMD modes

### O1

Offset 1, intent depends on packagemode

### O2

Offset 2, intent depends on packagemode

### O3

Offset 3, intent depends on packagemode

### O4

Offset 4, intent depends on packagemode

### P2

points to the other segment, see packagemode

### PackageMode

Packaging mode NORMAL: [----CODE----|----METADATA----|----DATA----|----STACK----] 1 2 3 4 SSMD: [----CODE----|----METADATA----] [----DATA----|----STACK----] 1 2 3 4 ENTITY: [----CODE----] [----METADATA----] [----DATA----|----STACK----] 1 2 3 4

### SSMDDataSize

bytesize for needed BlastSSMDDataStack records

### Stack

Stack[] pointer -> Data[last] == Stack[-1]

### StackCapacity

the maxiumum stack capacity in elements (1 element == 32 bit) - looks at flags, if == nostack then returns a capacity of 0 - IMPORTANT NOTE: looking at profiler this really should be cached if asked a lot

### StackSegmentPtr

pointer to stack segment as calculated from package configuration

### StackSize

stack size in bytes, may not be a multiple of elementsize/4bytes


## BlastPackageFlags

Package Flags

### Aligned4

align data offsets on a 4 byte boundary

### Aligned8

align data offsets on a 4 byte boundary

### None

full data allocated, package can be directly executed

### NoStack

package is allocated without stack data (template for SSMD)


## BlastPackageMode

Blast script packaging types

### Compiler

package type used by compiler - THE POINTERS ARE INVALID [----CODE----] [----METADATA----] [----DATA----|----STACK----] 1 2 3 4 1 = codesegment size 2 = metadata size 3 = datasize in bytes / stack offset in bytes 4 = datasegment size = stackcapacity = 4 - 3

### Entity

Entity Package: the script's code is seperated from all data [----CODE----] [----METADATA----|----DATA----|----STACK----] 1 2 3 4 1 = codesegment size 2 = metadata size 3 = stack offset 4 = datasegment size

### Normal

Compile all into a single package, code data and stack combined [----CODE----|----METADATA----|----DATA----|----STACK----] 1 2 3 4 ** ALL OFFSETS IN PACKAGE IN BYTES *** 1 = metadata offset 2 = data_offset 3 = stack_offset 4 = package_size

### SSMD

SSMD Package with code and metadata seperate from datastack - SSMD requirement: while data changes, its intent does not so metadata is shared - SSDM in V2/BS2 allows for (nested) branching by setting sync points on non constant jumps: -- loop ends -- if then else jumps [----CODE----|----METADATA----] [----DATA----|----STACK----] 1 2 3 4 1 = metadata offset 2 = codesegment size 3 = stack offset 4 = datasegment size prop stacksize (in elements) => (datasegment size - stack_offset) / 4


## BlastRuntimeVersions

Versions of blast present in build

### Final1

the final version 1 = release 1


## BlastScript

A BLAST Script

### Code

the actual scriptcode conforming to the languageversion set

### Dispose

cleanup package data if allocated on dispose

### Execute(blast, environment, caller)

execute the script in the given environment with the supplied data

| Name | Description |
| ---- | ----------- |
| blast | *System.IntPtr*<br>blastengine data |
| environment | *System.IntPtr*<br>[optional] pointer to environment data |
| caller | *System.IntPtr*<br>[ooptional] caller data |

#### Returns

success if all is ok

### FromText(code, name, id)

create script object from code

| Name | Description |
| ---- | ----------- |
| code | *System.String*<br>the code |
| name | *System.String*<br>name for the script |
| id | *System.Int32*<br>a unique id |

#### Returns

a blast script

### Id

Blast scriptid, used to uniquely identify the script. It is used throughout blast to id the packaged script

### IsPackaged

true if the script has been packaged / prepared

### IsPrepared

true if the script has been packaged / prepared

### LanguageVersion

Target language vesion, depending on compilation settings it might change in the package but the user should ensure that the code is compatible;

### Name

The name of the script as used in messages

### Package

native package data, contains references to code and data segments

### Prepare(blast)

Prepare the script for execution

| Name | Description |
| ---- | ----------- |
| blast | *System.IntPtr*<br>blast engine data |

#### Returns

success if all is ok

### ReleasePackage

release package memory, nulls reference to it and free;s any native package memory with it

### ToString

get the string representation of a blast script as ID:Name


## BlastScriptAPI

For now, just a collection of function pointers that holds a native list with function information

### Constructor(allocator)

Constructor for a new blastscriptapi instance, provides native allocator

| Name | Description |
| ---- | ----------- |
| allocator | *Unity.Collections.Allocator*<br> |

### Allocator

allocated to be used for any data comming from this api

### Dispose

dispose of any native memory that could be allocated for holding function pointer information

### FunctionCount

number of functions defined in this api

### FunctionInfo

managed information, includes a copy of the native info

### Functions

native function definition info

### GetFunctionById(function_id)

lookup a function definition that is directly linked to an interpretor operation

| Name | Description |
| ---- | ----------- |
| function_id | *NSS.Blast.ReservedBlastScriptFunctionIds*<br>the reserved id of the function to lookup |

#### Returns

a function definition

### GetFunctionById(function_id)

lookup a function definition that is directly linked to an interpretor operation

| Name | Description |
| ---- | ----------- |
| function_id | *System.Int32*<br>the unique id of the function to lookup |

#### Returns

a function definition

### GetFunctionByName(name)

lookup a function definition that is directly linked to an interpretor operation

| Name | Description |
| ---- | ----------- |
| name | *System.String*<br>the name of the function to lookup |

#### Returns

a function definition

### GetFunctionByOpCode(op)

lookup a function definition that is directly linked to an interpretor operation

| Name | Description |
| ---- | ----------- |
| op | *NSS.Blast.blast_operation*<br>the operation that should translate to a function used during interpretation |

#### Returns

a function definition

### GetFunctionDataById(id)

Directly get a function using the id as an index

| Name | Description |
| ---- | ----------- |
| id | *System.Int32*<br>function id/index |

#### Returns

the script function object

### Initialize

Initialize native function pointer stack

#### Returns



### IsInitialized

true if native function pointer data is initialized/allocated

### IsVariableParamFunction(op)

returns true if the function accepts a variable sized list of paramaters

| Name | Description |
| ---- | ----------- |
| op | *NSS.Blast.blast_operation*<br>the operation mapping to a function |

#### Returns

true if the function exists and has a variable parameter list

### Name

name of the api

### RegisterFunction(id, name, min_param_count, max_param_count, accept_vector_size, return_vector_size, op)

Register a function with blast

| Name | Description |
| ---- | ----------- |
| id | *NSS.Blast.ReservedBlastScriptFunctionIds*<br>a reserved function id |
| name | *System.String*<br>functino name |
| min_param_count | *System.Int32*<br>minimal parameter count |
| max_param_count | *System.Int32*<br>maximum parameter count |
| accept_vector_size | *System.Int32*<br>accepted vector size, 0 for any |
| return_vector_size | *System.Int32*<br>returned verctor size, 0 for any |
| op | *NSS.Blast.blast_operation*<br>blast operation used to encode it |

#### Returns

returns a unique (within the blast instance) function id

### RegisterFunction(id, name, min_param_count, max_param_count, accept_vector_size, return_vector_size, op)

Register a function with blast

| Name | Description |
| ---- | ----------- |
| id | *NSS.Blast.ReservedBlastScriptFunctionIds*<br>a reserved function id |
| name | *System.String*<br>functino name |
| min_param_count | *System.Int32*<br>minimal parameter count |
| max_param_count | *System.Int32*<br>maximum parameter count |
| accept_vector_size | *System.Int32*<br>minimal vector size, 0 for any |
| return_vector_size | *System.Int32*<br>max verctor size, 0 for any |
| op | *NSS.Blast.extended_blast_operation*<br>extended blast operation used to encode it |

#### Returns

returns a unique (within the blast instance) function id

### RegisterFunction(name, min_param_count, max_param_count, accept_vector_size, return_vector_size, op)

Register a function with blast

| Name | Description |
| ---- | ----------- |
| name | *System.String*<br>functino name |
| min_param_count | *System.Int32*<br>minimal parameter count |
| max_param_count | *System.Int32*<br>maximum parameter count |
| accept_vector_size | *System.Int32*<br>minimal vector size, 0 for any |
| return_vector_size | *System.Int32*<br>max verctor size, 0 for any |
| op | *NSS.Blast.blast_operation*<br>blast operation used to encode it |

#### Returns

returns a unique (within the blast instance) function id

### RegisterFunction(name, min_param_count, max_param_count, accept_vector_size, return_vector_size, op)

Register a function with blast

| Name | Description |
| ---- | ----------- |
| name | *System.String*<br>functino name |
| min_param_count | *System.Int32*<br>minimal parameter count |
| max_param_count | *System.Int32*<br>maximum parameter count |
| accept_vector_size | *System.Int32*<br>minimal vector size, 0 for any |
| return_vector_size | *System.Int32*<br>max verctor size, 0 for any |
| op | *NSS.Blast.extended_blast_operation*<br>blast operation used to encode it |

#### Returns

returns a unique (within the blast instance) function id

### RegisterFunction(nativefunction, name, parameter_count, accept_vector_size, return_vector_size)

Register a function with blast

| Name | Description |
| ---- | ----------- |
| nativefunction | *System.String*<br>a native function pointer |
| name | *System.IntPtr*<br>functino name |
| parameter_count | *System.Int32*<br>parameter count |
| accept_vector_size | *System.Int32*<br>minimal vector size, 0 for any |
| return_vector_size | *System.Int32*<br>max verctor size, 0 for any |

#### Returns

returns a unique (within the blast instance) function id

### TryGetFunctionCallById(id, function)

try to get a function by id, in release it just gets it, in debug it checks

| Name | Description |
| ---- | ----------- |
| id | *System.Int32*<br>function id/index |
| function | *NSS.Blast.BlastScriptFunction@*<br>function |

#### Returns

true if found


## BlastScriptFunction

burst compatible function description

### AcceptsVectorSize

vectorsize of accepted values in parameters, set to 0 to perform no check - TODO, V2/3/4?? could make this more strict

### CanHaveParameters

true if the function can have parameters

### ExtendedScriptOp

Built-in functions directly compile into a script operation

### Flags

Flags: - reserved: function targets a reserved function

### FunctionId

function Id, doubles as index into function tables

### Generic\`\`1

cast our functionpointer into the delegate used to call it

#### Type Parameters

- T - the delegate type

#### Returns



### GetFunctionName

rebuilds the functionname from a native character array (expensive operation)

#### Returns

the string representing the functionname

### HasVariableParameterCount

returns true if the function accepts a variable sized list of paramaters

### IsExternalCall

True if the functioncall is an external functionpointer

### IsNotValid

returns if the function is NOT valid (checks id, assumes memory is initialized to zeros)

### IsPopVariant

true if function encodes a pop function

### IsPushVariant

true function encodes a push operation

### IsReserved

true if the function targets a reserved function name

### IsValid

returns if the function is valid (checks id, assumes memory is initialized to zeros)

### Match

char array to match to in lowercase, only ASCII - length == Blast.MaximumFunctionNameLength

### MaxParameterCount

maximal number of parameters, 0 for none, max = 31

### MinParameterCount

minimal number of parameters

### NativeFunctionPointer

a native function pointer (1st member, makes sure its aligned if this struct is)

### ReturnsVectorSize

vectorsize of returnvalue, 0 if no value is returned

### ScriptOp

Built-in functions directly compile into a script operation


## BlastScriptFunctionFlag

flags for extra information on script functions

### NativeFunction

function uses a native function pointer for execution

### Reserved

function targets a blast reserved function (seed, push, peek)


## BlastScriptFunctionInfo

managed information on functions

### CSName

the identifier used in CS code - DONT USE

### Function

the native function data contains id, information and function pointer

### HasVariableParameterCount

true if the function has a variable length parameter list

### Match

the identifier to match the function to = function name

### Parameters

[Optional] parameter names, these dont dictate min/max parametercount

### ToString

tostring override for better view in debugger

#### Returns




## BlastScriptPackage

BlastScriptPackage contains all data needed to use and execute scriptcode, it consists of: - BlastPackage -> contains the native bytecode - Variable information - IO mapping - Bursted functionpointer mapping

### Bursted

A functionpointer to burst transpiled bytecode, possible if the package was known at compile time. SSMD mode will still use the bytecode package.

### Destroy

Destroy any allocated native memory

### Execute(blast, environment, caller)

execute the script in the given environment with the supplied data

| Name | Description |
| ---- | ----------- |
| blast | *System.IntPtr*<br>blastengine data |
| environment | *System.IntPtr*<br>[optional] pointer to environment data |
| caller | *System.IntPtr*<br>[ooptional] caller data |

#### Returns

success if all is ok

### Flags

package flags as set by attached package

### GetCodeSegmentText(width)

Get a string representation of the bytecode, example output: 000| push compound 1 + 2 nop push function max ^ pop 2 010| debug pop nop 000| 030 085 002 086 000 029 042 009 025 086 010| 255 253 025 000

| Name | Description |
| ---- | ----------- |
| width | *System.Int32*<br>number of columns to render |

#### Returns

A formatted string

### GetDataSegmentText

Get a string representation of the datasegement

### GetPackageCodeBytesText(System.Int32,System.Boolean)

get code as 000| 000 000 000 000

#### Returns



### GetPackageDataBytesText(System.Int32,System.Boolean)

get datasegment as 000| 000 000 000 000

#### Returns



### GetPackageInfoText

return overview of package information

#### Returns



### Inputs

defined inputs

### IsAllocated

Returns true if native memory is allocated for the package

### IsBurstCompiled

True if this package has also been burstcompiled and can be executed with a native function pointer

### Outputs

defined outputs

### Package

the bytecode package

### PackageMode

packaging mode set by attached package data

### PackageSize

size of package data

### ToString

ToString overload for more information during debugging

### VariableOffsets

Offsets for variables in element count into datasegment, an elements is 4 bytes large == 1 float

### Variables

Variable information


## BlastScriptTokenDefinition

definition of a token used in blast script


## BlastSSMDDataStack

data for ssmd operation modes: data-stack only - only used as pointer, fields handy in debugger


## BlastVariable

Description of a variable as determined during compilation of script. It is not needed for execution and is thus not available through the native BlastPackageData. Native code can query metadata.

### AddReference

Add a reference to this variable

### DataType

The datatype of the variable: - V1: only numeric datatypes are supported - V2: support for ID types - V3: ID64, NUMERIC64

### Id

the unique id of the variable as used within the script

### IsConstant

is this variable constant?

### IsInput

true if specified in inputs

### IsOutput

true if specified in outputs

### IsVector

true if this is a vector of size > 1

### Name

The name of the variable as it was used in the script

### ReferenceCount

Number of times blast references the variable

### ToString

ToString override for a more detailed view during debugging

#### Returns



### VectorSize

vectorsize of the variable


## BlastVariableDataType

supported variable data types

### ID

integer datatype

### ID64

long datatype

### Numeric

float datatype

### Numeric64

double datatype


## BlastVariableMapping

description mapping a variable to an input or output

### ByteSize

Bytesize of variable

### DataType

Datatype of variable

### Offset

Offset of variable into datasegment, in bytes

### ToString

ToString override providing a more usefull description while debugging

#### Returns

a formatted string

### Variable

the variable that is mapped

### VariableId

Id of variable


## BlastVectorSizes

supported vectorsizes

### float1

size 1: 4 bytes

### float2

size 2: 8 bytes

### float3

size 3: 12 bytes

### float4

size 4: 16 bytes


## BlastVectorTypes

supported vectortypes

### v1

size 1 vector

### v2

size 2 vector

### v3

size 3 vector

### v4

size 4 vector

### NSS.Blast.Cache.blast.max(System.Single,System.Single)

hmmmmz we would neeed very many overloads when supporting 63 parameters...


## CastUtil

cast 1 refernce to another Quaternion q; ref float4 f = ref CastUtil.RefToRef(q); f.w = 123; print(q.w); // 123

### NSS.Blast.CodeUtils.GetBytesView(code, length, column_count, use_index)

return bytes formatted as 000| 000 000 000 000 000 000 000 000

| Name | Description |
| ---- | ----------- |
| code | *System.Byte**<br> |
| length | *System.Int32*<br> |
| column_count | *System.Int32*<br> |
| use_index | *System.Boolean*<br> |

#### Returns




## BlastCompiler

Blast Compiler Compile scripts into bytecode, the process consists of several stages: For bytecode these stages might be executed: 1 - tokenize: convert code into a list of tokens 2 - parse: parse list of tokens into a tree of nodes 3 - transform: transform nodes sequences 4.1 - analyse parameters: determine parameter types and check inputs and outputs 4.2 - analyse: analyse nodes, reorder were needed, optimize for execution 5 - flatten: flatten execution path 6 - node optimizer: optimize nodes 7 - compile: generate bytecode from the internal representation 8 - optimize bytecode: optimize bytecode patterns 9 - package: package bytecode and set it up for execution

### ByteCodeStages

Default compilation setup

### Compile(blast, script, options)

Compile a script

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br>blast engine data |
| script | *NSS.Blast.BlastScript*<br>the script to compile |
| options | *NSS.Blast.BlastCompilerOptions*<br>compileoptions |

#### Returns

compiler data

### Compile(blast, code, options)

Compile script from text

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br>blast engine data |
| code | *System.String*<br>the code |
| options | *NSS.Blast.BlastCompilerOptions*<br>compiler options |

#### Returns

compiler data

### CompileCS(blast, script, options)

Compile using .net c# compiler - only on windows .net framework > 4.5

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br> |
| script | *NSS.Blast.BlastScript*<br> |
| options | *NSS.Blast.BlastCompilerOptions*<br> |

#### Returns



### CompileDataPackage(blast, script, options)

Compile the script into a native blastscript datapackage

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br> |
| script | *NSS.Blast.BlastScript*<br> |
| options | *NSS.Blast.BlastCompilerOptions*<br> |

#### Returns



### CompileHPC(blast, script, options)



| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br> |
| script | *NSS.Blast.BlastScript*<br> |
| options | *NSS.Blast.BlastCompilerOptions*<br> |

#### Returns



### CompilePackage(blast, script, options)

compile script into a managed blastscriptpackage containing blastpackagedata

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br> |
| script | *NSS.Blast.BlastScript*<br> |
| options | *NSS.Blast.BlastCompilerOptions*<br> |

#### Returns



### CSStages

C# compilation uses the output from the hpc stage

### EstimateStackSize(NSS.Blast.Compiler.CompilationData)

estimate stack size by running script with a selection of parameters from input, output and validation settings TODO: EstimateStackSize and Validate should be combined

#### Returns

estimated stack size in bytes

### HPCStages

compilation stages for compilation into a job, - use the same precompilation, make sure behaviour is equal even if some unknown bug is there

### opt_ident

form this opcode until 255 variables are encoded

### opt_value

from this opcode until opt_ident constant values are encoded

### Package(NSS.Blast.Compiler.IBlastCompilationData,NSS.Blast.BlastCompilerOptions)

package the result of the compiler into an executable package

#### Returns

the native blast package data structure

### PackageNormal(cdata, code_size, metadata_size, data_size, stack_size, flags)

Package in normal mode. - packagemode = NORMAL - languageversion = BS1

| Name | Description |
| ---- | ----------- |
| cdata | *NSS.Blast.Compiler.CompilationData*<br>Compiler data |
| code_size | *System.Int32*<br>size of code in bytes |
| metadata_size | *System.Int32*<br>size of metadata in bytes, 1 byte per data element in data and stack segment combined |
| data_size | *System.Int32*<br>size of datasegment in bytes |
| stack_size | *System.Int32*<br>size of stacksegement in bytes |
| flags | *NSS.Blast.BlastPackageFlags*<br>flags: alignment, stack |

#### Returns

blast package data

### PackageSSMD(cdata, code_size, metadata_size, data_size, stack_size, flags)

package for ssmd use: [code-metadata] [data-stack]

| Name | Description |
| ---- | ----------- |
| cdata | *NSS.Blast.Compiler.CompilationData*<br>compiler result data |
| code_size | *System.Int32*<br> |
| metadata_size | *System.Int32*<br> |
| data_size | *System.Int32*<br> |
| stack_size | *System.Int32*<br> |
| flags | *NSS.Blast.BlastPackageFlags*<br> |

#### Returns



### Validate(result, blast)

Validate output using data set in script for NULL inputs

| Name | Description |
| ---- | ----------- |
| result | *NSS.Blast.Compiler.IBlastCompilationData*<br>bytecode compiler data |
| blast | *System.IntPtr*<br>blast engine data |

#### Returns

true if validation succeeded


## BlastIntermediate

intermediate bytecode data for use by compiler

### code

byte code compiled from script

### code_pointer

index into bytecode, next point of execution, if == code_size then end of script is reached

### code_size

size of code in bytes

### data

input, output and scratch data fields

### data_count

offset into data after the last variable, from here the stack starts

### DataCount

nr of data elements (presumably 32bits so 4bytes/element) - same as data_offset, added for clarity

### Execute(blast)

execute the intermediate for validation and stack info

| Name | Description |
| ---- | ----------- |
| blast | *System.IntPtr@*<br> |

#### Returns



### GetDataSegmentElement(data_segment_index)

read a float from the datasegement at given element index

| Name | Description |
| ---- | ----------- |
| data_segment_index | *System.Int32@*<br>element index into data segment |

#### Returns

the data

### Id

unique script id

### max_stack_size

maximum reached stack size in floats

### Validate(System.IntPtr@)

validate intermediate


## CompilationData

Data created during compilation and used for analysis, packaging and debugging/display purposes

### Constructor(blast, script, options)

setup new compilation data

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br>blast engine data |
| script | *NSS.Blast.BlastScript*<br>the script to compile |
| options | *NSS.Blast.BlastCompilerOptions*<br>compiler options |

### AST

the rootnode of the abstract syntax tree

### Blast

blast engine data

### code

intermediate bytecode, only public for debugging view purposes, dont use, dont modify

### CompilerMessages

List of messages issued during compilation

### CompilerOptions

Options used during compilation

### ConstantVariables

List of constant variables (constant data needs to be somewhere)

### CreateVariable(name, is_input, is_output)

create a holder for variable data collected during compilation - will log errors if the variable exists and returns null - initializes reference count at 1

| Name | Description |
| ---- | ----------- |
| name | *System.String*<br>first part of identifier - the name |
| is_input | *System.Boolean*<br>true if used as an input |
| is_output | *System.Boolean*<br>true if used as an output |

#### Returns

null on failure, any error will be logged

### Defines

list of defines defined by this script

### ErrorCount

number of errors that occured during compilation

### Executable

the intermediate

### GetHumanReadableBytes(columns, index)

get a readable string from the compiled code

| Name | Description |
| ---- | ----------- |
| columns | *System.Int32*<br>number of columns to use in the presentation of the bytes |
| index | *System.Boolean*<br>true if you want an index (000| ) at the start of each line |

#### Returns



### GetHumanReadableCode(System.Int32,System.Boolean)

this version has a little more information than the generic bytecode reader in blast due to having access to all compilation data

#### Returns

a readable string

### GetOrCreateVariable(name)

get or create a holder for variable data during compilation - maintains reference count

| Name | Description |
| ---- | ----------- |
| name | *System.String*<br>identifier name |

#### Returns

null on failure

### HasErrors

number of errors that occured during compilation

### HasErrorsOrWarnings

true if any erorr or warning occured

### HasWarnings

true if any warning was logged during compilation

### Inputs

list of inputs defined by this script

### IsOK

true if everything went ok

### Jumps

list of jumps

### LastError

returns the last error code or success if nothing went wrong

### LastErrorMessage

keep reference of any last error message, voiding the need to search for it

### LogError(msg, code, linenr, member)

Log an error to the log, also writes to player log / debugstream

| Name | Description |
| ---- | ----------- |
| msg | *System.String*<br>the message |
| code | *System.Int32*<br>optional errorcode |
| linenr | *System.Int32*<br>optional linenr |
| member | *System.String*<br>optional caller member name |

### LogMessage(System.String,System.Int32,System.String)

on older .net versions we could get the stackframe see: https://stackoverflow.com/questions/12556767/how-do-i-get-the-current-line-number and: https://stackoverflow.com/questions/38476796/how-to-set-net-core-in-if-statement-for-compilation

### LogToDo(msg, linenr, member)

logs a todo, only in standalone debug builds

| Name | Description |
| ---- | ----------- |
| msg | *System.String*<br>the message |
| linenr | *System.Int32*<br>optional line number |
| member | *System.String*<br>optional caller member name |

### LogTrace(msg, linenr, member)

Trace a message, does nothing in release builds

| Name | Description |
| ---- | ----------- |
| msg | *System.String*<br>the message to trace |
| linenr | *System.Int32*<br>line number |
| member | *System.String*<br>caller member name |

### LogWarning(msg, linenr, member)

Log a warning to the log, also writes to player log / debugstream

| Name | Description |
| ---- | ----------- |
| msg | *System.String*<br>the message |
| linenr | *System.Int32*<br>optional linenr |
| member | *System.String*<br>optional caller member name |


## Message

a compiler message

### NSS.Blast.Compiler.CompilationData.Offsets

list of used variable offsets

### NSS.Blast.Compiler.CompilationData.Outputs

list of outputs defined by this script

### NSS.Blast.Compiler.CompilationData.Script

the input script

### NSS.Blast.Compiler.CompilationData.Tokens

list of tokens as parsed out of the script

### NSS.Blast.Compiler.CompilationData.TryGetDefine(identifier, defined_value)

try to lookup define by identifier name

| Name | Description |
| ---- | ----------- |
| identifier | *System.String*<br> |
| defined_value | *System.String@*<br> |

#### Returns



### NSS.Blast.Compiler.CompilationData.TryGetInput(v, mapping)

Try to lookup a input variable mapping

| Name | Description |
| ---- | ----------- |
| v | *NSS.Blast.BlastVariable*<br>the variable |
| mapping | *NSS.Blast.BlastVariableMapping@*<br>output mapping |

#### Returns

true if found

### NSS.Blast.Compiler.CompilationData.TryGetOutput(v, mapping)

try to lookup an output variable mapping

| Name | Description |
| ---- | ----------- |
| v | *NSS.Blast.BlastVariable*<br>the variable |
| mapping | *NSS.Blast.BlastVariableMapping@*<br>the output variable mapping |

#### Returns

true if found

### NSS.Blast.Compiler.CompilationData.TryGetVariable(name, variable)

try to lookup a reference - does not reference count

| Name | Description |
| ---- | ----------- |
| name | *System.String*<br>the name of the variable to lookup |
| variable | *NSS.Blast.BlastVariable@*<br>output variable |

#### Returns

true if found

### NSS.Blast.Compiler.CompilationData.Validations

list of validations defined by this script

### NSS.Blast.Compiler.CompilationData.Variables

List of variables in script

### NSS.Blast.Compiler.CompilationData.version

Version

### NSS.Blast.Compiler.CompilationData.Version

Version

### NSS.Blast.Compiler.CompilationData.WarningCount

number of warnings that occured during compilation


## CSCompilationData

compiler data for the C# compiler - as it uses the output from hpc we base data on its data

### Constructor(blast, script, options)

Setup CS Compiler chain

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br>blast engine data |
| script | *NSS.Blast.BlastScript*<br>script code |
| options | *NSS.Blast.BlastCompilerOptions*<br>compiler options |

### Namespace

Target namespace for compiling scripts into


## HPCCompilationData

compiler data for the hpc compiler

### Constructor(blast, script, options)

setup compilation data for the HPC compiler chain

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br>blast |
| script | *NSS.Blast.BlastScript*<br>the blast script to compile |
| options | *NSS.Blast.BlastCompilerOptions*<br>blast compiler options |

### HPCCode

resulting burstable C# code


## IBlastCompilationData

interface into compilationdata, we should restrict outside use a bit via this

### AST

Compiler node tree

### Blast

blast engine data used in this compilation

### CanValidate

true if the script can be validated (it contains validation defines)

### CompilerOptions

Compiler Options used during compilation

### Defines

Compiler defines used during compilation, this contains only the unique defines set by this script and more defines might apply depending on the setup

### ExistsVariable(name)

returns true if a variable exists with the given name

| Name | Description |
| ---- | ----------- |
| name | *System.String*<br>variable name |

#### Returns

true if the variable exists

### GetVariable(name)

lookup a variablemapping defined by the script by its name

| Name | Description |
| ---- | ----------- |
| name | *System.String*<br>the name of the variable as used in the script code |

#### Returns

the variable if found, null otherwise

### GetVariableFromOffset(offset)

lookup a variable defined by script based on its offset

| Name | Description |
| ---- | ----------- |
| offset | *System.Byte*<br>the datasegment offset |

#### Returns

the variable

### HasDefines

true if the script defines compiler defines

### HasErrors

true if an errorcode is set or errors are present in the compilation log

### HasInput(id)

check if there is an input defined by the script with the given id

| Name | Description |
| ---- | ----------- |
| id | *System.Int32*<br>the integer identifier |

#### Returns

true if defined

### HasInput(name)

check if there is an input defined by the script with the given id

| Name | Description |
| ---- | ----------- |
| name | *System.String*<br>the input variable name |

#### Returns

true if defined

### HasOffsets

true if the script defines variables

### HasVariables

true if the script defines variables

### Inputs

Defined Inputs

### IsOK

true if no errors are set in the compilation log and no errorcode is set

### Jumps

Jumps found in the script

### LogError(msg, code, linenr, member)

log an error to the compiler log

| Name | Description |
| ---- | ----------- |
| msg | *System.String*<br>the message to log |
| code | *System.Int32*<br>an error code |
| linenr | *System.Int32*<br>possibly the linenr |
| member | *System.String*<br>possibly the callername |

### LogToDo(msg, linenr, member)

log a message to the compiler log

| Name | Description |
| ---- | ----------- |
| msg | *System.String*<br>the message to log |
| linenr | *System.Int32*<br>possibly the linenr |
| member | *System.String*<br>possibly the callername |

### LogTrace(msg, linenr, member)

trace information, does nothing in release

| Name | Description |
| ---- | ----------- |
| msg | *System.String*<br>the message to log |
| linenr | *System.Int32*<br>possibly the linenr |
| member | *System.String*<br>possibly the callername |

### LogWarning(msg, linenr, member)

log a warning to the compiler log

| Name | Description |
| ---- | ----------- |
| msg | *System.String*<br>the message to log |
| linenr | *System.Int32*<br>possibly the linenr |
| member | *System.String*<br>possibly the callername |

### OffsetCount

number of variable offsets defined in the script

### Offsets

Offsets into the datasegment for variable indices

### Outputs

Defined Outputs

### Script

the script

### Tokens

List of tokens as parsed from the input

### TryGetDefine(identifier, defined_value)

attempt to get a defined value from script defined compilerdefines

| Name | Description |
| ---- | ----------- |
| identifier | *System.String*<br>the identifier |
| defined_value | *System.String@*<br>the output value |

#### Returns

true if a define was found with the given name

### Validations

Validations defined in script

### VariableCount

number of variables defined in the script

### Variables

List of variables as found in input

### Version

compiler version


## node

an ast node used by the blast compiler

### Constructor(_parent, _children)

general constructor

| Name | Description |
| ---- | ----------- |
| _parent | *NSS.Blast.Compiler.node*<br>parent node |
| _children | *NSS.Blast.Compiler.node[]*<br>child nodes |

### Constructor(_type, _token)

general constructor

| Name | Description |
| ---- | ----------- |
| _type | *NSS.Blast.Compiler.nodetype*<br>the nodetype |
| _token | *NSS.Blast.BlastScriptToken*<br>the attached token |

### AppendDependencies(nodes)

append multiple dependant nodes

| Name | Description |
| ---- | ----------- |
| nodes | *System.Collections.Generic.IEnumerable{NSS.Blast.Compiler.node}*<br>nodes to add to dependencies |

### AppendDependency(n)

add a node to the list of nodes to depend on, these are tobe inserted before this node during compilation, the parent of the node is updated to this

| Name | Description |
| ---- | ----------- |
| n | *NSS.Blast.Compiler.node*<br>the node to add |

### AppendIndexer(token, identifier)

add an indexer to this node

| Name | Description |
| ---- | ----------- |
| token | *NSS.Blast.BlastScriptToken*<br> |
| identifier | *System.String*<br> |

#### Returns



### AsFloat

interpret the node's attached identifier as a floating point value, returns Blast.InvalidNumeric if it could not parse the identifier as a numeric

### CheckIfCouldBeVectorList
check if a node is a vector, its children should all be - identifiers - functions - compounds ( todo -> should validate if they result in a single number.... )
### CheckIfFunctionIsUsedInTree(op)

check if a given function is used in this node or its children

| Name | Description |
| ---- | ----------- |
| op | *NSS.Blast.blast_operation*<br>the op representing the function |

#### Returns

true if used

### ChildCount

number of child nodes below this node

### children

children of node

### constant_op

any operation connected to this node (type == function | operation | parameter (pop))

### CountChildNodes(n)

get the total number of nodes in the children of n

| Name | Description |
| ---- | ----------- |
| n | *NSS.Blast.Compiler.node*<br>the node to count all child nodes of |

#### Returns



### CountChildren(NSS.Blast.Compiler.nodetype)

count children of given nodetype

#### Returns

number of children matching type t

### CountChildType(NSS.Blast.Compiler.nodetype,NSS.Blast.Compiler.nodetype)

count all children matching one of 2 types

### CountChildType(type)

count child nodes of the given type

| Name | Description |
| ---- | ----------- |
| type | *NSS.Blast.Compiler.nodetype*<br>the nodetype to count |

#### Returns



### CountNodes

get the total number of nodes in the tree as seen from current node

### CountOtherChildren(NSS.Blast.Compiler.nodetype)

count nr of childnodes with not nodetype t

#### Returns

number of children not matching nodetype t

### CreateChild(type, token, identifier, index)

create a new node as a child of this node and returns the newly created node

| Name | Description |
| ---- | ----------- |
| type | *NSS.Blast.Compiler.nodetype*<br>nodetype to create |
| token | *NSS.Blast.BlastScriptToken*<br>token to set |
| identifier | *System.String*<br>identifier used |
| index | *System.Int32*<br>index at which to insert node |

#### Returns

the newly created node

### CreateChild(type, token, identifier)

create a new node as a child of this node and returns the newly created node

| Name | Description |
| ---- | ----------- |
| type | *NSS.Blast.Compiler.nodetype*<br>nodetype to create |
| token | *NSS.Blast.BlastScriptToken*<br>token to set |
| identifier | *System.String*<br>identifier used |

#### Returns

the newly created node

### CreateConstantParameter(value_0)

create a constant value parameter from operation

| Name | Description |
| ---- | ----------- |
| value_0 | *NSS.Blast.blast_operation*<br>the value to insert |

#### Returns

the newly created paramater node with a constant value set

### CreatePopNode(blast, related_push)

create a pop node based on the information pushed, links the push and pop together

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br>current engine data |
| related_push | *NSS.Blast.Compiler.node*<br>the earlier push op |

#### Returns



### CreatePushNode(blast, topush)

create a push node with the information from the given node, THIS DOES NOT ADD THAT NODE AS CHILD

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br>blast engine data |
| topush | *NSS.Blast.Compiler.node*<br>node to push |

#### Returns

returns the pushing node

### DeepClone

deep clones node without root parent set

#### Returns



### DependencyCount

get the number of dependency nodes

### depends_on

dependencies of node

### encode44(NSS.Blast.Compiler.node,System.Byte)

-encode vectorsize in lower nibble -encode parametercount in high nibble

### encode44(NSS.Blast.Compiler.node)

-encode vectorsize in lower nibble -encode childcount == parametercount in high nibble

### EnsureIdentifierIsUniquelySet(tag)

make sure the identifier is set to a UniqueID if it is not set a new id is generated

| Name | Description |
| ---- | ----------- |
| tag | *System.String*<br>name to use for reference while debugging |

### FirstChild

first child of node, null if there are no children

### FirstConsecutiveOperationSequence(node, min_group_size, from, op, op_count, first_op_in_sequence)

get the largest group of operations of the same type

| Name | Description |
| ---- | ----------- |
| node | *NSS.Blast.Compiler.node*<br>the parent node of the operation list |
| min_group_size | *System.Int32*<br>minimal group size |
| from | *System.Int32*<br>start check from this node |
| op | *NSS.Blast.blast_operation@*<br>outputs operation of largest group or nop |
| op_count | *System.Int32@*<br>nr of operations in group |
| first_op_in_sequence | *NSS.Blast.Compiler.node@*<br> |

#### Returns



### FirstConsecutiveOperationSequence(min_groupsize, from, op, op_count, first_op_in_sequence)

scan children of node for the first group of operations of a given minimal size

| Name | Description |
| ---- | ----------- |
| min_groupsize | *System.Int32*<br>the minimal group size |
| from | *System.Int32*<br>start check from this node |
| op | *NSS.Blast.blast_operation@*<br>operation to scan for |
| op_count | *System.Int32@*<br>the operation count in the group found |
| first_op_in_sequence | *NSS.Blast.Compiler.node@*<br>first operation found in sequence |

#### Returns



### function

if the node is a function then its this one

### GenerateUniqueId(tag)

generate a unique id based on a guid

| Name | Description |
| ---- | ----------- |
| tag | *System.String*<br>name to use for reference while debugging |

#### Returns



### GetChild(first_choice, second_choice)

get first child matching first choice, if none found, try the second choice

| Name | Description |
| ---- | ----------- |
| first_choice | *NSS.Blast.Compiler.nodetype*<br>first to try to locate |
| second_choice | *NSS.Blast.Compiler.nodetype*<br>next attemt to locate |

#### Returns

a node if any was found, otherwise null

### GetChild(NSS.Blast.Compiler.nodetype)

get the first child found of a given nodetype

### GetChildren(NSS.Blast.Compiler.nodetype)

get children of given nodetype

#### Returns

an array of nodes

### GetConstantFloat4Value(NSS.Blast.Compiler.IBlastCompilationData)

get the constant float4 value encoded by the variable - float4: vector size is checked and errors will be logged if incorrect

### GetConstantFloatValue(NSS.Blast.Compiler.IBlastCompilationData)

get the constant float value encoded by the variable - float: vector size is checked and errors will be logged if incorrect

#### Returns



### GetLeafNodes

get all leaf nodes from this node

#### Returns



### GetLeafNodes(leafs, n)

gather all leaf nodes from a given node

| Name | Description |
| ---- | ----------- |
| leafs | *System.Collections.Generic.List{NSS.Blast.Compiler.node}*<br>leaf node list to use |
| n | *NSS.Blast.Compiler.node*<br>node to gather leafs from |

### GetMaximumTreeDepth

get maximum depth of node tree starting from this node

#### Returns

depth from this node until deepest leaf

### GetMaximumTreeDepth(depth)

get maximum depth of node tree starting from this node

| Name | Description |
| ---- | ----------- |
| depth | *System.Int32*<br>depth from this node until deepest leaf |

#### Returns

depth from this node until deepest leaf

### GetNodeDescription

get a textual description of this node

#### Returns

the text description

### GetOtherChildren(t)

get child nodes not of the type t

| Name | Description |
| ---- | ----------- |
| t | *NSS.Blast.Compiler.nodetype*<br>the nodetype to discriminate |

#### Returns

an array of nodes

### HasChildNodes

True if the node contains children

### HasChildren

true if the node contains child nodes

### HasDependencies

true if the node has dependencies

### HasIdentifier

true if node is represented by an identifier

### HasIndexers

true if node contains indexers

### HasOneChild

true if the node has exactly 1 node

### HasSingleCompoundAsChild

check if we have 1 child and that it is a compounded statement list

#### Returns



### identifier

any identifier attached to this node

### indexers

BS2: indexers, arrays and compound types [].

### InsertBeforeThisNodeInParent(type, token)

insert a new node of the given type and operation before this node in parent

| Name | Description |
| ---- | ----------- |
| type | *NSS.Blast.Compiler.nodetype*<br>node type |
| token | *NSS.Blast.BlastScriptToken*<br>token for script operation |

### InsertChild(System.Int32,NSS.Blast.Compiler.node)

insert a child not at given index - removes new child from old parent - set new childs parent to this node

### InsertDependency(ast_node)

insert (actually it appends) a depenency, updateing parent and chldren list

| Name | Description |
| ---- | ----------- |
| ast_node | *NSS.Blast.Compiler.node*<br>the node to append |

### InsertParent(node)

insert a node as new parent to this node => before: Parent.Child, after: Parent.NewNode.Child

| Name | Description |
| ---- | ----------- |
| node | *NSS.Blast.Compiler.node*<br>the node to insert/replace as a new parent |

### is_constant

true if the node represents a constant value

### is_vector

true if the value represented is a vector, dont use this directly as the compilers interpretation might change during the process. check variable or function property instead to find out if something is a vector

### IsAssignment

True if this is an assignment

### IsCompound

True if this a compound node

### IsCompoundWithSingleNegationOfValue

check if the node IS: [compound][-][param|pop_or_val][/compound]

### IsCompoundWithSingleNegationOfValue(node)

check if the node IS: [compound][-][param|pop_or_val][/compound]

| Name | Description |
| ---- | ----------- |
| node | *NSS.Blast.Compiler.node*<br>the node that should be the compound in the check |

### IsFlat(System.Boolean)

check if the node is a flat node - contains NO compounds - contains no object with children other then a function

#### Returns



### IsFlatParameterList(nodes)

check if the list of given nodes is flat - no nested things - no function calls ?? might want to be looser here... todo

| Name | Description |
| ---- | ----------- |
| nodes | *System.Collections.Generic.IEnumerable{NSS.Blast.Compiler.node}*<br>node list to check |

#### Returns



### IsFloat

interpret this node as a float value and return that

### IsFunction

True if this is a function

### IsLeaf

True if this is a leaf nod

### IsNonNestedVectorDefinition

check if this node is a definition of a vector that does not nest: (1 1 1 1) (1 pop pop) (2 maxa(1) 2 3) (3, -1 2 2) => (3 (-1) 2 2)

#### Returns



### IsNonNestedVectorDefinition(n)

check if given node contains a non nested vector define: node = (1 2 3 4) | node = (1 2 (-3) 4)

| Name | Description |
| ---- | ----------- |
| n | *NSS.Blast.Compiler.node*<br>the node to check |

#### Returns

true if it does

### IsOperation

True if this is an operation

### IsOperationList

check if the node is an operation sequence in the form: 3 + a + 4 + 4 + max(3093) + (4 + 0)

### IsOperationList(node, singleop)

check if the node is an operation sequence in the form: 3 + a + 4 + 4 + max(3093) + (4 + 0)

| Name | Description |
| ---- | ----------- |
| node | *NSS.Blast.Compiler.node*<br>the node to check |
| singleop | *NSS.Blast.blast_operation@*<br>the operation found, if single it maps to the operation, if none its nop, on many different it will be op.ex |

#### Returns

true if a list of operations

### IsOperationList(node)

check if the node is an operation sequence in the form: 3 + a + 4 + 4 + max(3093) + (4 + 0)

| Name | Description |
| ---- | ----------- |
| node | *NSS.Blast.Compiler.node*<br>the node to check |

#### Returns



### IsPopFunction

True if this is a function popping from the stack

### IsPushFunction

True if this is a function pushing to the stack

### IsRoot

Only true if this is the root of the ast

### IsScriptVariable

True if this node represents a scripted variable

### IsSingleOperationList(NSS.Blast.blast_operation@)

check if this node contains an operation sequence with only 1 different operator: a = 1 * 3 * 3 * 4;

#### Returns

true if an operation list and all operations used are the same

### IsSingleValueOrPop

determine if the node is a single value or a pop operation

### IsSingleValueOrPop(NSS.Blast.Compiler.node)

determine if the node is a single value or a pop operation

### IsVector

True if this is data with a cardinality larger then 1 (a vector)

### IsVectorDefinition(n)

check if a node equals a vector definition: -> ( 1 2 3 ) -> compound[3] ( id id id ) -> compound[n] ( n[pop | identifier[1]] ) -> root node == compound with n children representing its elements

| Name | Description |
| ---- | ----------- |
| n | *NSS.Blast.Compiler.node*<br> |

#### Returns



### LastChild

last child of node, null if there are no children, equals first if childcount == 1

### linked_pop

internal use: a linked pop operation, used during compilation to keep track of pushpop pairs

### linked_push

internal use: a linked push operation, used during compilation to keep track of pushpop pairs

### parent

the parent node, null if the node is the root

### ReduceSingularCompounds(node)

recursively reduces unneeded compound nesting (((2 3))) => (2 2)

| Name | Description |
| ---- | ----------- |
| node | *NSS.Blast.Compiler.node*<br>the root node of the nested compound |

### SetChild(ast_node, index)

set a node to be a child of this node (appends to end of child list), updates the parent of the node and removes it from its possible previous parent

| Name | Description |
| ---- | ----------- |
| ast_node | *NSS.Blast.Compiler.node*<br>the node to set as child is returned |
| index | *System.Int32*<br>index to insert at at parent |

### SetChild(ast_node)

set a node to be a child of this node (appends to end of child list), updates the parent of the node and removes it from its possible previous parent

| Name | Description |
| ---- | ----------- |
| ast_node | *NSS.Blast.Compiler.node*<br>the node to set as child is returned |

### SetChildren(nodes)

set a list of nodes a children to this node

| Name | Description |
| ---- | ----------- |
| nodes | *System.Collections.Generic.IEnumerable{NSS.Blast.Compiler.node}*<br>the nodes to set as child |

#### Returns

this node

### SetDependency(ast_node)

set a dependency for this node, some constructs such as loops use this for the initializer

| Name | Description |
| ---- | ----------- |
| ast_node | *NSS.Blast.Compiler.node*<br>the node to add to dependencies |

### skip_compilation

skip general compilation of this node, some nodes control when to compile their own dependencies like initializers in loops

### token

any token attached to this node

### ToNodeTreeString(indentation)

generate a multiline string representing the node tree structure

| Name | Description |
| ---- | ----------- |
| indentation | *System.Int32*<br>nr of space to indent for each child iteration |

### ToString

provides information in debug display through a tostring overload

#### Returns

node formatted as string

### type

nodetype of node

### variable

variable data inferred from the ast and connected to the nodes identifier

### vector_size

the vector size


## nodetype

the different nodetypes used in the ast

### assignment

this node represents an assignment to identifier

### compound

represents a compound: ( () )

### condition

a condition, either in if statements or while/for loops

### forloop

the root of a for loop

### function

this node represents a function

### ifelse

the ifelse clausule

### ifthen

the ifthen clausule

### ifthenelse

the root of an if then else structure

### index

BS2 parameter indexer, .[]

### jump_to

a jump instruction inserted by the compiler that jumps to a given label in the ast

### label

a label (a jump target) inserted by the compiler

### none

nodetype is not set

### operation

node represents an operation: +-/ etc.

### parameter

node represents a parameter to a function or sequence with identifier name/value

### root

this is the root node

### switchcase

a switch case

### switchdefault

the default case

### switchnode

the switch statement root node, transformed into ifthenelse statements during compilation

### whilecompound

the while loop body, handled as a compound

### whileloop

the root of a while loop

### yield

yield operation, must be in root


## BlastAnalysis

Basic Node Analysis - force multiplication rules - simplifies arithmetic - refactors divisions

### analyze_node(n)

analyze a node and its children, can be run in parallel on different node roots

| Name | Description |
| ---- | ----------- |
| n | *NSS.Blast.Compiler.IBlastCompilationData*<br> |

### apply_multiplication_rules(data, n)

apply rules of multiplication if needed to children of this node

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| n | *NSS.Blast.Compiler.node*<br> |

### Execute(data)

analyse ast tree and perform corrections/optimizations

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |

### refactor_divisions(data, n)

refactor divisions into multiplications with inverse of constants where possible

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| n | *NSS.Blast.Compiler.node*<br> |

### simplify_compound_arithmetic(NSS.Blast.Compiler.IBlastCompilationData,NSS.Blast.Compiler.node)

simplify non-vector non-function compounds by removing nested compounds when operations allow it. -> all operations equal then move compound up, returns nr of moves made

### simplify_node(NSS.Blast.Compiler.IBlastCompilationData,NSS.Blast.Compiler.node)

simplify nodes until no changes occur


## BlastBytecodeCompiler

Blast Compiler Stage - compiles the ast into bytecode

### AnalyzeCompoundNesting(data, root)

analyze node tree structure, find any nested compound that shouldnt be - fix simple cases - error on others - this 'analysis' must always run independant of analyzer

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.CompilationData*<br>compiler data |
| root | *NSS.Blast.Compiler.node*<br>root to start from |

#### Returns

success or error code

### CompileAST(data)

Compile the abstract syntax tree into bytecode

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.CompilationData*<br>compilerdata, among which the AST |

#### Returns

a list of bytecode, null on failure

### CompileFunction(data, ast_function, code)

Compile a function and its parameters

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.CompilationData*<br> |
| ast_function | *NSS.Blast.Compiler.node*<br>the node/function to compile |
| code | *NSS.Blast.Compiler.Stage.IMByteCodeList*<br> |

#### Returns

true on success, false otherwise, errors will be logged in data

### CompileNode(data, ast_node, code)

Compile a node into bytecode

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.CompilationData*<br> |
| ast_node | *NSS.Blast.Compiler.node*<br>the node to compile, may not be the root ast node |
| code | *NSS.Blast.Compiler.Stage.IMByteCodeList*<br>an optional existing codelist to append to |

#### Returns

an intermediate bytecode list

### CompileNodes(data, ast_root)

compile all nodes in the given root node into intermediate bytecode - if allowed by options, all child nodes will be processed in parallel

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.CompilationData*<br>compiler data |
| ast_root | *NSS.Blast.Compiler.node*<br>the root node to compile |

#### Returns

a list with bytecode possibly with extra data, hence intermediate bytecode

### CompileParameter(data, ast_param, code, allow_pop)

compile a single parameter node into the code stream

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.CompilationData*<br> |
| ast_param | *NSS.Blast.Compiler.node*<br>the parameter node |
| code | *NSS.Blast.Compiler.Stage.IMByteCodeList*<br>the code to append to |
| allow_pop | *System.Boolean*<br> |

#### Returns

false on failure

### CompileParameters(data, ast_function, code, parameter_nodes, min_validate, max_validate)

compile a list of nodes as a list of parameters

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.CompilationData*<br> |
| ast_function | *NSS.Blast.Compiler.node*<br>the node with the function |
| code | *NSS.Blast.Compiler.Stage.IMByteCodeList*<br>the bytecode to add compiled code to |
| parameter_nodes | *System.Collections.Generic.IEnumerable{NSS.Blast.Compiler.node}*<br>the parameter list |
| min_validate | *System.Int32*<br>min parameter count, error will be raised if less |
| max_validate | *System.Int32*<br>max parameter count, error will be raised if more |

#### Returns



### Execute(data)

Execute the compilation stage, prepares bytecode from the AST

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br>compiler data |

#### Returns

non zero on error conditions

### GetOperationOpCode(data, token)

translate a token representing an operation into its matching opcode, logs an error if operation cant be mapped

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| token | *NSS.Blast.BlastScriptToken*<br>the token to map |

#### Returns

script opcode

### StageType

Compilation Stage

### Version

Version 0.1.0 - Initial


## BlastBytecodeOptimizer

Bytecode Optimizer - optimizes bytecode based on pattern recognition

### Execute(data)

execute the bytecode optimizer

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br>compilationdata with code set |

#### Returns

nonzero exitcode on failure

### Optimize(cdata, segment)

optimize all code segments

| Name | Description |
| ---- | ----------- |
| cdata | *NSS.Blast.Compiler.CompilationData*<br> |
| segment | *Unknown type*<br> |

#### Returns



### OptimizePatterns(data, code)

scan and replace patterns

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.CompilationData*<br>compiler data |
| code | *NSS.Blast.Compiler.Stage.IMByteCodeList*<br>code to optimize |

#### Returns

false on failure, logs errors in compilerdata

### optimizer_pattern.match(result, ops, i, matched_pattern)

match pattern at i

| Name | Description |
| ---- | ----------- |
| result | *NSS.Blast.Compiler.CompilationData*<br> |
| ops | *NSS.Blast.Compiler.Stage.IMByteCodeList*<br> |
| i | *System.Int32*<br> |
| matched_pattern | *NSS.Blast.Compiler.Stage.BlastBytecodeOptimizer.optimizer_pattern@*<br> |

#### Returns

true on match

### NSS.Blast.Compiler.Stage.BlastCSCompiler.Execute(data)

compile script using the cs compiler supplied with .net

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |

#### Returns




## BlastFlatten

Flatten Nodes - removes all nested things and reduces them to a linear stream of instructions using stack operations

### FlattenAssignment(NSS.Blast.Compiler.IBlastCompilationData,NSS.Blast.Compiler.node@,System.Collections.Generic.List{NSS.Blast.Compiler.node}@,System.Boolean,NSS.Blast.Compiler.node@)

flatten assignement node

### FlattenCompound(data, compound, flattened_output)

flatten a compound

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| compound | *NSS.Blast.Compiler.node@*<br> |
| flattened_output | *System.Collections.Generic.List{NSS.Blast.Compiler.node}@*<br> |

#### Returns



### FlattenFunction(data, function, flattened_output, push_function, pusher)

flatten a function into a list of flat operations, its optional to push the resulting function to the end of the list and return the pushing node reference

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| function | *NSS.Blast.Compiler.node@*<br> |
| flattened_output | *System.Collections.Generic.List{NSS.Blast.Compiler.node}@*<br> |
| push_function | *System.Boolean*<br> |
| pusher | *NSS.Blast.Compiler.node@*<br> |

#### Returns



### FlattenFunctionParameters(data, function, flattened_output)

flatten a list of function parameters

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| function | *NSS.Blast.Compiler.node@*<br> |
| flattened_output | *System.Collections.Generic.List{NSS.Blast.Compiler.node}@*<br> |

#### Returns



### FlattenIfThenElse(NSS.Blast.Compiler.IBlastCompilationData,NSS.Blast.Compiler.node)

flatten an ifthenelse construct

### FlattenStatements(data, root, flat)

Flatten the statement

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| root | *NSS.Blast.Compiler.node*<br> |
| flat | *System.Collections.Generic.List{NSS.Blast.Compiler.node}@*<br> |

#### Returns



### FlattenWhileLoop(NSS.Blast.Compiler.IBlastCompilationData,NSS.Blast.Compiler.node)

flatten a while loop (which might originally have been a for loop dueue to transform stage) - pops away operations from condition - generates flat list of statements for loop compound - maintains same root object --- THE WHILELOOP SHOULD BE EXCLUDED FROM NESTING TESTS --- while this nests in the node tree it nests control flow and that will flatten out when compiling into jumps


## BlastHPCCompiler

Blast Compiler Stage - compiles the ast into hpc code for compile-time scripts

### CompileAST(data, indent)

Compile the abstract syntax tree into a c# job to be used as hpc for burst by unity

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.HPCCompilationData*<br>compilerdata, among which the AST |
| indent | *System.Int32*<br>indentation used in output |

#### Returns

a string containg the code

### CompileParameter(data, ast_param, code)

compile a single parameter node into the code stream

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.CompilationData*<br> |
| ast_param | *NSS.Blast.Compiler.node*<br>the parameter node |
| code | *System.Text.StringBuilder*<br>the code to append to |

#### Returns

false on failure

### CompileParameters(data, ast_node, code, parameter_nodes, min_validate, max_validate)

compile a list of nodes as a list of parameters

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.CompilationData*<br> |
| ast_node | *NSS.Blast.Compiler.node*<br>the node with the function |
| code | *System.Text.StringBuilder*<br>the stringbuilder to add hpc code to |
| parameter_nodes | *System.Collections.Generic.IEnumerable{NSS.Blast.Compiler.node}*<br>the parameter list |
| min_validate | *System.Int32*<br>min parameter count, error will be raised if less |
| max_validate | *System.Int32*<br>max parameter count, error will be raised if more |

#### Returns



### Execute(data)

Execute the compilation stage, prepares c# code ready for the burst compiler

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br>compiler data |

#### Returns

non zero on error conditions

### GetFunctionName(data, function)

get the name of the function in the target hpc

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.CompilationData*<br>compilation data |
| function | *NSS.Blast.BlastScriptFunction*<br>the function to get the name for |

#### Returns

the hpc function name

### GetOperationString(data, token)

Get a string representing the token in the target

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.CompilationData*<br>compiler data (logging) |
| token | *NSS.Blast.BlastScriptToken*<br>the token to translate |

#### Returns

the operation translated to target operation text

### StageType

= HPC Compilation Stage

### Version

Version 0.1


## BlastHPCStackResolver

Stack Resolver for HPC code - transmute push-pops to stack-var assignments - re-use variables as much as possible


## BlastJumpResolver

Resolve Jumps

### Execute(NSS.Blast.Compiler.IBlastCompilationData)

resolve all jumps - connect jump-offsets with jump labels

### ResolveJumps(cdata, code)

Resolve all jumps

| Name | Description |
| ---- | ----------- |
| cdata | *NSS.Blast.Compiler.CompilationData*<br>compilation data |
| code | *NSS.Blast.Compiler.Stage.IMByteCodeList*<br>intermediate bytecode |

#### Returns

true on success


## BlastOptimizer

Basic Optimization Stage

### Execute(NSS.Blast.Compiler.IBlastCompilationData)

Optimize operations expressed by the ast if optimization is enabled through compiler settings

### OptimizeAssignFunction(data, node)

analyze the assignment and optimize 2 statement types: 1> a = function(parameters); => assignf a parameters 2> b = - function(paramaters); => assignf - a parameters

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| node | *NSS.Blast.Compiler.node*<br> |

#### Returns



### ReplaceSequence(blast, node, singleop, replacement_function, from, operation_count)

replace sequence IN PLACE with a function

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br>blast engine data -> needs access to functions |
| node | *NSS.Blast.Compiler.node*<br>node to be updated |
| singleop | *NSS.Blast.blast_operation*<br>the singleop |
| replacement_function | *NSS.Blast.blast_operation*<br>the replacement fucntion |
| from | *System.Int32*<br>only use childnodes starting from this index |
| operation_count | *System.Int32*<br>the number of operations to replace if > 0 |

#### Returns



### StageType

optimizer stage

### Version

V0.1.0 - initial version


## BlastPackaging

Package Stage: process compiled bytecode into packages

### Execute(data)

package bytecode into script package

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |

#### Returns



### PackageIntermediate(cdata, code)

package the compiled code into BlastIntermediate

| Name | Description |
| ---- | ----------- |
| cdata | *NSS.Blast.Compiler.CompilationData*<br> |
| code | *NSS.Blast.Compiler.Stage.IMByteCodeList*<br>the code to package |

#### Returns

non-zero error code on failure

### StageType

Packaging Stage -> creates package

### Version

Version 0.1


## BlastParameterAnalysis

Parameter Analysis - determine parameter types (float, vectorsize) - confirm inputs used (warnings if not) and outputs set (not set = error) - validate correct parameter usage

### check_if_vector(data, leaf_node)

perform a check to see if a node results in a vector

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| leaf_node | *NSS.Blast.Compiler.node*<br> |

### Execute(data)

the parameter analyzer only looks at the parameters and their usage - !! it wont make any node changes !! - checks vectorsizes - checks input/output settings -

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br>current compilationdata |

#### Returns

0 for success, other exitcode = error

### StageType

compiler stage: parameter analysis

### Version

v0.1.0 - initial version


## BlastParser

The Parser: - Parses list of tokens into a tree of nodes representing the flow of operations - Identifies unique parameters - Spaghetti warning - handcrafted parser ahead..

### check_if_assignment_node(data, node)

check if the node is an assignment

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| node | *NSS.Blast.Compiler.node*<br>node to map out |

#### Returns



### Execute(data)

execute the parser stage: - parse tokens into node tree - map identifiers (indexers, functions, constants)

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br>compilation data |

#### Returns

exitcode, 0 == success

### find_next_skip_compound(data, token, idx, max, i1)

search for the next token skipping over compounds

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| token | *NSS.Blast.BlastScriptToken*<br>token to look for |
| idx | *System.Int32*<br>idx to start looking from |
| max | *System.Int32@*<br>max idx to look into |
| i1 | *System.Int32@*<br>idx of token |

#### Returns

true if found

### find_next_skip_compound(data, token, idx, max, i1)

search for the next token skipping over compounds

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| token | *NSS.Blast.BlastScriptToken[]*<br>token to look for |
| idx | *System.Int32*<br>idx to start looking from |
| max | *System.Int32@*<br>max idx to look into |
| i1 | *System.Int32@*<br>idx of token |

#### Returns

true if found

### find_next_statement(data, idx, i1, i2)

scan token tree and find start and end index of next statement in token list

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| idx | *System.Int32@*<br>current index into token list |
| i1 | *System.Int32*<br>start index of next statement |
| i2 | *System.Int32@*<br>end index of next statement |

### find_next(data, token, idx, max, i1, skip_over_compounds, accept_eof)

find next token from idx

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| token | *NSS.Blast.BlastScriptToken*<br> |
| idx | *System.Int32*<br>idx to start looking from |
| max | *System.Int32@*<br>max index to check into |
| i1 | *System.Int32@*<br>token location or -1 if not found |
| skip_over_compounds | *System.Boolean*<br>skip over ( ) not counting any token inside the (compound) |
| accept_eof | *System.Boolean*<br>accept eof as succesfull end of search |

#### Returns



### find_next(data, token, idx, max, i1)

scan for the next token of type

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| token | *NSS.Blast.BlastScriptToken*<br>token to look for |
| idx | *System.Int32*<br>idx to start looking from |
| max | *System.Int32@*<br>max idx to look into |
| i1 | *System.Int32@*<br>idx of token |

#### Returns

true if found

### find_next(data, tokens, idx, max, i1, skip_over_compounds, accept_eof)

find next match in token array

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| tokens | *NSS.Blast.BlastScriptToken[]*<br> |
| idx | *System.Int32*<br>idx to start looking from |
| max | *System.Int32@*<br>max index to check into |
| i1 | *System.Int32@*<br>token location or -1 if not found |
| skip_over_compounds | *System.Boolean*<br>skip over ( ) not counting any token inside the (compound) |
| accept_eof | *System.Boolean*<br>accept eof as succesfull end of search |
 /// 
#### Returns



### find_next(data, token, idx, max, i1)

scan for the next token of type

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| token | *NSS.Blast.BlastScriptToken[]*<br>token to look for |
| idx | *System.Int32*<br>idx to start looking from |
| max | *System.Int32@*<br>max idx to look into |
| i1 | *System.Int32@*<br>idx of token |

#### Returns

true if found

### grow_index_chain(data, chain_root, idx, idx_max)

grow a chain of indices after some other node/token

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| chain_root | *NSS.Blast.Compiler.node*<br>node to index |
| idx | *System.Int32@*<br>token index to start reading chain from |
| idx_max | *System.Int32@*<br>max index to grow into |

#### Returns

chain root node with chain as children, or null on failure

### map_identifiers(data, ast_node)

map identifiers to variables - determine if a opcode constant (1,2 , pi and stuff) or just a constant number on the data stack

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br>compiler data |
| ast_node | *NSS.Blast.Compiler.node*<br>the node to scan including child nodes |

#### Returns

true if succeeded / IsOK

### NegateNodeInCompound(minus, n_function)

if minus: - insert a parent compound: parent.function => parent.compound.function - insert sibling with substract opcode

| Name | Description |
| ---- | ----------- |
| minus | *System.Boolean*<br> |
| n_function | *NSS.Blast.Compiler.node*<br> |

#### Returns



### parse_sequence(data, idx, idx_max)

parse a sequence of tokens between () into a list of nodes

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| idx | *System.Int32@*<br>index directly after the opening ( or at first token of sequence within () |
| idx_max | *System.Int32@*<br> |

#### Returns



### parse_statements(data, parent, idx_start, idx_max)

parse a statement list - depending on defines this may execute multithreaded

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| parent | *NSS.Blast.Compiler.node*<br>the parent node |
| idx_start | *System.Int32*<br>starting index into tokens |
| idx_max | *System.Int32*<br>max index in tokens to scan into |

#### Returns

exitcode - blasterror

### scan_and_parse_function(data, function, idx, idx_max)

scan and parse out the next function. function; function(); function(function(a, b), c); function(function(a, b)[2].x, c);

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br>general compiler data |
| function | *NSS.Blast.BlastScriptFunction*<br>function to parse |
| idx | *System.Int32@*<br>idx, starting at function, ending directly after |
| idx_max | *System.Int32@*<br>max index to scan into |

#### Returns

a node containing the function or null on failure

### scan_and_parse_identifier(data, idx, idx_max, add_minus)

scan input from idx building up 1 identifier as we go, after returning a valid node the scan index will be on the token directly after the identifier

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| idx | *System.Int32@*<br>the index starting the scan from and the must be on the first token of the identifier to parse. on succes it will be on the token directly after the identifier |
| idx_max | *System.Int32@*<br>the max index to scan into (max including) |
| add_minus | *System.Boolean*<br> |

#### Returns

null on errors, a valid node on success - can return nodes: function() and identifier[34].x

### scan_and_parse_numeric(data, idx, idx_max)

scan and parse a numeric from the token list in the form: -100.23

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| idx | *System.Int32@*<br>indext to start scan from, on success wil be at position after last token of identifier |
| idx_max | *System.Int32@*<br>the max index to scan into |

#### Returns

null on failure, a node with the value on success

### skip_closure(data, idx)

skip the closure () starting with idx at the (, if true ends with idx at position after )

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| idx | *System.Int32@*<br> |

#### Returns




## BlastPreCompileCleanup

Pre-Compile Cleanup - for now only cleans up parameter references


## BlastTokenizer

The Tokenizer: - splits input into list of tokens and identifiers - splits out: comments, defines and validations (all stuff starting with # until eol)

### Execute(data)

Execute the tokenizer stage

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br>compilation data |

#### Returns

success if ok, otherwise an errorcode

### is_token(System.Char)

check if char is a defined script token

#### Returns

true if a token

### is_whitespace(ch)

classify char as whitespace: space, tabs, cr/lf, , (comma)

| Name | Description |
| ---- | ----------- |
| ch | *System.Char*<br> |

#### Returns

true if a whitespace character

### parse_token(ch)

classify char as token, default to identifier

| Name | Description |
| ---- | ----------- |
| ch | *System.Char*<br> |

#### Returns



### read_input_output_mapping(data, comment, a, is_input)

read #input and #output defines

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| comment | *System.String*<br> |
| a | *System.String[]*<br> |
| is_input | *System.Boolean*<br> |

#### Returns

null on failure (also logs error in data)

### scan_to_comment_end(System.String,System.Int32)

read past eol

### StageType

Tokenizer -> converts input text into array of tokens

### Version

version


## BlastTransform

Transform higher level constructs into their simpler constituents, [while, for, switch] into ifthen sequences

### clone_nodes(nodes)

make a deepclone of the list of nodes

| Name | Description |
| ---- | ----------- |
| nodes | *System.Collections.Generic.IEnumerable{NSS.Blast.Compiler.node}*<br>input list to clone |

#### Returns

yields each cloned node

### reduce_simple_function_sequence(data, ast_node)

reduce a singular function in a sequence

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| ast_node | *NSS.Blast.Compiler.node*<br> |

#### Returns



### transform_for(data, n_for)

transform a for loop into a while statement

| Name | Description |
| ---- | ----------- |
| data | *NSS.Blast.Compiler.IBlastCompilationData*<br>compilation data holding the ast |
| n_for | *NSS.Blast.Compiler.node*<br>the node with the for loop |

### transform_switch(result, n_switch)

transform a switch into a series of ifthen statements

| Name | Description |
| ---- | ----------- |
| result | *NSS.Blast.Compiler.IBlastCompilationData*<br> |
| n_switch | *NSS.Blast.Compiler.node*<br>the node containing the switch statement |


## IMByteCode

intermediate bytecode - can contain additional data


## IMByteCodeList

list of intermediate bytecode

### Add(op, label)

add op to code list

| Name | Description |
| ---- | ----------- |
| op | *NSS.Blast.blast_operation*<br> |
| label | *NSS.Blast.Compiler.Stage.IMJumpLabel*<br>optional jump label |

#### Returns

the index of the op

### Add(code, label)

add code to list

| Name | Description |
| ---- | ----------- |
| code | *System.Byte*<br>the opcode byte |
| label | *NSS.Blast.Compiler.Stage.IMJumpLabel*<br>optional jump label |

#### Returns

returns index of opcode

### ReduceSegments

add all segments to this list clearing the segment list afterwards

### segments

segments, used when compiling multithreaded; the compiler will build a tree of codelists with segments after that following stages might run using multithreading on the segments


## IMJumpLabel

a jump label, for help keeping track of jump targets


## CompileTimeBlastScript

any script derived from this will be compiled during compilation/design public class BS1_compiletime : CompileTimeBlastScript { public override string Code => @"a = a + 1;"; }


## CoreAPI

Implements Core-API functionality

### Constructor(allocator)

Extend BlastScriptAPI (core just is a shell)

| Name | Description |
| ---- | ----------- |
| allocator | *Unity.Collections.Allocator*<br> |

### RegisterCoreAPI

register all base functions


## IBlastCompilerStage

a compiler stage - employs 1 step of the compilation process


## BlastInterpretor

V2 - use state machine instead of get_compound_result and internal grow-vector / operation sequence loop, should reduce load a lot on handling vectors state ---- read root statement ----\ \------read compound ----------/ \-----grow value-------------/ \-----get result ----------/

### BlastOperationIsValue(System.Byte@)

return true if op is a value: - pop counts!! - byte value between lowest constant and extended op id (dont allow constants in extended op id's)

#### Returns



### caller_ptr

optional pointer to caller information

### CallExternal(code_pointer, minus, vector_size, f4)

call an external function pointer

| Name | Description |
| ---- | ----------- |
| code_pointer | *System.Int32@*<br> |
| minus | *System.Boolean@*<br> |
| vector_size | *System.Byte@*<br> |
| f4 | *Unity.Mathematics.float4@*<br> |

#### Returns



### code

code segment pointer

### data

data segment pointer - for now each data element is 4 bytes long FIXED

### decode62(c, vector_size)

decode info byte of data, 62 uses the upper 6 bits from the parametercount and the lower 2 for vectorsize, resulting in 64 parameters and size 4 vectors.. - update to decode44? 16 params max and 16 vec size?

| Name | Description |
| ---- | ----------- |
| c | *System.Byte@*<br> |
| vector_size | *System.Byte@*<br> |

#### Returns



### engine_ptr

pointer to engine data

### environment_ptr

optional pointer to environment data

### execute(blast, environment, caller, resume_state)

execute bytecode

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineData**<br>engine data |
| environment | *System.IntPtr*<br>pointer to environment data in native memory |
| caller | *System.IntPtr*<br>pointer to caller data in native memory |
| resume_state | *System.Boolean*<br>resume state from yield or reset state to initial |

#### Returns

success

### execute(blast, environment, caller)



| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineData**<br> |
| environment | *System.IntPtr*<br> |
| caller | *System.IntPtr*<br> |

#### Returns



### Execute(blast, environment, caller)

execute bytecode

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br>engine data |
| environment | *System.IntPtr*<br>pointer to environment data in native memory |
| caller | *System.IntPtr*<br>pointer to caller data in native memory |

#### Returns

exit code

### Execute(NSS.Blast.BlastEngineDataPtr)

execute bytecode set to the interpretor

### get_abs_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

get absolute value of input - single input function - same output vector size as input

### get_adda_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

add all inputs together - n elements of equal vector size

### get_all_result(code_pointer, minus, not, vector_size)

convert all calls to all to !any( == 0) !any() is a lot cheaper then all() because we can drop out early and may not need to lookup every value ///

| Name | Description |
| ---- | ----------- |
| code_pointer | *System.Int32@*<br> |
| minus | *System.Boolean@*<br> |
| not | *System.Boolean@*<br> |
| vector_size | *System.Byte@*<br> |

#### Returns



### get_any_result(code_pointer, minus, not, vector_size)

a = any(a b c d)

| Name | Description |
| ---- | ----------- |
| code_pointer | *System.Int32@*<br> |
| minus | *System.Boolean@*<br> |
| not | *System.Boolean@*<br> |
| vector_size | *System.Byte@*<br> |

#### Returns



### get_atan_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

calculate arc tangent (radians) - 1 parameter fixed - outputvectorsize == inputvectorsize

### get_ceil_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

get value rounded up (ceiling) - 1 parameter fixed - outputvectorsize == inputvectorsize

### get_clamp_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

clamp a value between 2 others: math.clamp(a, min, max) - 3 parameters - equal vectorsize or min-max == 1 and a > 1 - input = output vectorsize

### get_compound_result(code_pointer, vector_size, return_first_result)

recursively handle a compounded statement and return its value - the compiler should flatten execution, this will save a lot on stack allocations but it wont flatten everything - the compiler should avoid writing bytecode that recursively uses compounds whenever possible

| Name | Description |
| ---- | ----------- |
| code_pointer | *System.Int32@*<br> |
| vector_size | *System.Byte@*<br> |
| return_first_result | *System.Boolean*<br>if true, it will return after getting the first result, used for non terminating groups (pushfunction) |

#### Returns



### get_cos_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

get cosine - 1 parameter fixed - outputvectorsize == inputvectorsize

### get_cosh_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

calculate cos-1 (radians) - 1 parameter fixed - outputvectorsize == inputvectorsize

### get_cross_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

cross product of 2 inputs - 2 input parameters - input vectorsize == 3 - output vectorsize == 3

### get_degrees_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

degrees from radians - 1 parameter fixed - outputvectorsize == inputvectorsize

### get_dot_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

get dot product of 2 paramaters - 2 inputs - inputvector size = any - output vectorsize == 1

### get_exp_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

raise e to given power - 1 parameter - input = output vectorsize

### get_exp10_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

get base 10 exponential for parameter - 1 parameter - input = output vectorsize

### get_floor_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

get value rounded down (floor) - 1 parameter fixed - outputvectorsize == inputvectorsize

### get_fma_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

fused multiply add - 3 float params: m1 * m2 + a1

#### Returns



### get_frac_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

get fraction(s) of value (math.frac) - 1 parameter fixed - outputvectorsize == inputvectorsize

### get_lerp_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

linear interpolation from a to b at step c - 3 inputs: 3 vectors equal size or first 2 equal and last = 1 - only numeric input - lerp((1 2), (10 20), 0.5); - lerp((1 2), (10 20), (0.5 0.1)); returns vector size of input values

### get_log_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

calculate natural logarithm - 1 input - input == output vectorsize

### get_log10_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

get base 10 logarithm - 1 parameter - input = output vectorsize

### get_log2_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

calc base2 log from params - 1 parameter - input == output vectorsize

### get_max_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

get max value [float] -> all parameters should have the same vectorsize as the output - returns vector of same size as input

### get_maxa_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

get the maximum value of all arguments of any vectorsize

### get_min_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

get min value - all params should have the same size - returns vector of same size as input

### get_mina_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

return the smallest of the arguments of any vectorsize

### get_mula_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

multiply all inputs together - equal sized vectors - n elements

### get_nlerp_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

normalized linear interpolation - 2 quaternion + float in returns float4/quaternion

### get_normalize_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

normalize vector - single vector input, size > 1 - same sized vector output

### get_pow_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

raise x to power of y - always 2 parameters - vectorsize in == vectorsize out

### get_rad_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

radians from degrees - 1 parameter fixed - outputvectorsize == inputvectorsize

### get_rsqrt_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

get reciprocal roots(s) of value (math.rsqrt) - 1 parameter fixed - outputvectorsize == inputvectorsize

### get_saturate_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

saturate a vector (clamp between 0.0 and 1.0 including 0 and 1) -

### get_select_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

3 inputs, first 2 any type, 3rd type equal or scalar bool select(a, b, condition) - input = outputvectorsize - 1 output

### get_sin_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

get sinus of value - 1 parameter fixed - outputvectorsize == inputvectorsize

### get_sinh_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

calculate sin-1 (radians) - 1 parameter fixed - outputvectorsize == inputvectorsize

### get_slerp_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

spherical linear interpolation - 2 quaternion + float in returns float4/quaternion

### get_sqrt_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

get roots(s) of value (math.sqrt) - 1 parameter fixed - outputvectorsize == inputvectorsize

### get_tan_result(System.Int32@,System.Byte@,Unity.Mathematics.float4@)

calculate tangent (radians) - 1 parameter fixed - outputvectorsize == inputvectorsize

### Handle_DebugData(code_pointer, vector_size, op_id, datatype, pdata)

handle command to show the given field in debug

| Name | Description |
| ---- | ----------- |
| code_pointer | *System.Int32*<br> |
| vector_size | *System.Byte*<br> |
| op_id | *System.Int32*<br> |
| datatype | *NSS.Blast.BlastVariableDataType*<br> |
| pdata | *System.Void**<br> |

### Handle_DebugStack

printout an overview of the datasegment/stack (if shared)

### IsBooleanOperation(NSS.Blast.blast_operation)

WARNING checks if boolean operaion, uses value op enum!!

### IsMathematicalOperation(NSS.Blast.blast_operation)

WARNING checks if +-*/ uses value op enum!!

### IsMathematicalOrBooleanOperation(NSS.Blast.blast_operation)

WARNING checks if is operation, uses value op enum blast_operation.add until blast_operation.not_equals

### max_iterations

maxiumum iteration count, usefull to avoid endless loop bugs

### metadata

metadata segment pointer

### opt_id

>= opt_id is starting opcode for parameters, everything until 255|ExOp is considered a datasegment index

### opt_value

>= if the opcode between opt_value and (including) opt_id then its an opcode for a constant

### pop_f1(System.Int32@)

pop float of vectorsize 1, forced float type, verify type on debug (equals pop_or_value)

### pop_or_value(code_pointer)

1.68 ms on 100000x on the same script as the non-branch version without the branch and 2 selects its 2.23 ms on the same test

| Name | Description |
| ---- | ----------- |
| code_pointer | *System.Int32@*<br> |

#### Returns



### pop_with_info(type, vector_size)

get the next value from the datasegment, stack or constant dictionary

| Name | Description |
| ---- | ----------- |
| type | *System.Int32@*<br>datatype of element popped |
| vector_size | *NSS.Blast.BlastVariableDataType@*<br>vectorsize of element popped |

#### Returns

pointer to data castable to valuetype*

### Reset(blast)

reset code_pointer and stack_offset to their initial states

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineData**<br>pointer to blast engine data |

### ResumeYield(blast, environment, caller)

resume executing bytecode after yielding

| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br>engine data |
| environment | *System.IntPtr*<br>pointer to environment data in native memory |
| caller | *System.IntPtr*<br>pointer to caller data in native memory |

#### Returns

exit code

### ResumeYield(NSS.Blast.BlastEngineDataPtr)

resume executing bytecode after yielding

### SetPackage(pkg, _code, _data, _metadata)

set package data from package and seperate buffers

| Name | Description |
| ---- | ----------- |
| pkg | *NSS.Blast.BlastPackageData*<br>the package data |
| _code | *System.Byte**<br>code pointer |
| _data | *System.Single**<br>datastack pointer |
| _metadata | *System.Byte**<br>metadata |

### SetPackage(NSS.Blast.BlastPackageData)

we might need to know if we need to copy back data (or we use a dummy)

### ValidationMode

stack segment pointer
 [NoAlias] [NativeDisableUnsafePtrRestriction] internal unsafe float* stack; 
if true, the script is executed in validation mode: - external calls just return 0's

### yield(f4_register)

yield - stacks state - note that it consumes 20 bytes of stack space (on top of max used by script) to use yield

| Name | Description |
| ---- | ----------- |
| f4_register | *Unity.Mathematics.float4*<br> |


## BlastReflect

provides utilities for finding and loading compile-time blast scripts and hpc jobs

### FindCompileTimeBlastScripts

get a list of scripts to compile during compilation of the unity project

### FindHPCJobs

find all hpc jobs compiled into the assemblies loaded


## BlastScriptRegistry

Here we maintain all scripts registered, either by manually calling Register(script) or by finding it in the binary through reflection. -> the registry is a static singleton -> this registry only stores script, not package data -> access is threadsafe s

### All

Enumerate all registred blast scripts

#### Returns

a blastscript ienumerator

### Exists(id)

lookup the id and check if it exists

| Name | Description |
| ---- | ----------- |
| id | *System.Int32*<br>the unique scriptid to search for |

#### Returns

true if found, false otherwise

### Exists(name)

scan the registry for a script with the given name

| Name | Description |
| ---- | ----------- |
| name | *System.String*<br>the case insensitive name to search for |

#### Returns

true if found, false otherwise

### Get(id)

lookup a script with a given script id

| Name | Description |
| ---- | ----------- |
| id | *System.Int32*<br>integer id, must be positive |

#### Returns

a script, or null if not found

### Get(name)

perform a linear scan for a script with the given name and return iot if found. Case Insensitive

| Name | Description |
| ---- | ----------- |
| name | *System.String*<br>the name to lookup |

#### Returns

the script if found or null if nothing was found with the given name

### Register(code, name, id)

register code with given name and id with registry

| Name | Description |
| ---- | ----------- |
| code | *System.String*<br>the script code to register |
| name | *System.String*<br>the name to attach, should be unique and is case insensitive |
| id | *System.Int32*<br>the script id to use, 0 to generate one, should be > 0 and unique |

#### Returns

the script id

### TryGetReferenceId(name, reference_id)

try to find the id of a script with a given name, performs a linear search

| Name | Description |
| ---- | ----------- |
| name | *System.String*<br>the case insensitive name to lookup |
| reference_id | *System.Int32@*<br>the script id |

#### Returns

true if a script with the given name was found


## ReservedBlastScriptFunctionIds

IDs reserved for functions used in blast, these get registered to blast with a name (that doesnt need to be equal)

### Debug

Output debuginformation to the debug stream about given parameter

### DebugStack

Output debuginformation to the debug stream

### Input

input mapping function - reserved for internal use

### Offset

all other functions start indexing from this offset

### Output

output mapping function - reserved for internal use

### Peek

Peek stack top

### Pop

Pop something from the stack

### Push

Push something to the stack

### PushCompound

Push the result from executing a compound onto the stack

### PushFunction

Push a function's return value to the stack

### PushVector

Push a vector directly onto the stack

### Seed

Seed the random number generator

### Yield

Yield execution


## BlastSSMDInterpretor

The SSMD Interpretor

### code

code segment pointer

### data

data segment pointer - for now each data element is 4 bytes long FIXED

### engine_ptr

pointer to engine data

### environment_ptr

optional pointer to environment data

### Execute(blast, environment, ssmddata, ssmd_data_count)



| Name | Description |
| ---- | ----------- |
| blast | *NSS.Blast.BlastEngineDataPtr*<br> |
| environment | *System.IntPtr*<br> |
| ssmddata | *NSS.Blast.BlastSSMDDataStack**<br> |
| ssmd_data_count | *System.Int32*<br> |

#### Returns



### Execute(packagedata, blast, environment, ssmddata, ssmd_data_count)



| Name | Description |
| ---- | ----------- |
| packagedata | *NSS.Blast.BlastPackageData@*<br> |
| blast | *NSS.Blast.BlastEngineDataPtr*<br> |
| environment | *System.IntPtr*<br> |
| ssmddata | *NSS.Blast.BlastSSMDDataStack**<br> |
| ssmd_data_count | *System.Int32*<br> |

#### Returns



### Execute(datastack, ssmd_data_count, f4_register)

main interpretor loop

| Name | Description |
| ---- | ----------- |
| datastack | *System.Byte***<br> |
| ssmd_data_count | *System.Int32*<br> |
| f4_register | *Unity.Mathematics.float4**<br> |

#### Returns



### get_fma_result(System.Void*,System.Int32@,System.Byte@,Unity.Mathematics.float4*@)

fused multiply add - always 3 params, input vector size == output vectorsize

#### Returns



### get_op_a_result(temp, code_pointer, vector_size, f4)

handle a sequence of operations - mula e62 p1 p2 .. pn - every parameter must be of same vector size - future language versions might allow multiple vectorsizes in mula

| Name | Description |
| ---- | ----------- |
| temp | *System.Void**<br>temp scratch data |
| code_pointer | *System.Int32@*<br>current codepointer |
| vector_size | *System.Byte@*<br>output vectorsize |
| f4 | *Unity.Mathematics.float4*@*<br>output data vector |

### GetCompoundResult(System.Void*,System.Int32@,System.Byte@)

process a compound, on function exit write back data to register

### handle_op_f1_f1(NSS.Blast.blast_operation@,System.Byte@,System.Byte@,System.Single*,Unity.Mathematics.float4*,System.Boolean@,System.Byte@)

handle operation a.x and b.x

### handle_op_f2_f1(NSS.Blast.blast_operation@,System.Byte@,System.Byte@,Unity.Mathematics.float4*,Unity.Mathematics.float4*,System.Boolean@,System.Byte@)

handle operation a.xy and b.xx

### handle_op_f2_f2(NSS.Blast.blast_operation@,System.Byte@,System.Byte@,Unity.Mathematics.float4*,Unity.Mathematics.float4*,System.Boolean@,System.Byte@)

handle operation a.xy and b.xy

### handle_op_f3_f1(NSS.Blast.blast_operation@,System.Byte@,System.Byte@,Unity.Mathematics.float4*,Unity.Mathematics.float4*,System.Boolean@,System.Byte@)

handle operation a.xyz and b.xxx

### handle_op_f3_f3(NSS.Blast.blast_operation@,System.Byte@,System.Byte@,Unity.Mathematics.float4*,Unity.Mathematics.float4*,System.Boolean@,System.Byte@)

handle operation a.xyz and b.xyz

### handle_op_f4_f1(NSS.Blast.blast_operation@,System.Byte@,System.Byte@,Unity.Mathematics.float4*,Unity.Mathematics.float4*,System.Boolean@,System.Byte@)

handle operation a.xyzw and b.xxxx

### handle_op_f4_f4(NSS.Blast.blast_operation@,System.Byte@,System.Byte@,Unity.Mathematics.float4*,Unity.Mathematics.float4*,System.Boolean@,System.Byte@)

handle operation a.xyz and b.xyz

### metadata

metadata segment pointer

### OperationIsSSMDHandled(op)

returns true for ssmd valid operations: add = 2, substract = 3, divide = 4, multiply = 5, and = 6, or = 7, not = 8, xor = 9, greater = 10, greater_equals = 11, smaller = 12, smaller_equals, equals, not_equals

| Name | Description |
| ---- | ----------- |
| op | *NSS.Blast.blast_operation*<br>the operation to check |

#### Returns

true if handled by the ssmd interpretor

### pop_f1_into(System.Int32@,System.Single*)

pop a float1 value form stack data or constant source and put it in destination

### pop_f1_with_op_into_f1(code_pointer, buffer, output, op)

pop a float1 value from data/stack/constants and perform arithmetic op ( + - * / ) with buffer, writing the value back to m11

| Name | Description |
| ---- | ----------- |
| code_pointer | *System.Int32@*<br>current code pointer |
| buffer | *System.Single**<br>buffer memory, may equal output |
| output | *System.Single**<br>output memory |
| op | *NSS.Blast.blast_operation*<br>the operation to perform |

### pop_f1_with_op_into_f4(code_pointer, buffer, output, op)

pop a float1 value from data/stack/constants and perform arithmetic op ( + - * / ) with buffer, writing the value back to m11

| Name | Description |
| ---- | ----------- |
| code_pointer | *System.Int32@*<br> |
| buffer | *System.Single**<br>temp buffer that may equal output |
| output | *Unity.Mathematics.float4**<br>output buffer that may equal temp buffer |
| op | *NSS.Blast.blast_operation*<br>operation to handle |

### pop_f2_with_op_into_f2(System.Int32@,Unity.Mathematics.float2*,Unity.Mathematics.float2*,NSS.Blast.blast_operation)

pop a float2 value from data/stack/constants and perform arithmetic op ( + - * / ) with buffer, writing the value back to output

### pop_f2_with_op_into_f4(code_pointer, buffer, output, op)

pop a float2 value from data/stack/constants and perform arithmetic op ( + - * / ) with buffer, writing the value back to m11

| Name | Description |
| ---- | ----------- |
| code_pointer | *System.Int32@*<br>current codepointer |
| buffer | *Unity.Mathematics.float2**<br>buffer that may equal output buffer |
| output | *Unity.Mathematics.float4**<br>output buffer |
| op | *NSS.Blast.blast_operation*<br>operation to execute on value |

### pop_f3_with_op_into_f3(System.Int32@,Unity.Mathematics.float3*,Unity.Mathematics.float3*,NSS.Blast.blast_operation)

pop a float3 value from data/stack/constants and perform arithmetic op ( + - * / ) with buffer, writing the value back to output

### pop_f3_with_op_into_f4(code_pointer, buffer, output, op)

pop a float2 value from data/stack/constants and perform arithmetic op ( + - * / ) with buffer, writing the value back to m11

| Name | Description |
| ---- | ----------- |
| code_pointer | *System.Int32@*<br> |
| buffer | *Unity.Mathematics.float3**<br> |
| output | *Unity.Mathematics.float4**<br> |
| op | *NSS.Blast.blast_operation*<br> |

### pop_f4_with_op_into_f4(System.Int32@,Unity.Mathematics.float4*,Unity.Mathematics.float4*,NSS.Blast.blast_operation)

pop a float4 value from data/stack/constants and perform arithmetic op ( + - * / ) with buffer, writing the value back to output

### pop_fx_into\`\`1(System.Int32@,\`\`0*)

pop a float[1|2|3|4] value form stack data or constant source and put it in destination

### pop_fx_into\`\`1(code_pointer, dataindex)

pop a float and assign it to dataindex inside a datasegment - shouldt the compiler just directly assign the dataindex (if possible)

#### Type Parameters

- T - 

| Name | Description |
| ---- | ----------- |
| code_pointer | *System.Int32@*<br> |
| dataindex | *System.Byte*<br> |

### push_data_f1(index)

push data value on stack

| Name | Description |
| ---- | ----------- |
| index | *System.Int32*<br>index of data to lookup |

### push_f1_pop_1(System.Int32@)

push a float1 value on te stack retrieved via 1 pop

### push_f2_pop_11(System.Int32@)

push a float2 value on te stack retrieved via 2x 1 pop - each element may have a diferent origen, we need to account for that

### push_f3_pop_111(System.Int32@)

push an float3 value on te stack retrieved via 3x 1 pop - each element may have a diferent origen, we need to account for that

### push_f4_pop_1111(System.Int32@)

push an float4 value on te stack retrieved via 4x 1 pop - each element may have a diferent origen, we need to account for that

### push_pop_f(System.Int32@,System.Int32@)

read codebyte, determine data location, pop data and push it on the stack

### push_register_f1

push register[n].x as float

### push_register_f2

push register[n].xy as float2 onto stack

### push_register_f3

push register[n].xyz as float3 onto stack

### push_register_f4

push register[n] as float4 onto stack

### set_data_from_register_f1(index)

set a float1 data location from register location

| Name | Description |
| ---- | ----------- |
| index | *System.Int32@*<br>data index |

### set_data_from_register_f2(index)

set a float2 data location from register location

| Name | Description |
| ---- | ----------- |
| index | *System.Int32@*<br>data index |

### set_data_from_register_f3(index)

set a float3 data location from register location

| Name | Description |
| ---- | ----------- |
| index | *System.Int32@*<br>data index |

### set_data_from_register_f4(index)

set a float4 data location from register location

| Name | Description |
| ---- | ----------- |
| index | *System.Int32@*<br>data index |

### set_register_from_data_f1(System.Single*)

set register[n].x from data

### set_register_from_data_f4(Unity.Mathematics.float4*)

set register[n].xyzw from data

### SetPackage(NSS.Blast.BlastPackageData@)

set ssmd package data

### stack_pop_f1_into(destination)

pop a float1 value from the stack and copy it into destination

| Name | Description |
| ---- | ----------- |
| destination | *System.Single**<br>destination f1* |


## StringBuilderCache

copied with minor changes from ms cli reference source https://referencesource.microsoft.com/#mscorlib/system/text/stringbuildercache.cs,40
