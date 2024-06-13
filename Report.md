# Windows x64 Assembly

Honestly was more like a revision of the Assembly Crash course from pwn college but did learn few new things like the calling conventions and  floating point parameters from **xmm0** - **xmm3**. The flow of control in some examples might have cleared some doubts I had.

# Windows Reversing Intro

The first section does a basic IDA overview, function prologue and epilogue. Then we use the **HelloWorld.exe** file to take a look at function calling using `printf()` and `std::cout` and finish off with function inlining. The loop analysis section was pretty straight forward.

Then we learn about the two types of structures **arrays** and **classes** for golding multiple pieces of data

Well most importantly I wanted to learn the DLL'S section. It was a fair good intro to mangling function names and we'd be following the Microsoft C++ and mangling scheme in the further rooms. 

[Microsoft C++ Mangling Scheme:](http://mearie.org/documents/mscmangle/) 
[More Mangling Schemes:](https://en.wikipedia.org/wiki/Name_mangling)


# PE Headers 

Here we learn how to read and understand different PE Headers. **pe-tree** makes the work easier.
A PE file is a Common Object File Format (COFF) data structure. The COFF consists of Windows PE files, DLLs, shared objects in Linux, and ELF files.

## IMAGE_DOS_HEADER
The IMAGE_DOS_HEADER consists of the first 64 bytes of the PE file and the first two bytes say `**4D 5A**` which translate to **MZ** and shows up as **0x5a4d** on pe-tree which is the reversed byte order of `**4D 5A**` due to endianess.
### DOS_STUB
**!This program cannot be run in DOS mode**
## IMAGE_NT_HEADERS
  Has the most vital information about the PE. 

The **SIGNATURE** represent the hex bytes for PE as **50 45 00 00**.
The **FILE_HEADER** contains the crucial information such as the machine architecture, time of binary compilation, number of sections and size of optional header.

## OPTIONAL_HEADER
 Also a part of NT_HEADER

 - **Magic:** The Magic number tells whether the PE file is a 32-bit or 64-bit application.
 - **AddressOfEntryPoint:** - This is the address from where Windows will begin execution or the address of first instruction to be executed
 - **BaseOfCode and BaseOfData:** These are the addresses of the code and data sections, respectively, relative to ImageBase.
 - **ImageBase:** The ImageBase is the preferred loading address of the PE file in memory. Generally it's **0x00400000**
 - **Subsystem:** This represents the Subsystem required to run the image.
 - **DataDirectory:** This information is handy as it gives a glimpse of what the PE file might be trying to do.

 ## IMAGE_SECTION_HEADER

 - **.text:** The section that contains executable code for the application.
 - **.data:** Contains initialized data of the application. It has READ/WRITE permissions but doesn't have EXECUTE permissions.
 - **.rdata/.idata**  Contains import information
 - **.ndata:** - Contains unitialized data 
 - **.reloc:** This section contains relocation information of the PE file.
 - **.rsrc:** The resource section contains icons, images, or other resources required for the application UI.

 ## IMAGE_IMPORT_DESCRIPTOR
The IMAGE_IMPORT_DESCRIPTOR structure contains information about the different Windows APIs that the PE file loads when executed. This information is handy in identifying the potential activity that a PE file might perform. For example, if a PE file imports CreateFile API, it indicates that it might create a file when executed.

[Header Documentation](https://learn.microsoft.com/en-us/windows/win32/api/winnt/ns-winnt-image_nt_headers32)
