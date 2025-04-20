# Config SSH in Github

1. #### Check for Existing SSH Keys

Open your terminal and run:
```bash
ls -al ~/.ssh
```

Look for files like id_ed25519 and id_ed25519.pub (or id_rsa and id_rsa.pub). If you don’t have them, proceed to generate a new key

2. #### Generate a New SSH Key

Run the following command (replace with your GitHub email):
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

- If your system does not support Ed25519, use:
```bash
 ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

- Press Enter to accept the default file location.
- Set a secure passphrase when prompted for added security


3. #### Add Your SSH Key to the SSH Agent

Start the SSH agent:
```bash
eval "$(ssh-agent -s)"
```

Add your private key to the agent:
```bash
ssh-add ~/.ssh/id_ed25519
```

(Use id_rsa if you generated an RSA key)

4. #### Add the SSH Key to Your GitHub Account

Copy your public key to the clipboard:
```bash
cat ~/.ssh/id_ed25519.pub
```

Log in to `GitHub`.

Go to Settings > `SSH` and `GPG keys` > New SSH key.

Paste the copied key, give it a descriptive title, and save

#
[GPG KEY](GPG-KEYS.md)