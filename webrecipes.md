# Web recipes
## fuzzing

### #1 identify directories agains dictionary 
```zsh
gobuster dir -t 50  -x php,txt,html,js -u http://10.10.10.28:80/cdn-cgi/login  -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -o gobuster_root.txt
```
*Remarks*: Sometimes is useful add flag -f to add slash at the end of calls. -x use exensions according the operating system and technologies detected. e.g. Apache better php but IIS better asp or aspx. 

*Remarks2*: For each interesting directory found you should run agains gobuster. Try different dictionaries or brute force if you suspect there is something there. 

```console
===============================================================
Gobuster v3.1.0
by OJ Reeves (@TheColonial) & Christian Mehlmauer (@firefart)
===============================================================
[+] Url:                     http://10.10.10.28:80/cdn-cgi/login
[+] Method:                  GET
[+] Threads:                 50
[+] Wordlist:                /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
[+] Negative Status codes:   404
[+] User Agent:              gobuster/3.1.0
[+] Extensions:              php,txt,html,js
[+] Timeout:                 10s
===============================================================
2021/07/15 21:11:06 Starting gobuster in directory enumeration mode
===============================================================
/admin.php            (Status: 302) [Size: 0] [--> /cdn-cgi/login/index.php]
/index.php            (Status: 200) [Size: 4679]
/db.php               (Status: 200) [Size: 0]
/script.js            (Status: 200) [Size: 0]
Progress: 27960 / 1102805 (2.54%)
```
### #2 Identify directories via Burbsuite
Just play with the web and go to *target* tab to check directory and files detected in spider process. Also is a good idea to check the calls.

### #3 Curl + grep
Detect links and emails and comments
```zsh
foo@bar$ curl -s http://10.10.10.28 | grep 'href\|src\|@\|<!--'
```
