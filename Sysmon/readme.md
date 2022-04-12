### Sysmon Install and Config
This will install Sysmon on the local system using the SwiftOnSecurity configuration file.

Thanks to SwiftOnSecurity for this resource https://github.com/SwiftOnSecurity/sysmon-config

1. Place the sysmon executable and the sysmonconfig-export.xml in the same folder
2. Run  the command (as Administrator) `sysmon64.exe -i sysmonconfig-export.xml -accepteula`
