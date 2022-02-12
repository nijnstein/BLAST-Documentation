<img width="600" alt="BLAST hdr" src="https://user-images.githubusercontent.com/96932314/151460984-1c8f7bc5-be31-4b5f-9921-536c0092fb72.PNG">

## BLAST
[Overview](README.md) - [Language Reference](LanguageReference.md) - [Namespace (doxygen)](Namespace/_Sidebar.md)

# Usage Examples 

Single use: 

```csharp
            Blast.InitInstance();
            BlastScript bs = BlastScript.FromText("result = 1 + value;");
            bs["value"] = 2;

            BlastError res = bs.Execute();

            Xunit.Assert.True(bs["result"] == (object)3f);
            Xunit.Assert.True(res == BlastError.success);
``` 
Repeated Use:

```csharp
            Blast.InitInstance();

            // create a script package from text 
            BlastScript bs = BlastScript.FromText("result = 1 + value;");
          
            // prepare it for execution (compiles script package)
            bs.Prepare();

            // run in a loop, using different inputs 
            BlastError res = BlastError.success;
            for (int i = 0; i < 100000 && res == BlastError.success; i++)
            {
                bs["value"] = i;

                res = bs.Execute();
                if (res == BlastError.success)
                {
                    float result = (float)bs["result"];
                }
            }
```

SSMD | Single Script Multiple Data execution 

usage will simplify

```csharp
            int n = 1024; 
            using (Blast blast = Blast.Create(Allocator.Persistent))
            {
                BlastScript bs = BlastScript.FromText("result = 1 + value;");
                BlastError res = Blast.Package(blast.Engine, bs, BlastCompilerOptions.SSMD.Trace());

                unsafe
                {
                    // allocate datasegments  
                    byte* data = stackalloc byte[bs.Package.Package.SSMDDataSize * n];
                    BlastSSMDDataStack* ssmd_data = (BlastSSMDDataStack*)(void*)data;

                    // clone default data 
                    bs.Package.Package.CloneDataStack(n, ssmd_data); 

                    // set value (                    
                    for(int i = 0; i < n; i++)
                    {
                        ssmd_data[i].a[0] = i; 
                    }

                    // execute script with n * input data
                    res = blast.Execute(bs.Package.Package, IntPtr.Zero, new IntPtr(ssmd_data), n);
                }
            }
``` 
