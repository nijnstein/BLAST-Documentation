# NSS.Blast.Compiler Namespace
 

\[Missing <summary> documentation for "N:NSS.Blast.Compiler"\]


## Classes
&nbsp;<table><tr><th></th><th>Class</th><th>Description</th></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="20a7b82b-c1ca-32fd-17a7-d5eb376d77ee">BlastCompiler</a></td><td>
Blast Compiler Compile scripts into bytecode, the process consists of several stages: For bytecode these stages might be executed: 1 - tokenize: convert code into a list of tokens 2 - parse: parse list of tokens into a tree of nodes 2.1 - variable mapping map all identifiers 3 - transform: transform nodes sequences 4.1 - analyse parameters: determine parameter types and check inputs and outputs 4.2 - analyse: analyse nodes, reorder were needed, optimize for execution 5 - flatten: flatten execution path 6 - node optimizer: optimize nodes 7 - compile: generate bytecode from the internal representation 8 - optimize bytecode: optimize bytecode patterns 9 - package: package bytecode and set it up for execution</td></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="acd2f6cc-9dc8-39b3-7ff6-2a1a35ecce47">BlastCompilerOptions</a></td><td>
Options for compiling and packaging scripts</td></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="3fbdacdd-dea0-1dcb-3082-313eb48e07f8">BlastScriptInlineFunction</a></td><td>
an inlined script function definition</td></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="52667f7e-8dc6-6543-e265-fdc90d6834fa">CompilationData</a></td><td>
Data created during compilation and used for analysis, packaging and debugging/display purposes</td></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="e67b54fe-fb86-7ae8-d46e-8efaf40ec157">CompilationData.Message</a></td><td>
a compiler message</td></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="0c6307ba-1f61-647f-cfa4-6d7284dd5ec8">CSCompilationData</a></td><td>
compiler data for the C# compiler - as it uses the output from hpc we base data on its data</td></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="e2aa1efe-4cdd-2d87-8a39-632f946b078a">CSNamespace</a></td><td /></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="383f9bef-dc6b-ffde-7f1e-9c11fe9a9708">HPCCompilationData</a></td><td>
compiler data for the hpc compiler</td></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="38a875bf-70f0-e536-aa61-8946763a62fb">HPCNamespace</a></td><td /></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="00052b74-5ebe-2692-51cf-37db37010dd0">IMJumpLabel</a></td><td>
a jump label, for help keeping track of jump targets</td></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="7dc9b7e9-64ad-f224-ae1a-4e6639739f56">node</a></td><td>
an ast node used by the blast compiler</td></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="c366c26d-606f-fda5-9bab-5302c240799a">NodeListCache</a></td><td>
a node list cache, trashes the gc a little less using this, only caches small lists, 1 for each thread using this</td></tr><tr><td>![Public class](media/pubclass.gif "Public class")</td><td><a href="eac29d29-e73a-f80b-4118-bd5cd3dda230">NodeListExtensions</a></td><td>
provide some extensions on list, using list as stack we hit the cache more</td></tr></table>

## Structures
&nbsp;<table><tr><th></th><th>Structure</th><th>Description</th></tr><tr><td>![Public structure](media/pubstructure.gif "Public structure")</td><td><a href="32900304-967e-b7b4-7743-8a10dd78931b">BlastIntermediate</a></td><td>
intermediate bytecode data for use by compiler</td></tr></table>

## Interfaces
&nbsp;<table><tr><th></th><th>Interface</th><th>Description</th></tr><tr><td>![Public interface](media/pubinterface.gif "Public interface")</td><td><a href="d2afd70e-15cd-df6e-c1b9-6e1d3e9552bd">IBlastCompilationData</a></td><td>
interface into compilationdata, we should restrict outside use a bit via this</td></tr></table>

## Enumerations
&nbsp;<table><tr><th></th><th>Enumeration</th><th>Description</th></tr><tr><td>![Public enumeration](media/pubenumeration.gif "Public enumeration")</td><td><a href="ffd5cdd4-40dc-84d1-747d-40e06a699332">CompilationData.Message.MessageType</a></td><td /></tr><tr><td>![Public enumeration](media/pubenumeration.gif "Public enumeration")</td><td><a href="e28d8f32-0117-cb7b-5d31-0a3d9a5d6817">nodetype</a></td><td>
the different nodetypes used in the ast</td></tr></table>&nbsp;
