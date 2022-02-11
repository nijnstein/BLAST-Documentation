# BlastCompilerOptions Class
 

Options for compiling and packaging scripts


## Inheritance Hierarchy
<a href="https://docs.microsoft.com/dotnet/api/system.object" target="_blank" rel="noopener noreferrer">System.Object</a><br />&nbsp;&nbsp;NSS.Blast.Compiler.BlastCompilerOptions<br />
**Namespace:**&nbsp;<a href="26a25caa-f50b-92ad-f15c-dbb9db1493ae.md">NSS.Blast.Compiler</a><br />**Assembly:**&nbsp;BLAST (in BLAST.dll) Version: 1.0.0

## Syntax

**C#**<br />
``` C#
public class BlastCompilerOptions
```

**VB**<br />
``` VB
Public Class BlastCompilerOptions
```

**C++**<br />
``` C++
public ref class BlastCompilerOptions
```

**F#**<br />
``` F#
type BlastCompilerOptions =  class end
```

The BlastCompilerOptions type exposes the following members.


## Constructors
&nbsp;<table><tr><th></th><th>Name</th><th>Description</th></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="6072180b-2a27-ef6d-8b3e-c7df570a84a9.md">BlastCompilerOptions()</a></td><td>
initialize with default options</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="6d3c16b9-881f-5a5b-f806-821a09957d73.md">BlastCompilerOptions(BlastPackageMode)</a></td><td>
initilize default options in given packaging mode</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="26ff5555-6467-ea4b-a3d1-f52085f1bf2d.md">BlastCompilerOptions(Int32)</a></td><td>
initialize default options with given stacksize</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="6e26a388-b3fe-e847-ed3f-c4534561024e.md">BlastCompilerOptions(Int32, BlastPackageMode)</a></td><td>
initialize default options in given packagemode with a pre-determined stack size</td></tr></table>&nbsp;
<a href="#blastcompileroptions-class">Back to Top</a>

## Properties
&nbsp;<table><tr><th></th><th>Name</th><th>Description</th></tr><tr><td>![Public property](media/pubproperty.gif "Public property")![Static member](media/static.gif "Static member")</td><td><a href="90bbdec2-1534-a598-ab5c-378ba876f39c.md">Default</a></td><td>
Default compiler options: BS1 - Normal - Optimizing</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")![Static member](media/static.gif "Static member")</td><td><a href="dc749ecd-4ede-34c6-7a0a-6e41867f0f8a.md">Entity</a></td><td>
Default compiler options for packaging entities: BS1 - Entity Packagemode - Optimizing</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")![Static member](media/static.gif "Static member")</td><td><a href="521b4559-1656-0d58-bf9e-c3f5a01785d2.md">SSMD</a></td><td>
Default SSMD compiler options: BS1 - SSMD Packagemode - Optimizing</td></tr></table>&nbsp;
<a href="#blastcompileroptions-class">Back to Top</a>

## Methods
&nbsp;<table><tr><th></th><th>Name</th><th>Description</th></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="7eb6f20a-d779-38e2-64a6-1c814ba17b9b.md">AddDefine</a></td><td>
add a compiled define</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="81da5517-546b-65a8-a274-bd12dae80ba1.md">ClearDefines</a></td><td>
remove all defines from compiler options</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="5e1376b8-5d4d-d074-74c3-89f594dc3df1.md">DisableOptimisations</a></td><td>
disable compiler optimisations, default = enabled</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="cfd12fa8-43c1-05b9-262f-ad0ffb00e671.md">EnableOptimisations</a></td><td>
enable compiler optimizations, default == enabled</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="3cfdcf57-9ef5-308c-f54d-20504e32ce27.md">EnableValidation</a></td><td>
enable validation (default = off)</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="d676ae07-2bdf-db11-da00-76f8a76b6a67.md">IsDefined</a></td><td>
Check if the key is defined in compiler options</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="9692e186-150a-bca9-4878-c7b34c6da040.md">PackageWithoutStack</a></td><td>
package without a stack segment, use stackmemory in the interpretor</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="2b0d0440-fe60-d991-c92d-051703d92e99.md">RemoveDefine</a></td><td>
Remove any value possibly assosiated with the key</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="b738c6ce-4152-d5d6-01c0-c2d0b51031b4.md">SetAllocator</a></td><td>
Set allocation mode for packages, use temp with caution in combination with bursted code</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="459c0974-c729-cb1a-ce40-b288e3e37c40.md">SetLanguage</a></td><td>
Set language target</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="490fcf12-8cdc-20d4-05da-8e331f7cea07.md">SetPackageMode</a></td><td>
Set packaging mode</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="f806255d-b26e-fd63-3d84-9f2859031201.md">SetStackSize</a></td><td>
set the size of the stack, if 0 is set stack is estimated during compilation</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="ab79c9b2-1d01-f880-5c00-87210ce9c285.md">Silent</a></td><td>
disable all logging, fails silently</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="b07b7825-b6bb-054f-5991-7bdd0c57e264.md">Trace</a></td><td>
set trace logging</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="a0380bb8-24fc-ef79-ca20-b4e7b9546dae.md">TryGetDefine</a></td><td>
Try to lookup a key and get its value</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="d56b6b39-ea2f-1895-c9ae-0edab30c77d4.md">Verbose</a></td><td>
set verbose logging</td></tr></table>&nbsp;
<a href="#blastcompileroptions-class">Back to Top</a>

## Fields
&nbsp;<table><tr><th></th><th>Name</th><th>Description</th></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="5919ed53-d883-de0c-9980-58ebba12186c.md">AutoValidate</a></td><td>
run validation if set in script</td></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="c2f22248-2faf-d6f8-2855-fc7c63cfaf48.md">CompileDebug</a></td><td>
compile the debug function only if enabled</td></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="57af8bc2-efa7-0e28-fb42-21b490046b20.md">CompileWithSystemConstants</a></td><td>
compile script using constant data fields</td></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="a1ffac8d-5933-9616-6d3c-b94f693436a2.md">ConstantEpsilon</a></td><td>
compare epsilon for constants, on fast float mode it wont match on float.epsilon</td></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="8449b4dd-d474-9bae-fd6a-5acc316c6de3.md">ConstantPrecision</a></td><td>
constant precision expressed as a string value</td></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="1e8c2a11-c88c-f915-dba4-cdf34d08b7fb.md">DefaultStackSize</a></td><td>
default stack size in number of bytes - overridden if the script defines a stack size</td></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="925f91a7-ac91-22cc-2e6f-362704ff6ba6.md">Defines</a></td><td>
additional compiler defines</td></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="09d04201-a7dc-e51b-1cbd-a1ca1af5c816.md">EstimateStackSize</a></td><td>
estimate stack size using input, output and validation parameters - overridden if the script defines a stack size</td></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="0a55d786-8e51-5f55-bde1-e0c7522a98e8.md">Experimental</a></td><td>
dont touch if you need to ask</td></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="cfbc3d74-c71c-72f3-9c5b-736bc2046c81.md">Language</a></td><td>
The languageversion to use for the output of the compilation. Packagemode and language version are coupled but there may be deviations: - You can execute BS1 language version files with SSMD package modes if you guarentee that the code doesnt branch (the interpretor wont check this) - You can exectue BS1SSMD compiled packages with the normal interpretor in normal package mode</td></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="635846e5-bbc8-f424-aa2e-0357c5a96d72.md">Optimize</a></td><td>
run code optimizer</td></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="7460bc59-79d9-9dbe-d4bd-c5757dfe721f.md">PackageAllocator</a></td><td>
Allocator for data package</td></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="106ab007-f393-80f3-27f7-3312ecdf055b.md">PackageMode</a></td><td>
the package mode for the output, this determines how code and data is organized in memory</td></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="35da1f59-8899-56ec-1cbf-ebcd2aacfabc.md">PackageStack</a></td><td>
packages include stackdata</td></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="7a037b4a-6b30-7947-22ce-ec651e500ff5.md">ParallelCompilation</a></td><td>
enable for partially parallel compilation [forcebly disabled]</td></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="b6849b94-bf98-6613-6393-e990cc6fdeb5.md">SupportYield</a></td><td>
if yield is not emitted we can save 20 bytes on the stack, with very small stuff that might be handy not implemented .. todo</td></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="892a9af9-35c6-d4f5-cf68-7bf0baa6dd53.md">TraceLogging</a></td><td>
enable trace level logging -> will generate a massive report</td></tr><tr><td>![Public field](media/pubfield.gif "Public field")</td><td><a href="3c27bf23-eea2-4a78-e3bd-b95cf124dfb2.md">VerboseLogging</a></td><td>
verbose report logging, log is also blitted to unity</td></tr></table>&nbsp;
<a href="#blastcompileroptions-class">Back to Top</a>

## See Also


#### Reference
<a href="26a25caa-f50b-92ad-f15c-dbb9db1493ae.md">NSS.Blast.Compiler Namespace</a><br />