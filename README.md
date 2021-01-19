# W1Nd0wS_BADstrings
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


<h2>C:/con/con - </h2>

- Compatibility: 95, 98.
- Cause: BSOD.
- How it works:
- How to reproduce the bug: WIN+R,put the string, and run! Or you can trying to load an image from file:///c:/con/con from a webpage.
- Additional Infos: This bug affect also files. If for example you rename a file,  Microsoft have make a list with the "reserved Names": 
CON, PRN, AUX, NUL, COM1, COM2, COM3, COM4, COM5, COM6, COM7, COM8, COM9, LPT1, LPT2, LPT3, LPT4, LPT5, LPT6, LPT7, LPT8, and LPT9.
If you try a rename the file with one of this reserved name you will see this:



Video:
https://www.youtube.com/watch?v=ACP9qcjwV3I


