# IBlastCompilationData Interface
 

interface into compilationdata, we should restrict outside use a bit via this

**Namespace:**&nbsp;<a href="26a25caa-f50b-92ad-f15c-dbb9db1493ae">NSS.Blast.Compiler</a><br />**Assembly:**&nbsp;BLAST (in BLAST.dll) Version: 1.0.0

## Syntax

**C#**<br />
``` C#
public interface IBlastCompilationData
```

**VB**<br />
``` VB
Public Interface IBlastCompilationData
```

**C++**<br />
``` C++
public interface class IBlastCompilationData
```

**F#**<br />
``` F#
type IBlastCompilationData =  interface end
```

The IBlastCompilationData type exposes the following members.


## Properties
&nbsp;<table><tr><th></th><th>Name</th><th>Description</th></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="227e1f3c-6d9a-bc49-2ba6-f385ae5708a1">AST</a></td><td>
Compiler node tree</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="4d98a18d-863e-8aed-f757-5fe2e72e2874">Blast</a></td><td>
blast engine data used in this compilation</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="89bfa349-9528-d7dd-a971-a0e75b3296f5">CanValidate</a></td><td>
true if the script can be validated (it contains validation defines)</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="6d21a9c2-8d0b-8c2c-4be5-4e84565cace6">CompilerOptions</a></td><td>
Compiler Options used during compilation</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="520411af-07e0-bc9d-3372-ae014429f6b6">Defines</a></td><td>
Compiler defines used during compilation, this contains only the unique defines set by this script and more defines might apply depending on the setup</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="7e4b34b2-f833-c416-ab1d-d7c2822b939b">HasDefines</a></td><td>
true if the script defines compiler defines</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="040c4f80-0304-f0d4-6ee6-6e2d5b61e048">HasErrors</a></td><td>
true if an errorcode is set or errors are present in the compilation log</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="29399aaa-75bd-4500-1a8c-72ebe186666a">HasInlinedFunctions</a></td><td>
true if the script has functions inlined</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="2c082c51-04e3-80e3-b47f-6c989ebdaf5f">HasInputs</a></td><td>
true if the script defines inputs</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="4188c5be-317a-2520-fb4c-35de810a0e13">HasOffsets</a></td><td>
true if the script defines variables</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="8fbd00e2-3a79-6d76-06e9-fa1fe00fdcd0">HasOutputs</a></td><td>
true if the script defines outputs</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="40dddbd5-ed7c-ca09-75af-1ec7fa74d500">HasVariables</a></td><td>
true if the script defines variables</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="1a09a144-3c33-1ab4-5bae-9470e88dc727">Inputs</a></td><td>
Defined Inputs</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="0c4a197a-d73f-22a0-103d-1b6133ac9984">IsOK</a></td><td>
true if no errors are set in the compilation log and no errorcode is set</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="2c087802-03ba-7d73-6c8e-790fecb04bfd">Jumps</a></td><td>
Jumps found in the script</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="f0aac5f7-854a-69f3-52a5-1646ca43c64b">OffsetCount</a></td><td>
number of variable offsets defined in the script</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="0d1e3f8f-eee4-2e5f-0cf2-65d2eaa4daad">Offsets</a></td><td>
Offsets into the datasegment for variable indices</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="f3389f99-82a4-92c9-a88d-face4cedc760">Outputs</a></td><td>
Defined Outputs</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="39763fb6-d55e-f5f7-af50-4325cd74d6c6">Script</a></td><td>
the script</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="f375372b-8bd0-9151-cdad-c432cebb6196">Tokens</a></td><td>
List of tokens as parsed from the input</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="5251bd00-affd-395c-fd4f-542ff13bd1a2">Validations</a></td><td>
Validations defined in script</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="44193f79-2cfa-e81a-6ba7-eaafb02a5b5e">VariableCount</a></td><td>
number of variables defined in the script</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="32e69740-f608-843a-9795-39a0a86d53c7">Variables</a></td><td>
List of variables as found in input</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="627df2bc-4c63-2d40-7214-d8e4bbf44eba">Version</a></td><td>
compiler version</td></tr></table>&nbsp;
<a href="#iblastcompilationdata-interface">Back to Top</a>

## Methods
&nbsp;<table><tr><th></th><th>Name</th><th>Description</th></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="4af0c3de-c1b9-48e0-2d5d-077591b5d946">ExistsInlineFunction</a></td><td>
checks if an inlined function with the given name|identifier exists</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="e6b915e2-bafd-1b3a-bd25-529e71109173">ExistsVariable</a></td><td>
returns true if a variable exists with the given name</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="a0fa6b0c-936f-823c-e67c-2bc03610dec1">GetVariable</a></td><td>
lookup a variablemapping defined by the script by its name</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="176cd64b-579d-fed4-7636-20b48a0d107a">GetVariableFromOffset</a></td><td>
lookup a variable defined by script based on its offset</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="b02ca5ec-8579-dd54-dbf0-acb2764d1b47">HasInput(Int32)</a></td><td>
check if there is an input defined by the script with the given id</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="1926e32b-32d3-dc70-2737-ff0b73aaf30b">HasInput(String)</a></td><td>
check if there is an input defined by the script with the given id</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="838a53c7-8f40-f732-e76e-7507c92fcd92">LogError</a></td><td>
log an error to the compiler log</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="25c0cea0-9b9e-5f3d-5851-df4112e99268">LogToDo</a></td><td>
log a message to the compiler log</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="38edf714-b30a-43b9-499d-62e231013d0d">LogTrace</a></td><td>
trace information, does nothing in release</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="9ff35f99-4dfd-78fc-a64d-c08c96c4d3e1">LogWarning</a></td><td>
log a warning to the compiler log</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="5573864b-dceb-0cd1-0052-d5f91a2b356c">TryGetDefine</a></td><td>
attempt to get a defined value from script defined compilerdefines</td></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="16abb53e-f687-82d2-0c83-4b9dfc3c0f84">TryGetInlinedFunction</a></td><td /></tr></table>&nbsp;
<a href="#iblastcompilationdata-interface">Back to Top</a>

## See Also


#### Reference
<a href="26a25caa-f50b-92ad-f15c-dbb9db1493ae">NSS.Blast.Compiler Namespace</a><br />