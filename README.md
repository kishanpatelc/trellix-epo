1. Run following commands before running Ansible scripts against remote windows servers:

Use DOS Prompt:
================
winrm quickconfig

Use Powershell:
================

 winrm set winrm/config/service '@{AllowUnencrypted="true"}'
 winrm set winrm/config/service/auth '@{Basic="true"}'
 
 NetSh Advfirewall set allprofiles state off
 Netsh Advfirewall show allprofiles


2. To view Application event log:
Get-WinEvent -LogName Application -MaxEvents 20 | Format-List

3. To tail an log file:
Get-Content .\install.log -Wait -Tail 60

4. Note for Installing Agent Handler: install script seems to always fail at the first time. Then it succeeds after a successful manual installation.