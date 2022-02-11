# BlastParser Class
 

The Parser: - Parses list of tokens into a tree of nodes representing the flow of operations - Identifies unique parameters - Spaghetti warning - handcrafted parser ahead..


## Inheritance Hierarchy
<a href="https://docs.microsoft.com/dotnet/api/system.object" target="_blank" rel="noopener noreferrer">System.Object</a><br />&nbsp;&nbsp;NSS.Blast.Compiler.Stage.BlastParser<br />
**Namespace:**&nbsp;<a href="f44e629d-16ad-ce78-c6d1-bb239589698b">NSS.Blast.Compiler.Stage</a><br />**Assembly:**&nbsp;BLAST (in BLAST.dll) Version: 1.0.0

## Syntax

**C#**<br />
``` C#
public class BlastParser : IBlastCompilerStage
```

**VB**<br />
``` VB
Public Class BlastParser
	Implements IBlastCompilerStage
```

**C++**<br />
``` C++
public ref class BlastParser : IBlastCompilerStage
```

**F#**<br />
``` F#
type BlastParser =  
    class
        interface IBlastCompilerStage
    end
```

The BlastParser type exposes the following members.


## Constructors
&nbsp;<table><tr><th></th><th>Name</th><th>Description</th></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="79ac5b21-1640-61f3-b7a4-f02c092de7f4">BlastParser</a></td><td>
Initializes a new instance of the BlastParser class</td></tr></table>&nbsp;
<a href="#blastparser-class">Back to Top</a>

## Properties
&nbsp;<table><tr><th></th><th>Name</th><th>Description</th></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="48218ca0-8757-1215-4cb7-2414cbd0b56f">StageType</a></td><td>
parsing stage: transforms token list into a node tree</td></tr><tr><td>![Public property](media/pubproperty.gif "Public property")</td><td><a href="83d73261-dfdc-0868-a71c-6322f72012bb">Version</a></td><td>
version 0.2.1</td></tr></table>&nbsp;
<a href="#blastparser-class">Back to Top</a>

## Methods
&nbsp;<table><tr><th></th><th>Name</th><th>Description</th></tr><tr><td>![Public method](media/pubmethod.gif "Public method")</td><td><a href="9c9c871b-6c86-80cf-f7a1-9f50d9bf450f">Execute</a></td><td>
execute the parser stage: - parse tokens into node tree - map identifiers (indexers, functions, constants)</td></tr></table>&nbsp;
<a href="#blastparser-class">Back to Top</a>

## See Also


#### Reference
<a href="f44e629d-16ad-ce78-c6d1-bb239589698b">NSS.Blast.Compiler.Stage Namespace</a><br />