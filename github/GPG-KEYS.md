# Configure GPG Keys in your GitHub account

1. #### Check for Existing GPG Keys or Generate a New One
    If you don’t have a GPG key, generate one using:

```bash
gpg --full-generate-key
```

- Choose the recommended algorithm (e.g., RSA or EdDSA).
- Follow the prompts to set your name, email, and passphrase.

To list existing keys:
```bash
gpg --list-secret-keys --keyid-format=long
```

2. #### Copy Your GPG Public Key
- Get the GPG key ID (replace KEY_ID with your actual key ID):
```bash
gpg --armor --export KEY_ID
```
> [!IMPORTANT]
> Copy the output (including the `-----BEGIN PGP PUBLIC KEY BLOCK-----` and `-----END PGP PUBLIC KEY BLOCK-----` lines).

3. #### Add Your GPG Key to GitHub

- Go to GitHub and click your profile photo in the upper-right corner.
- Select Settings.
- In the sidebar, click SSH and GPG keys.
- Next to the "GPG keys" header, click New GPG key.
- Paste your public key into the "Key" field.
- Give it a descriptive title.
- Click Add GPG key.
- If prompted, authenticate to confirm the action


#
[SSH-KEY](SSH-KEYS.md)