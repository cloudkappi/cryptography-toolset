## 1. Generating Keys
- #### Generate an RSA Private Key:
```
openssl genpkey -algorithm RSA -out private_key.pem -aes256
```

- #### Generate a Public Key from a Private Key:
```
openssl rsa -pubout -in private_key.pem -out public_key.pem
```

## 2. Creating and Managing Certificates
- #### Generate a Certificate Signing Request (CSR):
```
openssl req -new -key private_key.pem -out request.csr
```
- #### Self-Sign a Certificate:
```
openssl req -x509 -new -key private_key.pem -out certificate.crt -days 365
```

## 3. Encrypting and Decrypting Data
- #### Encrypt a File:
```
openssl enc -aes-256-cbc -salt -in plaintext.txt -out encrypted.dat
```

- #### Decrypt a File:
```
openssl enc -aes-256-cbc -d -in encrypted.dat -out decrypted.txt
```

## 4. Creating Hashes
- #### Generate a SHA-256 Hash:
```
openssl dgst -sha256 -out hash.txt file_to_hash.txt
```

## 5. Digital Signatures
- #### Sign a File:
```
openssl dgst -sha256 -sign private_key.pem -out signature.bin file_to_sign.txt
```

- #### Verify a Signature:
```
openssl dgst -sha256 -verify public_key.pem -signature signature.bin file_to_sign.txt
```

## 6. Certificate Management
- #### Convert a Certificate from PEM to DER Format:
```
openssl x509 -outform der -in certificate.pem -out certificate.der
```

- #### View Certificate Information:
```
openssl x509 -in certificate.crt -text -noout
```

## 7. Setting Up a Simple Certificate Authority (CA)
- #### Create a Private Key for the CA:
```
openssl genpkey -algorithm RSA -out ca_key.pem -aes256
```

- #### Create a Self-Signed Root Certificate for the CA:
```
openssl req -x509 -new -key ca_key.pem -out ca_cert.pem -days 3650
```

- #### Sign a CSR with the CA Certificate:
```
openssl x509 -req -in request.csr -CA ca_cert.pem -CAkey ca_key.pem -CAcreateserial -out signed_cert.pem -days 365
```

## 8. Key and Certificate Conversion
- #### Convert a Private Key from PEM to DER Format:
```
openssl rsa -in private_key.pem -outform DER -out private_key.der
```

- #### Convert a PKCS#12 (.pfx or .p12) File to PEM Format:
```
openssl pkcs12 -in keystore.p12 -out keystore.pem -nodes
```

## 9. Creating PKCS#12 Files
- #### Combine a Private Key and Certificate into a PKCS#12 File:
```
openssl pkcs12 -export -out certificate.pfx -inkey private_key.pem -in certificate.crt -certfile ca_cert.pem
```

## 10.  Testing and Debugging SSL/TLS Connections
- #### Test SSL/TLS Connection to a Server:
```
openssl s_client -connect www.example.com:443
```

- #### View the Certificate Chain of a Server:
```
openssl s_client -showcerts -connect www.example.com:443
```

## 11.  Random Number Generation
- #### Generate Random Data:
```
openssl rand -out random_data.bin 256
```

## 12.  Password Hashing
- #### Generate a Password Hash:
```
openssl passwd -1 -salt mysalt mypassword
```

## 13.  Secure Communication Channels
- #### Create a Simple Encrypted Communication Tunnel:
```
openssl s_server -accept 4433 -cert server.crt -key server.key
```
```
openssl s_client -connect localhost:4433
```

## 14. Creating Key for S3 SSE-C Encryption
- ### Key generation using below command
```
openssl enc -aes-128-cbc -k mysecret -P
```
