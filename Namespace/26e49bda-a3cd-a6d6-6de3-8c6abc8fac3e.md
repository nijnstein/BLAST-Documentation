# BlastPackageData.PackageMode Field
 

Script packaging mode

**Namespace:**&nbsp;<a href="88b55311-4a89-0894-e27a-e157e443c7f7">NSS.Blast</a><br />**Assembly:**&nbsp;BLAST (in BLAST.dll) Version: 1.0.0

## Syntax

**C#**<br />
``` C#
public BlastPackageMode PackageMode
```

**VB**<br />
``` VB
Public PackageMode As BlastPackageMode
```

**C++**<br />
``` C++
public:
BlastPackageMode PackageMode
```

**F#**<br />
``` F#
val mutable PackageMode: BlastPackageMode
```


#### Field Value
Type: <a href="b20095da-1caa-4284-d39e-afb8ff2da2d0">BlastPackageMode</a>

## Remarks

```
Packaging mode 

NORMAL: 
        [----CODE----|----METADATA----|----DATA----|----STACK----]
                     1                2            3             4  

SSMD:
        [----CODE----|----METADATA----]       [----DATA----|----STACK----]
                     1                2                    3             4

ENTITY:
        [----CODE----]      [----METADATA----]     [----DATA----|----STACK----]
                     1                       2                  3             4
```


## See Also


#### Reference
<a href="08d36c75-b5dc-8eaf-5936-daa952653fa2">BlastPackageData Structure</a><br /><a href="88b55311-4a89-0894-e27a-e157e443c7f7">NSS.Blast Namespace</a><br />