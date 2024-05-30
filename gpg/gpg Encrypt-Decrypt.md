# Encrypt and Decrypt File

### Table of Content
**[1. Encrypt and Decrypt file](#encrypt-and-decrypt-file)**</br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.1 Install gpg on Ubuntu](#install-gpg-on-ubuntu)</br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.2 To check any existing key](#to-check-any-existing-key)</br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.3 Generate new keys](#generate-new-keys)</br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.4 Exporting Public Key](#exporting-public-key)</br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.5 Encrypt a file](#encrypt-a-file)</br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[1.6 Decrypt a file](#decrypt-a-file)</br>
    </br>
**[2. Encrypt for multiple recipient](#encrypt-for-multiple-recipient)**</br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[2.1 Key Generation](#each-recipients-generates-their-keys)</br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[2.2 Exporting Public Keys](#exporting-public-keys)</br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[2.3 Importing Public Keys](#importing-public-keys)</br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[2.4 Encrypting File](#encrypting-file)</br>
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[2.5 Decrypting File](#decrypting-file)</br>

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

# Encrypt for multiple recipient

 GPG allows you to encrypt a message or file and recipients can decrypt it using their own private key. 

### Each recipients generates their keys 
```
gpg --gen-key
```

### Exporting Public Keys
```
gpg --export -a "Alice" > alice_public_key.asc
```
```
gpg --export -a "Bob" > bob_public_key.asc
```

### Importing Public Keys
```
gpg --import bob_public_key.asc
```
```
gpg --import alice_public_key.asc
```

### Encrypting File
```
gpg --output message_for_alice_and_bob.gpg --encrypt --recipient alice@example.com --recipient bob@example.com message.txt
```

### Decrypting File
```
gpg --output decrypted_message.txt --decrypt message_for_alice_and_bob.gpg
```

#### Additional Notes

GPG is primarly designed to encrypting individual files, it is combined with 'tar' to encrypt multiple files, folders, file system