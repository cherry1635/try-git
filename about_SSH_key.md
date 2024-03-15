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


 ssh-add -l
256 SHA256:nVpcFsR+ZL9kR3bwMV9U/sY8nOmarzsttfsdb8OFF/M cherrise28@outlook.com (ED25519)

# to delete the key
ssh-add -d github_push_pull_mdy3_15_24
Identity removed: github_push_pull_mdy3_15_24 ED25519 (cherrise28@outlook.com)
# ssh-add-l
```

[GitHub about config SSH -- quick look](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account)


<h4> what is difference about authentication key and signing key in github </h4>
The difference between signing keys and authentication keys is that signing keys can be used to sign Git commits and authentication keys can be used to access repositories. If you add a key as only one type, then it can be used only for that purpose, but the same key may be added for both.

If you just want to access repositories, then all you need is an authentication key. If you want to use an SSH key to verify that your commits have not been modified or tampered with and that they did indeed come from you (and not someone who forged your name and email in commits), then you'd want a signing key (plus a recent version of Git).

The reason they're different sets is that they have different security models and so it makes sense to allow people to set different keys for different purposes if they so choose. This is also in line with best practices for cryptographic key management.