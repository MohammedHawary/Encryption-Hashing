## Online Website To Cracking Hashes

1. [crackstation](https://crackstation.net/)

2. [md5hashing](https://md5hashing.net/hash/)

## Good Tool

1. [hashID · PyPI](https://pypi.org/project/hashID/)

2. hashcat
   
   ```bash
   hashcat -m 0 hash1.txt /usr/share/wordlists/rockyou.txt
   ```
   
   -m modul number from this site [hashcat](https://hashcat.net/wiki/doku.php?id=example_hashes) or `hashcat -h |grep sha256`

3. tot-bcrypt.py

## Websites To Know Type of Hash

1. [Hash Type Identifier - Identify unknown hashes](https://hashes.com/en/tools/hash_identifier)     Awesome

2. [hashcat](https://hashcat.net/wiki/doku.php?id=example_hashes)

## Tools To Know Type of Hash

1. hash-identifier
   
   | Prefix                                                          | Algorithm                                                  |
   | --------------------------------------------------------------- |:----------------------------------------------------------:|
   | \$1\$                                                           | md5crypt, used in Cisco stuff and older Linux/Unix systems |
   | \$2\$,\$2a\$, \$2b\$, \$2x\$, \$2y\$                            | Bcrypt (Popular for web applications)                      |
   | \$6\$ osha512crypt (Default for most Linux/Unix systems)pennssl |                                                            |

#### Create sha512crypt

```bash
openssl passwd -1 -salt [salt] [newpasswordhere]
mkpasswd -m sha-512 newpasswordhere
```

---

# John The ripper

If You didn't Know Type of Hash

```bash
john --wordlist=/usr/share/wordlists/rockyou.txt hash_to_crack.txt
```

Format-Specific Cracking

```bash
john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt hash_to_crack.txt
```

Use this Command to know hashes Formats

```bash
john --list=formats
```

You Can Built Your Custom Rule with this flag `--rule=ruleName`

https://www.openwall.com/john/doc/RULES.shtml

---

# Cracking Zip Files(zip2john)

Command

```bash
zip2john [options] [zip file] > [output file]
zip2john zipfile.zip > zip_hash.txt
```

Cracking

```bash
zip2john zipfile.zip > zip_hash.txt
john --wordlist=/usr/share/wordlists/rockyou.txt zip_hash.txt
```

---

# Cracking rar files(rar2john)

Command

```bash
rar2john [rar file] > [output file]
rar2john rarfile.rar > rar_hash.txt
```

Cracking

```bash
rar2john rarfile.rar > rar_hash.txt
john --wordlist=/usr/share/wordlists/rockyou.txt rar_hash.txt
```

<mark>Note</mark>

install `unrar` to extract `rar` file

`pip install unrar`

---

# Cracking SSH Key Passwords(ssh2john)

Command

```bash
ssh2john [id_rsa private key file] > [output file]
ssh2john id_rsa > id_rsa_hash.txt
```

Cracking

```bash
ssh2john id_rsa > id_rsa_hash.txt
john --wordlist=/usr/share/wordlists/rockyou.txt id_rsa_hash.txt
```






