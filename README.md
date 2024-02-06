# DiaView-Packaging-Issue
DiaView-Packaging Issue: Issue on Windows 11. PackageGenerator Execute wix command error, candle.exe : error CNDL0103 : The system cannot find the file '~\AppData\Local\Temp\DiaviewPack\WixProject\' with type 'Source'.

The issue is with the packaging application Wix is looking at the wrong directory. If the users directory contains a space i.e. C:\Users\John Doe\AppData\Local\Temp\DiaviewPack\WixProject\ then the packaging environment looks at Doe\AppData\Local\Temp\DiaviewPack\WixProject\ which does not exist.

## Solving the issue
Open Powershell and execute the following command[^1]Path should be name and surname changed to just surname[^2]
[^1]: Make sure to execute as Administrator
```powershell
cmd /c mklink /d C:\Users\Doe\ 'C:\Users\John Doe'
```
Then add newly created path 'C:\Users\Doe\AppData\Local\Temp' to the Environmet Variables for user as TMP

[^2]: Replace path names with respective paths from the error and current user directory path
