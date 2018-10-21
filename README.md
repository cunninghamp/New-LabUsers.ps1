# New-LabUsers.ps1
PowerShell script to populate Active Directory in a test lab environment with user accounts.

This script relies on the Active Directory PowerShell module. If you are running it on your test lab domain controller the module should already be present and the script should work. I have tested the script on Windows Server 2012 R2 only at this stage.

## Parameters

All parameters are optional. The script will default to use:

- The input file RandomNameList.txt
- Password length of 16 characters
- Top-level OU of "Company"
 
Use the script parameters if you need to change those values: 

- **InputFileName** - Use this parameter if you need to specify a different text file name containing
the list of users. A generated list of names is also provided with the script so that you can see the format required.
- **PasswordLength** - Use this parameter if you need to specify a different password length. By default
all the user accounts are created with a randomly generated password that is 16 characters long. You can reset the password for any user that you want to log on with.
- **OU** - Use this parameter if you want to name the top-level OU something different than the default name of "Company".

## Examples

Uses the RandomNameList.txt file to generate the list of user accounts in an OU called "Company" in Active Directory.
```
.\New-LabUsers.ps1
```

Uses the MyNames.txt file to generate the list of user accounts in an OU called "TestLab" in Active Directory.
```
.\New-LabUsers.ps1 -InputFileName .\MyNames.txt -PasswordLength 8 -OU TestLab
```

## Credits
Written by: Paul Cunningham

Find me on:

* My Blog:	https://paulcunningham.me
* Twitter:	https://twitter.com/paulcunningham
* LinkedIn:	https://au.linkedin.com/in/cunninghamp/
* Github:	https://github.com/cunninghamp

Check out my [books](https://paulcunningham.me/books/) and [courses](https://paulcunningham.me/training/) to learn more about Office 365 and Exchange Server.

Additional credits:

Random Password Generator function from Scripting Guys blog post http://blogs.technet.com/b/heyscriptingguy/archive/2013/06/03/generating-a-new-password-with-windows-powershell.aspx

Random name list generated from http://listofrandomnames.com

