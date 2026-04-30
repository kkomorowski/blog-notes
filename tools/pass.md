---
icon: lock
---

# `pass` - the standard unix password manager

## General notes

`pass` is a unix based password manager that securely stores the passwords
using the `gpg` encrypted files under a `git` repository.

## Example commands

### Generating the password

```
pass generate -c pass_name 12
               ↑            ↑
    Copy to clipboard       |
                      Password length
```

The password will be saved in the store, you can retrieve it using this
command:

```bash
pass pass_name
```

### Configuration environment variables

Add the configuration environment variables to your `.bashrc` or `.zshrc`:

### Default password length for `generate` command

Default password length is 32. If you wish to configure it use following
variable:

```bash
export PASSWORD_STORE_GENERATED_LENGTH=12
```
