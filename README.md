`Currently are 99 privacy tweaks available (01-01-2020)`

<a href="https://github.com/Mirinsoft/Debotnet/releases/latest" target="_blank">
 <img alt="Latest GitHub release" src="https://img.shields.io/github/release/mirinsoft/debotnet.svg" />
</a>
<a href="https://github.com/Mirinsoft/Debotnet/releases" target="_blank">
 <img alt="Downloads on GitHub" src="https://img.shields.io/github/downloads/Mirinsoft/debotnet/total.svg?style=flat-square" />
</a>
<a href="https://twitter.com/Mirinsoft" target="_blank">
 <img alt="Follow on Twitter" src="https://img.shields.io/twitter/follow/Mirinsoft.svg?label=Follow" />
</a>
</p>

*** 
<h1 align="center">
<sub>
<img  src="https://github.com/Mirinsoft/Debotnet/raw/master/debotnet.png"
      height="38"
      width="38">
</sub>
Debotnet - Your copy of Windows 10 is now Debotnetted!
</h1>

<p align="center">
<sup>A free and portable tool for controlling Windows 10's many privacy-related settings and keep your personal data private.</sup>

</p>

*** 


![alt text](https://www.mirinsoft.com/images/news/debotnet-intro.png)
*Custom templates can be found [here](https://github.com/mirinsoft/debotnet/blob/master/templates/design.md)*

## Debotnet is a free and portable tool for controlling Windows 10's many privacy-related settings and keep your personal data private.

The Windows 10 default privacy settings leave a lot to be desired when it comes to protecting you and your private information. Whenever I set up a new computer or update a current setup for my family or job, I always carefully go through the privacy settings for each install, making sure to lock it down to make it as private as possible.

Windows 10 has raised several concerns about privacy due to the fact that it has a lot of telemetry and online features, which send your data (sensitive and not) to Microsoft and can't be disabled, which means Microsoft can:

* Run software on your computer without your consent
* Get data from your computer without your consent
* Remove software and files from your computer without your consent

This qualifies Windows 10 as malware, and more specifically, a botnet.

#### You can read a more complete introduction in the blog post [here](https://www.mirinsoft.com/blog/news/60-take-charge-of-locking-down-your-privacy-with-debotnet).

Features
--------
* Disable telemetry and online features, which send your data (sensitive and not) to Microsoft
* Choose which unwanted functions you wish to disable
* Debotnet will show you what it's doing. You have full control, because the executing code can be viewed in a simple text editor
* Simple scripting engine for adding custom privacy rules
* Debug mode. E.g. the Test mode lets you see which values are twisted in registry or commands executed
* Scripts updated on GitHub
* Modern and familiar UI, with [template support](https://github.com/Mirinsoft/Roboget/blob/master/templates/templates.md)
* Small footprint. No installation required.
* Portable
* 100% Free Software ([CC BY 4.0](https://creativecommons.org/licenses/by/4.0/))

## How does it work?
As above mentioned Debotnet's main tools (in this case the scripts for debotnetting Windows) are not hard coded. Debotnet is based upon simple .DS1 files which define exactly which registry keys, files and or/services should be disabled, blocked, deleted etc. and preserved by the program. These script files allows you to execute command-line tools and parameter and also simple PowerShell code.

Here is a simple script for debotnetting a part of Windows.
```
[Info]
ID=No more forced updates
Ver=1.0
Desc=This will notify when updates are available, and you decide when to install them.\n\nThe values added to registry with this script will prevent forced updates.
Dev=Federico Dossena
DevURL=https://github.com/adolfintel/Windows10-Privacy
WinVer=Compatible with Windows 10
Evaluation=Recommended
EvaluationColor=009e5e

[Code]
Task1=Try,query "HKLM\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU" /v NoAutoUpdate,STDOUT
Task2=Try,query "HKLM\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU" /v AUOptions,STDOUT
Task3=Try,query "HKLM\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU" /v ScheduledInstallDay,STDOUT
Task4=Try,query "HKLM\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU" /v ScheduledInstallTime,STDOUT
File5=Reg,add "HKLM\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU" /v NoAutoUpdate /t REG_DWORD /d 0 /f,STDOUT
File6=Reg,add "HKLM\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU" /v AUOptions /t REG_DWORD /d 2 /f,STDOUT
File7=Reg,add "HKLM\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU" /v ScheduledInstallDay /t REG_DWORD /d 0 /f,STDOUT
File8=Reg,add "HKLM\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate\AU" /v ScheduledInstallTime /t REG_DWORD /d 3 /f,STDOUT

```

## Download 
http://www.imirin.com/downloads

## Suggesting features / providing feedback
Please use the [official community](https://www.mirinsoft.com/community) or report an [Issue on GitHub](https://github.com/mirinsoft/debotnet/issues/new)

## Additional information

#### More Information about Debotnet can be found on the [official website](https://www.mirinsoft.com/ms-apps/debotnet)
#### Several scripts are based upon the Windows 10 privacy guide from @https://github.com/adolfintel/Windows10-Privacy

<br>

<p align="center">
<sup>&copy Copyright 2020 <a href="https://www.mirinsoft.com" target="_blank">Mirinsoft</a></sup>
</p>
