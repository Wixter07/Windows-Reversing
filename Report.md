# Windows x64 Assembly

Honestly was more like a revision of the Assembly Crash course from pwn college but did learn few new things like the calling conventions and  floating point parameters from **xmm0** - **xmm3**. The flow of control in some examples might have cleared some doubts I had.

# Windows Reversing Intro

The first section does a basic IDA overview, function prologue and epilogue. Then we use the **HelloWorld.exe** file to take a look at function calling using `printf()` and `std::cout` and finish off with function inlining. The loop analysis section was pretty straight forward.

Then we learn about the two types of structures **arrays** and **classes** for golding multiple pieces of data

Well most importantly I wanted to learn the DLL'S section. It was a fair good intro to mangling function names and we'd be following the Microsoft C++ and mangling scheme in the further rooms. 

[Microsoft C++ Mangling Scheme:](http://mearie.org/documents/mscmangle/) 
[More Mangling Schemes:](https://en.wikipedia.org/wiki/Name_mangling)
