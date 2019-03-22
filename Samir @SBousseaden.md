#Hunt - 
1. [LM - Remote PowerShell] - you can hunt for it using 4648 with Additional Information pointing to HTTP, then exclude browser processes     and pay attention to processes not supposed to com via HTTP with alternative creds (i.e. svchost.exe or rundll32.exe) 

2. [LM-RDP] Pay attention to other than your known RDP clients connecting to 3389 (especially if SrcIp=DstIp) 👉 index=windows vendor_product="*sysmon*" EventCode=3 dest_port=3389 NOT (Image="C:\\Windows\\System32\\mstsc.exe") |stats count by Image, user

3. https://github.com/sbousseaden/EVTX-SAMPLES

4. [Start baselining CSC.exe Exec in ur env]: 
> process_name:csc.exe and parent_name:wscript.exe|cscript.exe|mshta.exe (JS/VBS C# payload delivery - cscript spawning csc)
> mshta.exe|wscript.exe|cscript.exe loading mscorwks.dll (C# execution via JS/VBS/HTA)




Refer:- https://twitter.com/SBousseaden
