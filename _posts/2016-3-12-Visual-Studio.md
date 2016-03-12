---
layout: post
title: Things you never know debuuging in Visual Studio
---

So what happen in a debugger when you set a breakpoint and press F5? 

We have two processor that matters, visual studio and the debugger. The debugger is going to communicate with some target process. In the target process for example we have a foo.exe mapped from address space 10000 to 20000.

So we have some source file in Visual Studio, foo.cpp. So the user presses F9 on line 12. So before we can do all these, we need to load the symbols from foo.exe. How this works is that as the target process as some point, the operating system decides to map foo.exe to this address space 10000 to 20000. And at that point the debugger would have gotten the notification that happend, and this happens before any code could run through the exe. We would temporary pause that process, and we would go off and try to load the symbols. 

So what are symbols?
Symbol is .PDB file which is created by the linker. 

What is inside a pdb file?
A program database (.pdb) file, also called a symbol file, maps the identifiers that you create in source files for classes, methods and oher code to the identifiers hat are used in the compiled executavles of your project. The .pdb file also maps the statements in the source code to the identifiers that are ised in the compiled execitables of your project. 

The .pdb file also maps statements in the source code to the execution instructions in the executables. The debugger uses this information to determine two key pieces of information: the source file and line number that are displayed in Visua Studio and the location in the executable to stio at where you set a breakpoint. A symbol files also contains orginal location of the source files, and optionally the location of a source server where the source files can be retrived from. 

It has a table that allows mapping of lines from a particular source file to an address range. 
Bascially a set of lookup tables that you can use to figure out where the compiler put things so you can map the dynamic view to what was back in the source.


So first we look up foo.cpp in the pdb file and we will find an object that represent that, we will query to see what source line that they are called, in this case line 12. So we will find one and that will tell us foo.exe relative virtual address i where that source line is. And at that point all we have to do is we have to update the instruction stream of that function where foo.cpp line 12 was so that instead of having the real original instruction that would be execute, now it has a breakpoint instruction. 

What is a breakpoint instruction?
It is a special instruction and one of the charactherisc of it is that it has to have of size equal to or less than smallest instruction. 


