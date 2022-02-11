# BlastScript.GetVariableOffset Method (String, Boolean)
 

get variable offset into datasegment

**Namespace:**&nbsp;<a href="88b55311-4a89-0894-e27a-e157e443c7f7.md">NSS.Blast</a><br />**Assembly:**&nbsp;BLAST (in BLAST.dll) Version: 1.0.0

## Syntax

**C#**<br />
``` C#
public int GetVariableOffset(
	string variable_name,
	bool assert_on_fail = true
)
```

**VB**<br />
``` VB
Public Function GetVariableOffset ( 
	variable_name As String,
	Optional assert_on_fail As Boolean = true
) As Integer
```

**C++**<br />
``` C++
public:
int GetVariableOffset(
	String^ variable_name, 
	bool assert_on_fail = true
)
```

**F#**<br />
``` F#
member GetVariableOffset : 
        variable_name : string * 
        ?assert_on_fail : bool 
(* Defaults:
        let _assert_on_fail = defaultArg assert_on_fail true
*)
-> int 

```


#### Parameters
&nbsp;<dl><dt>variable_name</dt><dd>Type: <a href="https://docs.microsoft.com/dotnet/api/system.string" target="_blank" rel="noopener noreferrer">System.String</a><br />\[Missing <param name="variable_name"/> documentation for "M:NSS.Blast.BlastScript.GetVariableOffset(System.String,System.Boolean)"\]</dd><dt>assert_on_fail (Optional)</dt><dd>Type: <a href="https://docs.microsoft.com/dotnet/api/system.boolean" target="_blank" rel="noopener noreferrer">System.Boolean</a><br />assert on failure to locate variable, default = true</dd></dl>

#### Return Value
Type: <a href="https://docs.microsoft.com/dotnet/api/system.int32" target="_blank" rel="noopener noreferrer">Int32</a><br />the variable offset or -1 if not found

## See Also


#### Reference
<a href="701ebde6-515e-1fd5-a11a-526716112a12.md">BlastScript Class</a><br /><a href="a72bef2a-7370-f7ec-c765-552bc271d693.md">GetVariableOffset Overload</a><br /><a href="88b55311-4a89-0894-e27a-e157e443c7f7.md">NSS.Blast Namespace</a><br />