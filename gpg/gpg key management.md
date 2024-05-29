# Key Management
Below are some of the Key management operations 

## Listing Keys
Listing Public Keys
```
gpg --list-keys
```

Listing Private Keys
```
gpg --list-secret-keys
```

## Exporting Keys
Exporting Public Key
```
gpg --export -a "User Name" > public_key.asc
```

Exporting Private Key
```
gpg --export-secret-keys -a "User Name" > private_key_backup.asc
```

## Importing Keys
Importing Public Key
```
gpg --import public_key.asc
```

Importing Private Key
```
gpg --import private_key_backup.asc
```

## Backup Keys
Backup all Secret Keys
```
gpg --export-secret-keys -a > all_private_keys_backup.asc
```

Restore keys from Backup
```
gpg --import all_private_keys_backup.asc
```

## Deleting Keys
Deleting Public Key
```
gpg --delete-key "User Name"
```

Deleting Private Key
```
gpg --delete-secret-key "User Name"
```

