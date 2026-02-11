VIDEO: https://www.youtube.com/watch?v=uElWqzjC1eI

**Method 1: localonly**

Shift F10 to open cmd

start ms-cxh:localonly (Stopped working in latest versions)

**Method 2: bypassnro**

Shift F10 to open cmd

Turn off internet and then run this: oobe\bypassnro (Stopped working in latest versions)

**Method 3: Developer console**

Press Control+Shift+J to open Developer Console

and then type this: WinJS.Application.restart(“ms-cxh:localonly”)

**Method 4: Registry add BypassNPO**

Shift F10 to open cmd

Run regedit

Registry value add:

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE

DWord 32-bit value

BypassNRO

Set value to 1

Shutdown /r /t 0

**Method 5: Registry HideOnlineAccountScreens**

Shift F10 to open cmd

Run regedit

Registry value add:

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE

New 32-bit value

HideOnlineAccountScreens

Set value to 1

**Method 6: local user:**

Shift F10 to open cmd

net user "username" * /add

net localgroup administrators "username" /add

cd oobe

msoobe && shutdown -r

**Method 7: local user more complex:**

Shift F10 to open cmd

net user "username" * /add

net localgroup administrators "username" /add

net user "username" /active:yes

net user "username" /expires:never

net user "Administrator" /active:no

net user "defaultuser0" /delete

net user

Then go into regEdit HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE

Delete DefaultAccountSAMName, Delete DefaultAccountSID, Delete DefaultAccountAction

Edit LaunchUserOOBE and rename SkipMachineOOBE

Make sure value is 1

Shutdown /r /t 0

**Method 8: Copy BypassNRO script into cmd:**

Shift F10 to open cmd

Paste in the following commands:

reg add HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE /v BypassNRO /t REG_DWORD /d 1 /f
shutdown /r /t 0

**Method 9: Create a bat script:**

Shift F10 to open cmd

Run a batch script that contains these links:

@echo off
reg add HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\OOBE /v BypassNRO /t REG_DWORD /d 1 /f
shutdown /r /t 0
