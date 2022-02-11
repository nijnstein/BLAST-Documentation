# BlastScriptAPI.GetFunctionByName Method 
 

lookup a function definition that is directly linked to an interpretor operation

**Namespace:**&nbsp;<a href="88b55311-4a89-0894-e27a-e157e443c7f7">NSS.Blast</a><br />**Assembly:**&nbsp;BLAST (in BLAST.dll) Version: 1.0.0

## Syntax

**C#**<br />
``` C#
public BlastScriptFunctionInfo GetFunctionByName(
	string name
)
```

**VB**<br />
``` VB
Public Function GetFunctionByName ( 
	name As String
) As BlastScriptFunctionInfo
```

**C++**<br />
``` C++
public:
BlastScriptFunctionInfo^ GetFunctionByName(
	String^ name
)
```

**F#**<br />
``` F#
member GetFunctionByName : 
        name : string -> BlastScriptFunctionInfo 

```


#### Parameters
&nbsp;<dl><dt>name</dt><dd>Type: <a href="https://docs.microsoft.com/dotnet/api/system.string" target="_blank" rel="noopener noreferrer">System.String</a><br />the name of the function to lookup</dd></dl>

#### Return Value
Type: <a href="35bc9cb6-da4c-534d-4c2a-2a3eef40d203">BlastScriptFunctionInfo</a><br />a function definition

## See Also


#### Reference
<a href="e6f5a4bb-3337-aec4-3768-690bdad3c62b">BlastScriptAPI Class</a><br /><a href="88b55311-4a89-0894-e27a-e157e443c7f7">NSS.Blast Namespace</a><br />