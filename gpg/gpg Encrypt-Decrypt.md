# Table of Content
 
- [Table of Content](#table-of-content)
- [Self Encrypt and Decrypt of file](#self-encrypt-and-decrypt-of-file)
    - [Install gpg on Ubuntu](#install-gpg-on-ubuntu)
    - [To check any existing key](#to-check-any-existing-key)
    - [Generate new keys](#generate-new-keys)
    - [Exporting Public Key](#exporting-public-key)
    - [Encrypt a file](#encrypt-a-file)
    - [Decrypt a file](#decrypt-a-file)

# Self Encrypt and Decrypt of file
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