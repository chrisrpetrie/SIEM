## Wazuh Agent Configuration

Configs for ossec.conf found in C:\Program Files (x86)\ossec-agent or equivalent location
*********************************************************************************************************
### Windows Defender

Add the following for logging Windows Defender events to Wazuh. The most common Anti Virus events are included. 

```xml
 <localfile>
    <location>Microsoft-Windows-Windows Defender/Operational</location>
    <log_format>eventchannel</log_format>
    <query>Event/System[EventID = 1006 or EventID = 1007 or EventID = 1008 or EventID = 1009 or EventID = 1010 or EventID = 1011 or EventID = 1012 or EventID = 1013 or EventID = 1015 or EventID = 1116 or EventID = 1117 or EventID = 1118]</query>
  </localfile>
  ```
*********************************************************************************************************
### Sysmon

Add the following for logging Sysmon events to Wazuh
```xml
  <localfile>
    <location>Microsoft-Windows-Sysmon/Operational</location>
    <log_format>eventchannel</log_format>
  </localfile>
```  
  *********************************************************************************************************
### Agent Buffer Options

Generally recommend to leave as defaults, but sometimes for testing, this may need to be tweaked to prevent the flooding mechanism kicking in
```xml  
  <client_buffer>
    <disabled>yes</disabled>
    <queue_size>5000</queue_size>
    <events_per_second>500</events_per_second>
  </client_buffer>
```  
