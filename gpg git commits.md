# Install gpg on Ubuntu with below command
sudo apt-get install gnupg

# To check any existing key in system
gpg --list-keys

# Generate new keys
gpg --full-generate-key

# Command to fetch Public keys. Copy paste the public key into github under GPG section for new key
gpg --list-secret-keys --keyid-format LONG

# Copy the Key ID from above output once public key is added
gpg --armor --export 530650148D937CE2

# Configure git global properties as below
git config --list
git config --global user.signingkey 530650148D937CE2 
git config --global commit.gpgsign true
git config --global tag.gpgsign true
which gpg
git config --global gpg.program /usr/bin/gpg


Once above configuration is completed, everytime a new commit is done it will be encrypted,
during the commit process, enter the passphrase set during key generation.
