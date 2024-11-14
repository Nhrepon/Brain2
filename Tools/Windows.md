## c driver user name change
- use this command to get user sid - wmic useraccount list full
- first create temp user and set account type administrator
- open pc with temp user
- open CMD in administrator mode
- use following command
```cmd

cd c:\users
ren "odlName" newName 

then go registry editor
Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Profilelist


```