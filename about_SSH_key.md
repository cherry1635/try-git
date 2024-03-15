# Config your key-pair

you should generate ssh key-pair.

ssh-keygen -t ed25519 -C "your_email@example.com"


first
```
# Set the sshd service to be started automatically
Get-Service -Name sshd | Set-Service -StartupType Automatic

# Now start the sshd service
Start-Service sshd

# 手动启动 ssh-agent
Start-Service ssh-agent


# start ssh
ssh-agent -s
# list all key file
ssh-add -l
# No files
// The agent has no identities.

# add a private to ssh-agent
ssh-add /your_private_key_path
```

[GitHub about config SSH -- quick look](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)