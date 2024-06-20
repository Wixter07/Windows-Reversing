# Easy Unpack 
Hmm so the text file says 

> ReversingKr UnpackMe
> 
> Find the OEP
> 
> ex) 00401000

So I read this from somewhere on stack overflow 

**The Original Entry Point is a concept typically referred to in reverse engineering for an executable that has been modified by some means such as being compressed (or encrypted) by a packer or infected with malware. Prior to modification, the entry-point of an executable IS the original entry point (OEP). When an executable has been modified, such as to include a stub of code that runs prior to the original code, the entry-point of the executable is changed to point to the new code. The stub then references the old entry-point when it is done. So once the stub runs, it will transfer control to the address of the original entry point so the modified program still works (or appears) to work as normal.**

And found this tool called PEid. Went through the [Documentation](https://www.aldeid.com/wiki/PEiD) and seems the Generic OEP Finder plugin will help.

![Screenshot 2024-06-20 173621](https://github.com/Wixter07/Windows-Reversing/assets/150792650/8d5641b5-830b-4717-88b2-cc174a6f9bec)

Voila `00401150`
