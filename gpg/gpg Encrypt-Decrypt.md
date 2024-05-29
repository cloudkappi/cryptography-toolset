# Encrypt and Decrypt File

### Table of Content
**[1. Encrypt and Decrypt file](#encrypt-and-decrypt-file)**</br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.1 Install gpg on Ubuntu](#install-gpg-on-ubuntu)</br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.2 To check any existing key](#to-check-any-existing-key)</br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.3 Generate new keys](#generate-new-keys)</br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.4 Exporting Public Key](#exporting-public-key)</br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.5 Encrypt a file](#encrypt-a-file)</br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.6 Decrypt a file](#decrypt-a-file)</br>

### Install gpg on Ubuntu
```
sudo apt-get install gnupg
```
</br>

### To check any existing key
```
gpg --list-keys
```
</br>

### Generate new keys
```
gpg --full-generate-key
```

1. Select the Key type
2. Select the bit size
3. Enter expiry period
4. Enter the "real name" as its in Github account
5. Enter verified email id assocaited with the account
6. After final submission it will ask for Passphrase. This passphrase will be used during commit
</br>

### Exporting Public Key
```
gpg --export --armor --output gpg_public_key.asc abc@email.com
```
</br>

### Encrypt a file
```
gpg --output encrypted_file.gpg --encrypt --recipient userid file_to_encrypt.txt
```
</br>

### Decrypt a file
```
gpg --output decrypted_file.txt --decrypt encrypted_file.gpg
```
</br>