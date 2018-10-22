# Technical Support

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
     - [Understanding Valgrind Output](#useValgrindOutput)

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

<a name="sue_qa">
##### **But, My Editor Isn't Here...**

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

### Understanding Valgrind Output<a name="useValgrindOutput"></a>

#### The Parts Of A Valgrind Output:

##### HEAP SUMMARY:
>HEAP SUMMARY:  
&nbsp &nbsp &nbsp &nbsp in use at exit: 48 bytes in 3 blocks  
&nbsp &nbsp total heap usage: 4 allocs, 1 frees, 560 bytes allocated  
