# node.CreatePushNode Method 
 

create a push node with the information from the given node, THIS DOES NOT ADD THAT NODE AS CHILD

**Namespace:**&nbsp;<a href="26a25caa-f50b-92ad-f15c-dbb9db1493ae.md">NSS.Blast.Compiler</a><br />**Assembly:**&nbsp;BLAST (in BLAST.dll) Version: 1.0.0

## Syntax

**C#**<br />
``` C#
public static node CreatePushNode(
	BlastEngineDataPtr blast,
	node topush
)
```

**VB**<br />
``` VB
Public Shared Function CreatePushNode ( 
	blast As BlastEngineDataPtr,
	topush As node
) As node
```

**C++**<br />
``` C++
public:
static node^ CreatePushNode(
	BlastEngineDataPtr blast, 
	node^ topush
)
```

**F#**<br />
``` F#
static member CreatePushNode : 
        blast : BlastEngineDataPtr * 
        topush : node -> node 

```


#### Parameters
&nbsp;<dl><dt>blast</dt><dd>Type: <a href="8db5e405-878e-4a0b-b105-f09f3c478935.md">NSS.Blast.BlastEngineDataPtr</a><br />blast engine data</dd><dt>topush</dt><dd>Type: <a href="7dc9b7e9-64ad-f224-ae1a-4e6639739f56.md">NSS.Blast.Compiler.node</a><br />node to push</dd></dl>

#### Return Value
Type: <a href="7dc9b7e9-64ad-f224-ae1a-4e6639739f56.md">node</a><br />returns the pushing node

## See Also


#### Reference
<a href="7dc9b7e9-64ad-f224-ae1a-4e6639739f56.md">node Class</a><br /><a href="26a25caa-f50b-92ad-f15c-dbb9db1493ae.md">NSS.Blast.Compiler Namespace</a><br />