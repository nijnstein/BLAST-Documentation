# BlastInterpretor.BlastOperationIsValue Method 
 

return true if op is a value: - pop counts!! - byte value between lowest constant and extended op id (dont allow constants in extended op id's)

**Namespace:**&nbsp;<a href="bc1962ef-fc17-4dde-e64c-a350d8f217aa.md">NSS.Blast.Interpretor</a><br />**Assembly:**&nbsp;BLAST (in BLAST.dll) Version: 1.0.0

## Syntax

**C#**<br />
``` C#
public static bool BlastOperationIsValue(
	 in byte op
)
```

**VB**<br />
``` VB
Public Shared Function BlastOperationIsValue ( 
	 ByRef op As Byte
) As Boolean
```

**C++**<br />
``` C++
public:
static bool BlastOperationIsValue(
	[InAttribute]  unsigned char% op
)
```

**F#**<br />
``` F#
static member BlastOperationIsValue : 
         op : byte byref -> bool 

```


#### Parameters
&nbsp;<dl><dt>op</dt><dd>Type: <a href="https://docs.microsoft.com/dotnet/api/system.byte" target="_blank" rel="noopener noreferrer">System.Byte</a><br />\[Missing <param name="op"/> documentation for "M:NSS.Blast.Interpretor.BlastInterpretor.BlastOperationIsValue(System.Byte@)"\]</dd></dl>

#### Return Value
Type: <a href="https://docs.microsoft.com/dotnet/api/system.boolean" target="_blank" rel="noopener noreferrer">Boolean</a><br />\[Missing <returns> documentation for "M:NSS.Blast.Interpretor.BlastInterpretor.BlastOperationIsValue(System.Byte@)"\]

## See Also


#### Reference
<a href="4de5bd5a-f1bd-8188-7356-ab8a45b847d4.md">BlastInterpretor Structure</a><br /><a href="bc1962ef-fc17-4dde-e64c-a350d8f217aa.md">NSS.Blast.Interpretor Namespace</a><br />