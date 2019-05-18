Threat Hunting - Hunt It Down!

1. Data Exfiltration - Network outgoing and failed and remote host equals *.tk| *.onion|*.xyz|*.cn|*.tor2web and process not in browsers.exe

2. Tampering - Deletion of Shadow copy files or disabling system restore in Windows. 
   Process run and Name = wmic.exe|vssadmin.exe and command line = *delete* (contains)
   Registry Write and Key = HKLM\Software\Microsoft\Windows Nt\SystemRestore\DisableSR and value = 1
   
3. Tampering - Manipulation of Windows Defender
   [Process] → [Run] → [Name=net.exe|powershell.exe|reg.exe] → [Command Line=*windefend*|*DisableRealtimeMonitoring*] (contains)
   
4. Process running with double extensions
   [Process] → [Run] → [Name equals *.docx.exe|*.pdf.exe|*.xlsx.exe|*.pptx.exe|*.mp4.exe|*.mp3.exe]
   
5. Sql ports communication to internet - Network outgoing and failed and remote ports =1433|1521|33060


Kindly watch this in raw format as * sign is not visible in the search queries mentioned above.


Refer - https://akkysanj.wordpress.com/2019/03/09/threat-hunting-hunt-it-down/
        https://twitter.com/Akky2892
