# BlastScriptAPI.RegisterFunction Method (String, Int32, Int32, Int32, Int32, extended_blast_operation)
 

Register a function with blast

**Namespace:**&nbsp;<a href="88b55311-4a89-0894-e27a-e157e443c7f7.md">NSS.Blast</a><br />**Assembly:**&nbsp;BLAST (in BLAST.dll) Version: 1.0.0

## Syntax

**C#**<br />
``` C#
public int RegisterFunction(
	string name,
	int min_param_count,
	int max_param_count,
	int accept_vector_size,
	int return_vector_size,
	extended_blast_operation op
)
```

**VB**<br />
``` VB
Public Function RegisterFunction ( 
	name As String,
	min_param_count As Integer,
	max_param_count As Integer,
	accept_vector_size As Integer,
	return_vector_size As Integer,
	op As extended_blast_operation
) As Integer
```

**C++**<br />
``` C++
public:
int RegisterFunction(
	String^ name, 
	int min_param_count, 
	int max_param_count, 
	int accept_vector_size, 
	int return_vector_size, 
	extended_blast_operation op
)
```

**F#**<br />
``` F#
member RegisterFunction : 
        name : string * 
        min_param_count : int * 
        max_param_count : int * 
        accept_vector_size : int * 
        return_vector_size : int * 
        op : extended_blast_operation -> int 

```


#### Parameters
&nbsp;<dl><dt>name</dt><dd>Type: <a href="https://docs.microsoft.com/dotnet/api/system.string" target="_blank" rel="noopener noreferrer">System.String</a><br />functino name</dd><dt>min_param_count</dt><dd>Type: <a href="https://docs.microsoft.com/dotnet/api/system.int32" target="_blank" rel="noopener noreferrer">System.Int32</a><br />minimal parameter count</dd><dt>max_param_count</dt><dd>Type: <a href="https://docs.microsoft.com/dotnet/api/system.int32" target="_blank" rel="noopener noreferrer">System.Int32</a><br />maximum parameter count</dd><dt>accept_vector_size</dt><dd>Type: <a href="https://docs.microsoft.com/dotnet/api/system.int32" target="_blank" rel="noopener noreferrer">System.Int32</a><br />minimal vector size, 0 for any</dd><dt>return_vector_size</dt><dd>Type: <a href="https://docs.microsoft.com/dotnet/api/system.int32" target="_blank" rel="noopener noreferrer">System.Int32</a><br />max verctor size, 0 for any</dd><dt>op</dt><dd>Type: <a href="b2678389-6f1b-6b04-ed6f-6ec5f2b602d7.md">NSS.Blast.extended_blast_operation</a><br />blast operation used to encode it</dd></dl>

#### Return Value
Type: <a href="https://docs.microsoft.com/dotnet/api/system.int32" target="_blank" rel="noopener noreferrer">Int32</a><br />returns a unique (within the blast instance) function id

## See Also


#### Reference
<a href="e6f5a4bb-3337-aec4-3768-690bdad3c62b.md">BlastScriptAPI Class</a><br /><a href="6d3b5541-67f5-c909-a3f9-af407575a2f7.md">RegisterFunction Overload</a><br /><a href="88b55311-4a89-0894-e27a-e157e443c7f7.md">NSS.Blast Namespace</a><br />