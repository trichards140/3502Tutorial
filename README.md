<a name="top"></a>
# Installing GCC and Valgrind

 - [Software And Compiler Setup](#setupMain)
   - [Setting Up Your Editing Environment](#settingUpEnv)
     - [Recommended Text Editors](#sue_rec)
     - [Honorable Mentions](#sue_hon)
     - [Common Questions](#sue_qa)
   - [Setting Up GCC](#gccMain)
     - [Installing GCC On Linux](#gccLinux)
     - [Installing GCC On Windows](#gccWin)
   - [Setting Up Valgrind](#vgMain)
     - [Installing Valgrind On Linux](#vgLinux)
     - [Installing Valgrind On Windows](#vgWin)
   - [Other Software Recommendations](#otherMain)
     - [Get A Good Console](#otherConsole)
       - [Consoles For Windows](#otherConsoleWindows)
 - [Using GCC And Valgrind](#useMain)
   - [General Use Instructions](#useGeneral)
     - [Compile With GCC](#useCompile)
     - [Memory Test With Valgrind](#useValgrind)
     - [Basic Valgrind Output](#useValgrindOutput)
   - [Advanced Valgrind Usage](#vgAdvMain)
     - [Debugging Segmentation Faults](#vgAdvLinking)
     - [Pinpointing Memory Leaks](#vgAdvLocating)
 - [Using Input and Output Files](#ioMain)

## Software And Compiler Setup <a name="setupMain"></a>

### Setting Up Your Editing Environment <a name="settingUpEnv"></a>

To setup your coding environment, the first thing you will need is a text editor.

#### **Recommended Text Editors** <a name="sue_rec"></a>
- ###### [Atom](https://atom.io/) - Windows, Linux, Mac
  - Like Sublime, But Free, And Better
- ###### [Notepad++](https://notepad-plus-plus.org/) - Windows
  - Excellent Editor That Proves Looks Aren't Everything, Only For Windows
- ###### [Code::Blocks](http://www.codeblocks.org/) - Windows, Linux, Mac
  - An IDE Style, Free, Open Source Editor
- ###### [Visual Studio Code](https://code.visualstudio.com/) - Windows, Linux, Mac
  - Another IDE Style, Free, Open Source Editor

#### **Honorable Mentions** <a name="sue_hon"></a>

- ###### [Sublime Text Editor](https://www.sublimetext.com/) - Windows, Linux, Mac
  - A Well Respected Choice, But Costs $$$
- ###### [Eclipse](https://www.eclipse.org/) - Windows, Linux, Mac
  - A Good Choice, But Far To Heavy For This Applciation


##### **But, My Editor Isn't Here...** <a name="sue_qa">

- That doesnt mean your editor is bad, it just means that some of the stuff described here might not apply to you.

##### **What About [Insert Editor Here]**

- What about it?

## Setting Up GCC <a name="gccMain"></a>
GCC is a GNU compiler for C, C++, Objective-C, Fortran, Ada, and Go.

### Installing On Linux <a name="gccLinux"></a>

#### Debian Based (Ubuntu and Derivatives)
  >`sudo apt-get install gcc`

  OR

  >`sudo apt install build-essential`

#### Fedora 22+

  >`dnf group install 'Development Tools'`

#### Other

  >`I Have No Idea - CONTRIBUTION APPRECIATED`


##### Now Test To Make Sure It's Working
  - Open a terminal and type in `gcc -v`
  - GCC should announce it's version along with some other info
  - If GCC responded, you're golden.

### Installing On Windows <a name="gccWin"></a>

#### Windows 7 to 10

  The easiest way to install GCC on Windows is to install MinGW, which includes GCC along with a handful of other small utilities.

  [Download The Latest Version of MinGW From Their Website](http://www.mingw.org/)

  When running the installer for MinGW, it will install into the default folder of *C:\MinGW*

  To make GCC work in the command line, we will need to add it to the %PATH% system variable.

  To Add GCC To Your System Path:
  - Press The Windows Key On Your Keyboard
  - Type In 'System Properties'
  - Select The Item Called SystemPropertiesAdvanced.exe
  - [A Window Will Appear](https://i.imgur.com/E6dzGRZ.png), At The Bottom Of This Window, Click The Button That Says *Environmental Variables*
  - A [New Window](https://i.imgur.com/N2IjDOY.png) Will Appear
  - Select 'Path' In The Top Portion Of The Window, Then Click Edit.
  - [Yet Another Window](https://i.imgur.com/NCwJ6en.png) Will Appear
  - If You Don't See An Entry Labeled *C:\MinGW\bin*, Click The Add Button, And Type `C:\MinGW\bin` Into The Input Field That Appeared.
  - Now Test To Make Sure It's Working
    - Open cmd and type in `gcc -v`
    - GCC should announce it's version along with some other info
    - If GCC responded, you're golden.

#### Windows XP

>`Good Luck Brave Soul - CONTRIBUTION APPRECIATED`

## Setting Up GCC <a name="vgMain"></a>

### Installing Valgrind On Linux <a name="vgLinux"></a>

#### Debian Based (Ubuntu and Derivatives)

  >`sudo apt-get install valgrind`

#### Fedora 22+

  >`sudo dnf install valgrind`

#### Other

  >`I Have No Idea - CONTRIBUTION APPRECIATED`


##### Now Test To Make Sure It's Working
  - Open a terminal and type in `valgrind --version`
  - Valgrind should announce it's version
  - If Valgrind responded, you're golden.

### Installing On Windows <a name="vgWin"></a>

#### Windows 10
Valgrind Cannot Be Installed Directly On Windows To The Best Of My Knowledge. That does not mean that valgrind cannot be used though Windows:

Valgrind Can Be Used On Windows Machine Using The New "Linux in a Windows" Method:
- Linux in a Windows (Windows 10 ONLY)
  - [Follow This Guide To Install The Linux Subsystem For Windows](https://docs.microsoft.com/en-us/windows/wsl/install-win10)
  - Now Open The Subsystem Console And Follow The Linux Valgrind and GCC Instructions (When Using The Subsystem Console, You Will Need To Follow Linux Instructions)

#### Windows 7 to 8.1

- VM Method Using VirtualBox
  - With Enough Requests I Will Write A Tutorial For This

## Other Software <a name="otherMain"></a>

### Get A Good Console <a name="otherConsole"></a>
  You will be interacting with the console a lot, so you should have one that you like.
#### Recommended Consoles For Windows<a name="otherConsoleWindows"></a>
- [cmder](http://cmder.net/)
  - Built on [ConEmu](https://conemu.github.io/), offering a facelift and extra functionality.
- [ConEmu](https://conemu.github.io/)
  - Like cmder, but ugly.

## Using GCC and Valgrind <a name="useMain"></a>

### General Use Instructions <a name="useGeneral"></a>

#### Compile With GCC<a name="useCompile"></a>

##### GCC Command Format<a name="useGCCFormat"></a>
Windows: ` gcc .\fileNameToCompile.c -o .\outputNameYouWant.exe`

Linux: ` gcc ./fileNameToCompile.c -o ./outputNameYouWant.out`

**Notes On How These Are Different**
- Linux and Windows Have Different Directory Separator Characters.
  - On Windows we use `\` and on Linux we use `/`
- Linux and Windows Have Different output extensions.
  - On Windows we use `.exe` and on Linux we use `.out`

##### GCC Use On Windows
  - Open a console window
  - Use `cd` to get to where your .c code is [How To Use `cd`](https://ss64.com/nt/cd.html)
  - Run gcc [using the format specified above](#useGCCFormat)
  - then enter `.\outputNameYouGaveToGCCEarlier.exe`, your program should start.

##### GCC Use On Linux (or Linux in A Windows)
- Open a terminal window
- Use `cd` to get to where your .c code is [How To Use `cd`](http://www.linfo.org/cd.html)
- Run gcc [using the format specified above](#useGCCFormat)
- then enter `./outputNameYouGaveToGCCEarlier.out`, your program should start.

#### Memory Test With Valgrind<a name="useValgrind"></a>
Once you have compiled the program with GCC, you can use valgrind to find any memory leaks. (and [much more](#advancedValgrind))

##### Valgrind Command Format<a name="useValgrindFormat"></a>

Windows: `Must Use A VM or Subsystem Running Linux`

Linux: ` valgrind ./outputNameYouGaveToGCCEarlier.out`

### Understanding Basic Valgrind Output<a name="useValgrindOutput"></a>

#### The Parts Of A Valgrind Output:

##### HEAP SUMMARY:
Gives an overview of the program's memory usage during runtime.
>HEAP SUMMARY:  
in use at exit: 48 bytes in 3 blocks  
total heap usage: 4 allocs, 1 frees, 560 bytes allocated  

The Heap Summary Describes Two Parts:
- *in use at exit* - Memory in use when the program exited
- *total heap usage* - Total memory usage during the program run

##### LEAK SUMMARY:
Only appears if the program had a memory leak
>LEAK SUMMARY:  
definitely lost: 0 bytes in 0 blocks  
indirectly lost: 0 bytes in 0 blocks  
possibly lost: 0 bytes in 0 blocks  
still reachable: 48 bytes in 3 blocks  
suppressed: 0 bytes in 0 blocks

The Leak Summary Describes:  
[This List Is From The Offical Valgrind Documentation](http://valgrind.org/docs/manual/faq.html#faq.deflost)

- *definitely lost* means your program is leaking memory -- fix those leaks!

- *indirectly lost* means your program is leaking memory in a pointer-based structure. (E.g. if the root node of a binary tree is *definitely lost*, all the children will be *indirectly lost*.) If you fix the *definitely lost* leaks, the *indirectly lost* leaks should go away.

- *possibly lost* means your program is leaking memory, unless you're doing unusual things with pointers that could cause them to point into the middle of an allocated block.

- *still reachable* means your program is probably ok -- it didn't free some memory it could have. This is quite common.

- *suppressed* means that a leak error has been suppressed. There are some suppressions in the default suppression files. You can ignore suppressed errors.

## Advanced Valgrind Usage <a name="vgAdvMain"></a>

Valgrind is much more than just a basic tool to test for memory leaks.

Valgrind can be used to find Segmentation Faults and Actually Locate Memory Leaks

### Debugging Segfaults (SIGSEGV) (signal 11) With Valgrind <a name="vgAdvLinking"></a>

Valgrind can help find segfaults in your c code, the procedure is simple.

- Compile your source code with the `-g` flag *Example:* `gcc -g ./sourceCode.c -o ./fileName.out`
- Valgrind [as described above](#useValgrindFormat).

##### This procedure links the line numbers during the compile phase. Allowing Valgrind to show the specific line number a failure occurs on.

Here's an example:
```
==13268== Invalid write of size 8
==13268==    at 0x1086A8: thisFunctionDoesCauseAnIssue (valgrindtutorial.c:44)
==13268==    by 0x108625: main (valgrindtutorial.c:21)
==13268==  Address 0x0 is not stack'd, malloc'd or (recently) free'd
```

Suddenly, Valgrind can explain which file, function, and line an error occurred on.

Dissecting This Output:  
```
==13268==    at 0x1086A8: thisFunctionDoesCauseAnIssue (valgrindtutorial.c:44)

==[PID]==    at [Memory Address]: [Function Name] ([Source File Name]:[Line Number])
```

Taking A Look At The Code:

![function blamed by valgrind for segfault](https://i.imgur.com/oIzT7vq.png "Function Dereferences Null On Line 44")

Line 44 is definitely a problem, nSum->contents dereferences NULL.

### Pinpoint Memory Leaks With Valgrind <a name="vgAdvLocating"></a>

Valgrind can also be used to find the source of a memory leak. This is less strait forward than segfault recognition.

Lets Take A Look At A Sample Output:
```
==13422== 708 (16 direct, 692 indirect) bytes in 1 blocks are definitely lost in loss record 7 of 7
==13422==    at 0x4C2FB0F: malloc (in /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so)
==13422==    by 0x108846: createLossyNode (valgrindMemoryLeaks.c:42)
==13422==    by 0x10876B: main (valgrindMemoryLeaks.c:26)
```

To Better Understand This, We Can Break It Down Into Lines:

`1 | ==13422== 708 (16 direct, 692 indirect) bytes in... `  
Line one describes the type and amount of memory loss experienced.  
`2 | ==13422==    at 0x4C2FB0F: malloc (in... `  
Line two describes the memory address and allocation function used to reserve the lost block.  
`3 | ==13422==    by 0x108846: createLossyNode (valgrindMemoryLeaks.c:42) `  
Line three describes the memory address, function, source code file, and line number where the allocation occured.
`4 and Beyond`  
Lines four and beyond are a [stack trace](https://en.wikipedia.org/wiki/Stack_trace).

##### Valgrind Does Not Know HOW The Program Lost The Memory, Only That The Memory Was Lost

Because Valgrind does not know where the memory was lost, it announces the only thing it does know, where the memory was allocated.

This is still useful information. By understanding what was lost, debugging can be narrowed to only follow the relevant data.

## Using Input and Output Files (Redirection) <a name="ioMain"></a>

### Master The < and > Symbols
**<** *is called a left-chevron*  
**>** *is called a right-chevron*

##### **<** Means

`[into this thing] < [read the contents of this file]`

Example:  
Windows: `.\outputNameYouGaveToGCCEarlier.exe < .\inputFile.in`  
Linux: `./outputNameYouGaveToGCCEarlier.out < ./inputFile.in`

##### **>** Means

`[write the output from this] > [into this file] `

Example:  
Windows: `.\outputNameYouGaveToGCCEarlier.exe > .\outputFile.txt`  
Linux: `./outputNameYouGaveToGCCEarlier.out > ./outputFile.txt`

Note:  
The output file will be created if it does not already exist.

##### Using Both

`[Input To This File & Output From This File] < [from this file] > [into this file] `

Example:  
Windows: `.\outputNameYouGaveToGCCEarlier.exe < .\inputFile.in > .\outputFile.txt`  
Linux: `./outputNameYouGaveToGCCEarlier.out < ./inputFile.in > ./outputFile.txt`

That's how it's done. No, seriously, it's that simple.

##### Yes, You Can Use It With Valgrind

This Sort Of Thing Also Works  
`valgrind ./outputNameYouGaveToGCCEarlier.out < ./inputFile.in > ./outputFile.txt`

##### Write Your Own Inputs
- Open a text editor
- Type the input you would normally type into the command line
  - Include the enters and don't worry about the output at all
- Save the file
- You can use that as an input file with the < symbol
