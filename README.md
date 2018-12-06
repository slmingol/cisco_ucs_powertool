### Build
```
$ docker build --tag cisco_ucs_powertool .
Sending build context to Docker daemon  48.13kB
Step 1/8 : FROM mcr.microsoft.com/powershell:latest
 ---> a273f3d162f4
Step 2/8 : RUN apt-get update &&     apt-get install -y --no-install-recommends 	wget unzip
 ---> Running in c699fca81130
Get:1 http://archive.ubuntu.com/ubuntu bionic InRelease [242 kB]
Get:2 http://security.ubuntu.com/ubuntu bionic-security InRelease [83.2 kB]
Get:3 http://archive.ubuntu.com/ubuntu bionic-updates InRelease [88.7 kB]
Get:4 http://archive.ubuntu.com/ubuntu bionic-backports InRelease [74.6 kB]
Get:5 http://archive.ubuntu.com/ubuntu bionic/universe amd64 Packages [11.3 MB]
Get:6 http://security.ubuntu.com/ubuntu bionic-security/main amd64 Packages [277 kB]
Get:7 http://security.ubuntu.com/ubuntu bionic-security/universe amd64 Packages [124 kB]
Get:8 http://security.ubuntu.com/ubuntu bionic-security/multiverse amd64 Packages [1,367 B]
Get:9 http://archive.ubuntu.com/ubuntu bionic/restricted amd64 Packages [13.5 kB]
Get:10 http://archive.ubuntu.com/ubuntu bionic/multiverse amd64 Packages [186 kB]
Get:11 http://archive.ubuntu.com/ubuntu bionic/main amd64 Packages [1,344 kB]
Get:12 http://archive.ubuntu.com/ubuntu bionic-updates/multiverse amd64 Packages [6,931 B]
Get:13 http://archive.ubuntu.com/ubuntu bionic-updates/restricted amd64 Packages [10.7 kB]
Get:14 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 Packages [588 kB]
Get:15 http://archive.ubuntu.com/ubuntu bionic-updates/universe amd64 Packages [747 kB]
Get:16 http://archive.ubuntu.com/ubuntu bionic-backports/universe amd64 Packages [3,655 B]
Fetched 15.1 MB in 6s (2,362 kB/s)
Reading package lists...
Reading package lists...
Building dependency tree...
Reading state information...
The following additional packages will be installed:
  libpsl5
Suggested packages:
  zip
Recommended packages:
  publicsuffix
The following NEW packages will be installed:
  libpsl5 unzip wget
0 upgraded, 3 newly installed, 0 to remove and 4 not upgraded.
Need to get 524 kB of archives.
After this operation, 1,588 kB of additional disk space will be used.
Get:1 http://archive.ubuntu.com/ubuntu bionic/main amd64 libpsl5 amd64 0.19.1-5build1 [41.8 kB]
Get:2 http://archive.ubuntu.com/ubuntu bionic-updates/main amd64 wget amd64 1.19.4-1ubuntu2.1 [316 kB]
Get:3 http://archive.ubuntu.com/ubuntu bionic/main amd64 unzip amd64 6.0-21ubuntu1 [167 kB]
debconf: delaying package configuration, since apt-utils is not installed
Fetched 524 kB in 2s (268 kB/s)
Selecting previously unselected package libpsl5:amd64.
(Reading database ... 5641 files and directories currently installed.)
Preparing to unpack .../libpsl5_0.19.1-5build1_amd64.deb ...
Unpacking libpsl5:amd64 (0.19.1-5build1) ...
Selecting previously unselected package wget.
Preparing to unpack .../wget_1.19.4-1ubuntu2.1_amd64.deb ...
Unpacking wget (1.19.4-1ubuntu2.1) ...
Selecting previously unselected package unzip.
Preparing to unpack .../unzip_6.0-21ubuntu1_amd64.deb ...
Unpacking unzip (6.0-21ubuntu1) ...
Setting up libpsl5:amd64 (0.19.1-5build1) ...
Setting up unzip (6.0-21ubuntu1) ...
Processing triggers for libc-bin (2.27-3ubuntu1) ...
Setting up wget (1.19.4-1ubuntu2.1) ...
Removing intermediate container c699fca81130
 ---> 128242a63878
Step 3/8 : RUN mkdir -p ~/.local/share/powershell/Modules
 ---> Running in b7040014d469
Removing intermediate container b7040014d469
 ---> 8711d835d328
Step 4/8 : RUN mkdir -p ~/.config/powershell/
 ---> Running in 026bbb13b88c
Removing intermediate container 026bbb13b88c
 ---> 261e505ad861
Step 5/8 : ADD https://community.cisco.com/kxiwq67737/attachments/kxiwq67737/4354j-docs-cisco-dev-ucs-integ/518/2/ucspowertoolcore.zip /tmp
Downloading [==================================================>]  19.63MB/19.63MB
 ---> 4adecda47078
Step 6/8 : RUN unzip /tmp/ucspowertoolcore.zip -d ~/.local/share/powershell/Modules/
 ---> Running in a6bf4d032314
Archive:  /tmp/ucspowertoolcore.zip
  inflating: /root/.local/share/powershell/Modules/Cisco.IMC/Cisco.Imc.Cmdlets.dll
  inflating: /root/.local/share/powershell/Modules/Cisco.IMC/Cisco.Imc.Cmdlets.dll-help.xml
  inflating: /root/.local/share/powershell/Modules/Cisco.IMC/Cisco.Imc.dll
  inflating: /root/.local/share/powershell/Modules/Cisco.IMC/Cisco.IMC.psd1
  inflating: /root/.local/share/powershell/Modules/Cisco.IMC/ImcAlias.psm1
  inflating: /root/.local/share/powershell/Modules/Cisco.UCS.Core/CcoImageMeta.xml
  inflating: /root/.local/share/powershell/Modules/Cisco.UCS.Core/Cisco.Ucs.Core.Cmdlets.dll
  inflating: /root/.local/share/powershell/Modules/Cisco.UCS.Core/Cisco.Ucs.Core.Cmdlets.dll-help.xml
  inflating: /root/.local/share/powershell/Modules/Cisco.UCS.Core/Cisco.Ucs.Core.dll
  inflating: /root/.local/share/powershell/Modules/Cisco.UCS.Core/Cisco.UCS.Core.psd1
  inflating: /root/.local/share/powershell/Modules/Cisco.UCS.Core/CoreAlias.psm1
  inflating: /root/.local/share/powershell/Modules/Cisco.UCS.Core/UcsHclToolMeta.xml
  inflating: /root/.local/share/powershell/Modules/Cisco.UCSCentral/Cisco.UcsCentral.Cmdlets.dll
  inflating: /root/.local/share/powershell/Modules/Cisco.UCSCentral/Cisco.UcsCentral.Cmdlets.dll-help.xml
  inflating: /root/.local/share/powershell/Modules/Cisco.UCSCentral/Cisco.UcsCentral.dll
  inflating: /root/.local/share/powershell/Modules/Cisco.UCSCentral/Cisco.UCSCentral.psd1
  inflating: /root/.local/share/powershell/Modules/Cisco.UCSCentral/UcsCentralAlias.psm1
  inflating: /root/.local/share/powershell/Modules/Cisco.UCSManager/Cisco.Ucsm.Cmdlets.dll
  inflating: /root/.local/share/powershell/Modules/Cisco.UCSManager/Cisco.Ucsm.Cmdlets.dll-help.xml
  inflating: /root/.local/share/powershell/Modules/Cisco.UCSManager/Cisco.Ucsm.dll
  inflating: /root/.local/share/powershell/Modules/Cisco.UCSManager/Cisco.UCSManager.psd1
  inflating: /root/.local/share/powershell/Modules/Cisco.UCSManager/UcsAlias.psm1
  inflating: /root/.local/share/powershell/Modules/Start-UcsPowerTool.ps1
Removing intermediate container a6bf4d032314
 ---> 8e3e55ecec75
Step 7/8 : RUN mv ~/.local/share/powershell/Modules/Start-UcsPowerTool.ps1 ~/.config/powershell/Microsoft.PowerShell_profile.ps1 -f
 ---> Running in bb2066a63ddd
Removing intermediate container bb2066a63ddd
 ---> d7923d54acb1
Step 8/8 : CMD [ "pwsh" ]
 ---> Running in 1b079bd9c507
Removing intermediate container 1b079bd9c507
 ---> 853c90a09250
Successfully built 853c90a09250
Successfully tagged cisco_ucs_powertool:latest
```

### Example
```
$ docker run -it cisco_ucs_powertool
PowerShell 6.1.1
Copyright (c) Microsoft Corporation. All rights reserved.

https://aka.ms/pscore6-docs
Type 'help' to get help.

          Welcome to Cisco UCS PowerTool Core Suite 2.2.1.8 Beta

Log in to a UCS Manager Domain:                                         Connect-Ucs
To generate PowerShell code from a running UCS Manager GUI:             ConvertTo-UcsCmdlet
To show object metadata for all UCS PowerTool commands:                 Get-UcsCmdletMeta

Log in to an IMC of standalone UCS server:                              Connect-Imc
Generate PowerShell code from a running IMC of standalone UCS server:   ConvertTo-ImcCmdlet
Show object metadata for all IMC PowerTool cmdlets:                     Get-ImcCmdletMeta

Log in to a UCS Central server:                                         Connect-UcsCentral
To generate PowerShell code from a running UCS Central GUI:             ConvertTo-UcsCentralCmdlet
To show object metadata for all UCS Central PowerTool commands:         Get-UcsCentralCmdletMeta
Once you've connected, display the details of active session(s):        Get-UcsPsSession

If you need more help, visit the UCS PowerTool user community:          https://communities.cisco.com/ucsintegrations

PS /> 
```

```
PS /> Get-Module -ListAvailable


    Directory: /root/.local/share/powershell/Modules


ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Binary     2.2.1.8    Cisco.IMC                           Desk      {FnStartImcServer, FnStopImcServer, FnRestartImcServer, FnResetImcServer...}
Binary     2.2.1.8    Cisco.UCS.Core                      Desk
Binary     2.2.1.8    Cisco.UCSCentral                    Desk      {FnRemoveUcsCentralFex, FnDecommissionUcsCentralFex, FnRecommissionUcsCentralFex, FnAcknowledgeUcsCentralFex...}
Binary     2.2.1.8    Cisco.UCSManager                    Desk      {FnRemoveUcsBlade, FnDecommissionUcsBlade, FnRecommissionUcsBlade, FnAcknowledgeUcsBlade...}


    Directory: /opt/microsoft/powershell/6/Modules


ModuleType Version    Name                                PSEdition ExportedCommands
---------- -------    ----                                --------- ----------------
Manifest   1.2.2.0    Microsoft.PowerShell.Archive        Desk      {Compress-Archive, Expand-Archive}
Manifest   6.1.0.0    Microsoft.PowerShell.Host           Core      {Start-Transcript, Stop-Transcript}
Manifest   6.1.0.0    Microsoft.PowerShell.Management     Core      {Add-Content, Clear-Content, Clear-ItemProperty, Join-Path...}
Manifest   6.1.0.0    Microsoft.PowerShell.Security       Core      {Get-Credential, Get-ExecutionPolicy, Set-ExecutionPolicy, ConvertFrom-SecureString...}
Manifest   6.1.0.0    Microsoft.PowerShell.Utility        Core      {Format-List, Format-Custom, Format-Table, Format-Wide...}
Script     1.1.7.2    PackageManagement                   Desk      {Find-Package, Get-Package, Get-PackageProvider, Get-PackageSource...}
Script     1.6.7      PowerShellGet                       Desk      {Find-Command, Find-DSCResource, Find-Module, Find-RoleCapability...}
Script     0.0        PSDesiredStateConfiguration         Desk      {Generate-VersionInfo, Set-PSMetaConfigDocInsProcessedBeforeMeta, Get-PSMetaConfigurationProcessed, Get-PSMetaConfigDocument...
Script     2.0.0      PSReadLine                          Desk      {Get-PSReadLineKeyHandler, Set-PSReadLineKeyHandler, Remove-PSReadLineKeyHandler, Get-PSReadLineOption...}
Binary     1.1.2      ThreadJob                           Desk      Start-ThreadJob


PS />
```
```
PS /> Get-Command -Module Cisco.UcsManager | head -20

CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Alias           Acknowledge-UcsBlade                               2.2.1.8    Cisco.UCSManager
Alias           Acknowledge-UcsChassis                             2.2.1.8    Cisco.UCSManager
Alias           Acknowledge-UcsFault                               2.2.1.8    Cisco.UCSManager
Alias           Acknowledge-UcsFex                                 2.2.1.8    Cisco.UCSManager
Alias           Acknowledge-UcsRackUnit                            2.2.1.8    Cisco.UCSManager
Alias           Acknowledge-UcsServerUnit                          2.2.1.8    Cisco.UCSManager
Alias           Acknowledge-UcsSlot                                2.2.1.8    Cisco.UCSManager
Alias           Add-UcsMo                                          2.2.1.8    Cisco.UCSManager
Alias           Associate-UcsServiceProfile                        2.2.1.8    Cisco.UCSManager
Alias           Compare-UcsMo                                      2.2.1.8    Cisco.UCSManager
Alias           Decommission-UcsBlade                              2.2.1.8    Cisco.UCSManager
Alias           Decommission-UcsChassis                            2.2.1.8    Cisco.UCSManager
Alias           Decommission-UcsFex                                2.2.1.8    Cisco.UCSManager
Alias           Decommission-UcsRackUnit                           2.2.1.8    Cisco.UCSManager
Alias           Decommission-UcsServerUnit                         2.2.1.8    Cisco.UCSManager
Alias           Disable-UcsDiskLocatorLed                          2.2.1.8    Cisco.UCSManager
Alias           Disassociate-UcsServiceProfile                     2.2.1.8    Cisco.UCSManager
PS />
```

```
PS /> $handle1 = Connect-Ucs -Name 192.168.111.206

cmdlet Connect-Ucs at command pipeline position 1
Supply values for the following parameters:
Credential
User: ucs-MY-IDM-DOM\joeuser
Password for user ucs-IDM-DOM\joeuser: ****************

PS /> Get-UcsPSSession


NumPendingConfigs           : 0
Ucs                         : ucs-fi-01a
Cookie                      : XXXXXXXXXXXXXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
Domains                     :
LastUpdateTime              : 12/5/18 10:53:50 PM
Name                        : 192.168.111.206
NoSsl                       : False
NumWatchers                 : 0
Port                        : 443
Priv                        : {admin, read-only}
PromptOnCompleteTransaction : False
Proxy                       :
RefreshPeriod               : 600
SessionId                   : web_15932_A
TransactionInProgress       : False
Uri                         : https://192.168.111.206
UserName                    : ucs-IDM-DOM\joeuser
Version                     : 3.2(3a)
VirtualIpv4Address          : 192.168.111.206
WatchThreadStatus           : None



PS />
```

### References
- https://hub.docker.com/r/microsoft/powershell/
- https://github.com/PowerShell/PowerShell-Docker
- https://github.com/PowerShell/PowerShell
- https://community.cisco.com/t5/unified-computing-system/login-user-syntax-for-ucs-powertools/td-p/3033114a
- https://blog.ukotic.net/2017/05/15/cisco-ucs-powertool-suite-part-1/
- https://community.cisco.com/t5/cisco-developed-ucs-integrations/cisco-ucs-powertool-core-suite-for-powershell-core-modules-for/ta-p/3643354
- https://hub.docker.com/r/ciscoucspowertool/powertoolcore/~/dockerfile/
