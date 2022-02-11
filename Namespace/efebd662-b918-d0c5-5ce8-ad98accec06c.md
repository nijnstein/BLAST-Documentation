# BlastScriptPackage.Execute Method 
 

execute the script in the given environment with the supplied data

**Namespace:**&nbsp;<a href="88b55311-4a89-0894-e27a-e157e443c7f7">NSS.Blast</a><br />**Assembly:**&nbsp;BLAST (in BLAST.dll) Version: 1.0.0

## Syntax

**C#**<br />
``` C#
public BlastError Execute(
	IntPtr blast,
	IntPtr environment,
	IntPtr caller,
	bool reset_defaults = true
)
```

**VB**<br />
``` VB
Public Function Execute ( 
	blast As IntPtr,
	environment As IntPtr,
	caller As IntPtr,
	Optional reset_defaults As Boolean = true
) As BlastError
```

**C++**<br />
``` C++
public:
BlastError Execute(
	IntPtr blast, 
	IntPtr environment, 
	IntPtr caller, 
	bool reset_defaults = true
)
```

**F#**<br />
``` F#
member Execute : 
        blast : IntPtr * 
        environment : IntPtr * 
        caller : IntPtr * 
        ?reset_defaults : bool 
(* Defaults:
        let _reset_defaults = defaultArg reset_defaults true
*)
-> BlastError 

```


#### Parameters
&nbsp;<dl><dt>blast</dt><dd>Type: <a href="https://docs.microsoft.com/dotnet/api/system.intptr" target="_blank" rel="noopener noreferrer">System.IntPtr</a><br />blastengine data</dd><dt>environment</dt><dd>Type: <a href="https://docs.microsoft.com/dotnet/api/system.intptr" target="_blank" rel="noopener noreferrer">System.IntPtr</a><br />[optional] pointer to environment data</dd><dt>caller</dt><dd>Type: <a href="https://docs.microsoft.com/dotnet/api/system.intptr" target="_blank" rel="noopener noreferrer">System.IntPtr</a><br />[ooptional] caller data</dd><dt>reset_defaults (Optional)</dt><dd>Type: <a href="https://docs.microsoft.com/dotnet/api/system.boolean" target="_blank" rel="noopener noreferrer">System.Boolean</a><br />rewrite default values in datasegment, can be omitted on first execute with fresh datasegment</dd></dl>

#### Return Value
Type: <a href="db8cb631-f3f7-e809-8853-bc1b825061a7">BlastError</a><br />success if all is ok

## See Also


#### Reference
<a href="334603e0-a0de-2aaa-4007-78f5dcc5dc51">BlastScriptPackage Class</a><br /><a href="88b55311-4a89-0894-e27a-e157e443c7f7">NSS.Blast Namespace</a><br />