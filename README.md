# DiaView-Packaging-Issue
DiaView-Packaging Issue: Issue on Windows 11. PackageGenerator Execute wix command error, candle.exe : error CNDL0103 : The system cannot find the file '~\AppData\Local\Temp\DiaviewPack\WixProject\' with type 'Source'.

The issue is with the packaging application Wix is looking at the wrong directory. If the users directory contains a space i.e. C:\Users\John Doe\AppData\Local\Temp\DiaviewPack\WixProject\ then the packaging environment looks at Doe\AppData\Local\Temp\DiaviewPack\WixProject\ which does not exist.

## Solving the issue
Open Powershell and execute the following command^1^
^1 Make sure not in Admin mode and thet the users folder is selected.^
```powershell
mklink /d Ogilvie\ C:\Users\Matthew Ogilvie
```

