Create an encrypted file using an SSH public key which can be decrypted on any system that has openssl. Encrypted file is a `tar.gz` archive which includes decryption instructions.

Very early state. Only RSA public keys currently supported and only *nix systems. Needs lots more testing and improvement.

# Usage

## Encryption

```
ede <ssh_pubkey_file or github_username> <file_or_dir_to_encrypt>
```

E.g:

```
ede juul ./mydir
```

This will create the file:

```
./mydir.encrypted.tar.gz
```

## Decryption

```
tar xvzf mydir.encrypted.tar.gz # extract file
# this results in the directory ./mydir/
less mydir/README # follow readme instructions
```

# ToDo
 
* test on different openssl versions
* support non-rsa keys
* add support for pubkey sources other than github
* windows support

# License

Apache 2.0
