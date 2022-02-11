<img width="600" alt="BLAST hdr" src="https://user-images.githubusercontent.com/96932314/151460984-1c8f7bc5-be31-4b5f-9921-536c0092fb72.PNG">

## BLAST
[Language Reference](LanguageReference.md)    -	   [Namespace (doxygen)](Namespace/_Sidebar.md)    -     [Examples](examples.md)

# Usage Examples 

Single use: 

```csharp
            using (Blast blast = Blast.Create())
            {
                BlastScript bs = BlastScript.FromText("result = 1 + value;");
                bs["value"] = 2;

                BlastError res = bs.Execute(blast);

                Xunit.Assert.True(bs["result"] == 3);
                Xunit.Assert.True(res == BlastError.success);
            }
``` 
Repeated Use:

'''csharp 
            // somewhere blast has to be initialized, all threads can use this same object
            // it provides functionpointers, constants and other information needed for execution
            Blast blast = Blast.Create(Allocator.Persistant); 
    
            // create a script package from text 
            BlastScript bs = BlastScript.FromText("result = 1 + value;");
            bs.Prepare(blast); 

            // run in a loop, using different inputs 
            BlastError res = BlastError.success; 
            for(int i = 0; i < 100000, res == BlastError.success; i++)
            {
                bs["value"] = i;
                
                res = bs.Execute(blast);                
                if(res == BlastError.success)
                {
                    float result = bs["result"];  
                }
            }
            
            // at the end of the program, cleanup blast 
            blast.Destroy(); 

'''

SSMD | Single Script Multiple Data execution 

usage will simplify

```csharp
    
            using(Blast blast = Blast.Create(Allocator.Persistent))
            {
                BlastScriptPackage package = blast.Package(code, BlastCompilerOptions.SSMD.Trace());

                byte* data = stackalloc byte[package.Package.SSMDDataSize * n];

                BlastSSMDDataStack* ssmd_data = (BlastSSMDDataStack*)(void*)data;
                package.Package.CloneDataStack(n, ssmd_data);

                // execute script wioth n * input data
                blast.Execute(package.Package, IntPtr.Zero, new IntPtr(ssmd_data), n);
            }

``` 



