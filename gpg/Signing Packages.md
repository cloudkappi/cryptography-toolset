# Signing and Verifying Software Packages
GPG is used by both Debain and Ubuntu to sign their software packages. User's can verify these signatures to ensure they are installing genuine software.

## Sign a Package

```
gpg --detach-sign --armor package.tar
```
This will create a signature file called package.tar.asc

## Verify a Package
```
gpg --verify package.tar.asc package.tar
```