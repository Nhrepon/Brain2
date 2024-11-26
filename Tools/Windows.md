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

## set custom DNS for Adguard
```
setting>network>adapter>propertise>tcp/ipv4>propertise>use dns server address

**To Block Ads:**
94.140.14.14
94.140.15.15

**To Block Adult Sites:**
94.140.14.15
94.140.15.16


```