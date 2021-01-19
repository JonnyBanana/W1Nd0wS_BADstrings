# W1Nd0wS_BADstrings
A collection of Evil String for Windows that causes various type of crash, bsod, filesystem corruption, etc.

<img src="https://raw.githubusercontent.com/JonnyBanana/W1Nd0wS_BADstrings/main/img/bad.jpg" alt="" data-canonical-src="https://raw.githubusercontent.com/JonnyBanana/W1Nd0wS_BADstrings/main/img/bad.jpg" width="250" height="250" />



<h2>C:\$MFT\123</h2>

- Compatibility: Vista, 7, 8.
- Cause: Slow, and crash the system.
- How it works: Windows uses “$MFT” for special metadata files that are used by NTFS file system, and Windows fail to handle this directory name correctly.
- How to reproduce the bug: There are several ways to exploit the exploit, you can simply call it from the windows searchbar, from cmd or powershell, and also from an html page (tested with windows explorer, but I think it works with all browsers) by calling a file in folder C:\$MFT\123.


Full Explanation with P0C:
https://habr.com/en/company/aladdinrd/blog/329166/
