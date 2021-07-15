# Windows priv escalation

## Enumeration

### #1 Getting user history
```bat
type C:\Users\<user>\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\ConsoleHost_history.txt
```
```bat
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
git
wsl -l -v
wsl
wsl -l -v
```
