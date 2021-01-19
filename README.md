# W1Nd0wS💀BADstrings
A collection of Evil String for Windows that causes various type of crash, bsod, filesystem corruption, etc.

<img src="https://raw.githubusercontent.com/JonnyBanana/W1Nd0wS_BADstrings/main/img/bad.jpg" alt="" data-canonical-src="https://raw.githubusercontent.com/JonnyBanana/W1Nd0wS_BADstrings/main/img/bad.jpg" width="250" height="250" />


<h2>C:\$MFT\123</h2>

- Compatibility: Vista, 7, 8, 8.1
- Cause: Slow, and crash the system.
- How it works: Windows uses “$MFT” for special metadata files that are used by NTFS file system, and Windows fail to handle this directory name correctly.
- How to reproduce the bug: There are several ways to exploit the exploit, you can simply call it from the windows searchbar, from cmd or powershell, and also from an html page (tested with windows explorer, but I think it works with all browsers) by calling a file in folder C:\$MFT\123.


More Infos:
https://www.theverge.com/2017/5/26/15696704/microsoft-windows-7-windows-8-pc-crash-bug-ntfs

Full Explanation with P0C:
https://habr.com/en/company/aladdinrd/blog/329166/

Video:
https://www.youtube.com/watch?v=vYL9UQRwUZc&ab_channel=HowToHack

RubberDucky Script that Reproduce the Bug:
https://github.com/JonnyBanana/-MFT-Duck-Crasher


<h2>C:\con\con, C:\Aux\Aux\, C:\nul\nul  </h2>

- Compatibility: 95, 98
- Cause: BSOD.
- How it works: In DOS there are names called "Reserved Names", if you rename a file or folder or if it is called from the terminal or code the system crashes, this happens because in NT systems the DOS is not a real O.S. but is often referred to as "DOS box", it's not really DOS, but a command line interpreter (CLI).
- How to reproduce the bug: WIN+R,put the string, and run! Or you can trying to load an image from file:///c:/con/con from a webpage, or from cmd/bat file.
- Additional Infos: This bug affect also renaming of files. If for example you rename a file,  Microsoft have make a list with the "reserved Names": 
CON, PRN, AUX, NUL, COM1, COM2, COM3, COM4, COM5, COM6, COM7, COM8, COM9, LPT1, LPT2, LPT3, LPT4, LPT5, LPT6, LPT7, LPT8, and LPT9.
If you try a rename the file with one of this reserved name you will see this:

<BR>
  

![Alt text](https://raw.githubusercontent.com/JonnyBanana/W1Nd0wS_BADstrings/main/img/nope.png "W1Nd0wS_BADstrings")


<BR>
  
But You can Create this folder(Very Unstable) with this command in cmd: 

Create Dir:  md \\.\c:\con  

Delete md \\.\c:\con 

Article:
https://thenewstack.io/the-44-year-old-operating-system-bug/

Video:
https://www.youtube.com/watch?v=ACP9qcjwV3I

Naming Files, Paths, and Namespaces (from Microsoft): 
https://docs.microsoft.com/en-us/windows/win32/fileio/naming-a-file

Main Tweet:
https://twitter.com/Foone/status/1058685897829318656


<h2>\\.\globalroot\device\condrv\kernelconnect</h2>

- Compatibility: 10
- Cause: BSOD.
- How it works: When Windows try to connecting to this device (\\.\globalroot\device\condrv\kernelconnect), developers are expected to pass along the 'attach' extended attribute to communicate with the device properly.If you try to connect to the path without passing the attribute due to improper error checking, it will cause an exception that causes a Blue Screen of Death
- How to reproduce the bug: There are several ways to reproduce the bug, you can create a shorctut (.lnk) that leads to the path, you can make a .url file, you can recall it from a web page, but simply type it and send it from the browser, and to some users they say just type it on google and hit enter to reproduce the bug. I strongly believe it also works from CMD/Powershell/Code.

Article: https://www.bleepingcomputer.com/news/security/windows-10-bug-crashes-your-pc-when-you-access-this-location/

Article:https://borncity.com/win/2021/01/18/windows-10-bug-allows-bsod-by-entering-a-path-in-a-browser/

The Bug on Browser:https://docs.microsoft.com/en-us/answers/questions/235907/windows-crash-when-navigate-39globalrootdevicecond.html

Video: https://www.youtube.com/watch?v=8OuW9mykeds


<h2>C:\:$i30:$bitmap</h2>

<p style="color:red;">DANGER!!!! USE ONLY IN VB!!!<p>

DONT COPY THIS STRING ON YOUR MAIN PC!!! 

EVEN ONLY COPYING AND PASTEING THE STRING IS REALLY DANGEROUS!!!!!

YOU SERIOUSLY RISK OF COMPROMISING YOUR FILESYSTEM AND LOSING ALL THE DATA ON THE DISK!!!

- Compatibility: 10
- Cause: Drive/NTFS Corruption, Crash and Restart the system.
- How it works:
- How to reproduce the bug: I REPEAT, USE THIS STRING ONLY IN VIRTUAL BOX OR IN A TARGET MACHINE!!! That are several ways to reproce this bug,

Article: https://www.bleepingcomputer.com/news/security/windows-10-bug-corrupts-your-hard-drive-on-seeing-this-files-icon/


