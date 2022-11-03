# W1Nd0wS💀BADstrings
A collection of Evil String for Windows that causes various type of crash, bsod, filesystem corruption, etc.

<img src="https://raw.githubusercontent.com/JonnyBanana/W1Nd0wS_BADstrings/main/img/bad.jpg" alt="" data-canonical-src="https://raw.githubusercontent.com/JonnyBanana/W1Nd0wS_BADstrings/main/img/bad.jpg" width="250" height="250" />

<h2>C:\$MFT\123</h2>

- <b>Compatibility:</b> Vista, 7, 8, 8.1
- <b>Cause:</b> Slow, and crash the system.
- <b>How it works:</b> Windows uses “$MFT” for special metadata files that are used by NTFS file system, and Windows fail to handle this directory name correctly.
- <b>How to reproduce the bug:</b> There are several ways to exploit this bug, you can simply call it from the windows searchbar, from cmd or powershell, and also from an html page (tested with windows explorer, but I think it works with all browsers) by calling a file in folder C:\$MFT\123.


More Infos:
https://www.theverge.com/2017/5/26/15696704/microsoft-windows-7-windows-8-pc-crash-bug-ntfs

Full Explanation with P0C:
https://habr.com/en/company/aladdinrd/blog/329166/

Video:
https://www.youtube.com/watch?v=vYL9UQRwUZc&ab_channel=HowToHack

RubberDucky Script that Reproduce the Bug:
https://github.com/JonnyBanana/-MFT-Duck-Crasher

</BR>

<h2>C:\con\con, C:\Aux\Aux\, C:\nul\nul  </h2>

- <b>Compatibility:</b> 95, 98
- <b>Cause:</b> BSOD.
- <b>How it works:</b> In DOS there are names called "Reserved Names", if you rename a file or folder or if it is called from the terminal or code the system crashes, this happens because in NT systems the DOS is not a real O.S. but is often referred to as "DOS box", it's not really DOS, but a command line interpreter (CLI).
- <b>How to reproduce the bug:</b> WIN+R, put the string, and run! Or you can try to load an image from file:///c:/con/con from a webpage, or from cmd/bat file.
- <b>Additional Infos:</b> This bug affect also renaming of files. Microsoft have make a list with the "reserved Names": 
CON, PRN, AUX, NUL, COM1, COM2, COM3, COM4, COM5, COM6, COM7, COM8, COM9, LPT1, LPT2, LPT3, LPT4, LPT5, LPT6, LPT7, LPT8, and LPT9.
If you try a rename the file with one of this reserved name you will see this:

<BR>
  

![Alt text](https://raw.githubusercontent.com/JonnyBanana/W1Nd0wS_BADstrings/main/img/nope.png "W1Nd0wS_BADstrings")


<BR>
  
But You can Create this folder (Very Unstable) with this command in cmd: 

```

Create Dir:  md \\.\c:\con    (Create a "con" directory in C:\)

Delete Dir:  rd \\.\c:\con  

```

Article:
https://thenewstack.io/the-44-year-old-operating-system-bug/

Video:
https://www.youtube.com/watch?v=ACP9qcjwV3I

Naming Files, Paths, and Namespaces (from Microsoft): 
https://docs.microsoft.com/en-us/windows/win32/fileio/naming-a-file

Main Tweet:
https://twitter.com/Foone/status/1058685897829318656
  
 </BR>

<h2>\\.\globalroot\device\condrv\kernelconnect</h2>

- <b>Compatibility:</b> XP, 10
- <b>Cause:</b> BSOD.
- <b>How it works</b>: When Windows try to connecting to this device (\\.\globalroot\device\condrv\kernelconnect), developers are expected to pass along the 'attach' extended attribute to communicate with the device properly. If you try to connect to the path without passing the attribute due to improper error checking, it will cause an exception that causes a Blue Screen of Death
- <b>How to reproduce the bug:</b> There are several ways to reproduce the bug, you can create a shorctut (.lnk) that leads to the path, you can make a .url file, you can recall it from a web page, but simply type it and send it from the browser, and to some users they say just type it on google and hit enter to reproduce the bug. I strongly believe it also works from CMD/Powershell/Code.

Article: https://www.bleepingcomputer.com/news/security/windows-10-bug-crashes-your-pc-when-you-access-this-location/

Article:https://borncity.com/win/2021/01/18/windows-10-bug-allows-bsod-by-entering-a-path-in-a-browser/

The Bug on Browser:https://docs.microsoft.com/en-us/answers/questions/235907/windows-crash-when-navigate-39globalrootdevicecond.html

Video: https://www.youtube.com/watch?v=8OuW9mykeds
  
</BR>


<h2>C:\:$i30:$bitmap</h2>


<b>DANGER!!!! USE ONLY IN VB!!!</b>

<b>DONT COPY THIS STRING ON YOUR MAIN PC!!!</b> 

<b>EVEN ONLY COPYING AND PASTEING THE STRING IS REALLY DANGEROUS!!!!!</b>

<b>YOU SERIOUSLY RISK OF COMPROMISING YOUR FILESYSTEM AND LOSING ALL THE DATA ON THE DISK!!!</b>

- <b>Compatibility:</b> 10
- <b>Cause:</b> Drive/NTFS Corruption, Crash and Restart the system.
- <b>How it works:</b> A drive can become corrupted by merely trying to access the $i30 NTFS attribute on a folder in a certain way. The Windows NTFS Index Attribute, or '$i30' string, is an NTFS attribute associated with directories that contains a list of a directory's files and subfolders. In some cases, the NTFS Index can also include deleted files and folders, which comes in handy when conducting an incident response or forensics. For now it is unclear why accessing this attribute corrupts the drive, but it's works....
- <b>How to reproduce the bug:</b> <b>I REPEAT, USE THIS STRING ONLY IN VIRTUAL BOX OR IN A TARGET MACHINE!!!</b> That are several ways to reproduce this bug, The less sophisticated way is to call it from the terminal with the cd command, it's possible also inject the path in a shortcut (.url) file, and windows explorer when try to open the file restart the pc.... But have a lot or more sophisticated ways, the more dangerous skill of this string it's probably that would trigger the vulnerability even if the user never opened the file! During my tests the mere fact of copying, pasting the path on a txt file and saving it can trigger the bug.
If inserted inside a .zip or .rar file the bug is executed only when the compressed file is opened ... It's a <b>NASTY BUG!!!!</b>

Article: https://www.bleepingcomputer.com/news/security/windows-10-bug-corrupts-your-hard-drive-on-seeing-this-files-icon/

Video: https://www.youtube.com/watch?v=KGsTi-iVmLY

Original Tweet: https://twitter.com/Slmi0xC/status/1349983599865466881

Interesting Tweet: https://twitter.com/wdormann/status/1347995993548206087

</BR>

<h2>wmic ComputerSystem where "name='%ComputerName%'" call rename HAL9TH</h2>

What can I say... this is not a real "Bad String", I would rather call it a "Vey Bad Idea".
In any case, with this technique you can bypass Windows Defender by simply changing the name of the target computer to "HAL9TH."

</br>

![Alt text](https://raw.githubusercontent.com/JonnyBanana/W1Nd0wS_BADstrings/main/img/HAL9TH.png "W1Nd0wS_BADstrings")

</BR>

Basically, to bypass WIndefender's defenses, simply run this command from an administrator prompt:

<b>wmic ComputerSystem where "name='%ComputerName%'" call rename HAL9TH</b>

</br>

And then you only need to restart the computer to make the changes effective.</BR>
And voila, the game is done...

</br>

In practice, an attacker can simply place a downloader file in the Windows %startup% folder (possibly encrypted), </br>
which if done well will not be detected as a threat at the time...</br>
This file will simply wait until a reboot before executing its commands, </br>
which will then download the real malware (hosted somewhere) to the victim computer, </br>
once Windows Defender is no longer a problem, thanks to the aforementioned command.</br>

Of course it requires admin permissions, but from firsthand experience i know </br>
that there are still plenty of Windows PCs that are not password protected.</br>

This technique was discovered by <b>@not_matthias</b></br>

Original Twet: https://twitter.com/not_matthias/status/1583213833694633990
  
</BR>

A special thank to my friend <a href="https://github.com/erikyo?tab=repositories">Erikyo</a> for letting me discover it

</BR>

<h2>To Do:</h2>

Do you know of any other strings it didn't find here? Very well!

Please Fork and Merge the Repo or simply contact me. 

You can find all my contacts in the home of my github: https://github.com/JonnyBanana










