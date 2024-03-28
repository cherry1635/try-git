Use GPG config Github Login and common usage

![hello](C:/NobodyKnow\GPG_book\pictures\kpl_gpg_config_start_ui.png)

The top pic will tell you, valid time.

----

diff from signing key and authentication key:

The difference between signing keys and authentication keys is that signing keys can be used to sign Git commits and authentication keys can be used to access repositories. If you add a key as only one type, then it can be used only for that purpose, but the same key may be added for both.

If you just want to access repositories, then all you need is an authentication key. If you want to use an SSH key to verify that your commits have not been modified or tampered with and that they did indeed come from you (and not someone who forged your name and email in commits), then you'd want a signing key (plus a recent version of Git).

The reason they're different sets is that they have different security models and so it makes sense to allow people to set different keys for different purposes if they so choose. This is also in line with best practices for cryptographic key management.

<h4>Simple Saying</h4>

if you want to request the service, show your authenti-key, else you want to submit some data, you must give your signing-key to tell others this is my submission.


<h4> Git GPG </h4>

```
git config --global user.signingkey <GPG Key ID>
git config --global commit.gpgsign true
```

<h4> how to know gpg key is ok with git?</h4>
To verify that your Git GPG key configuration is set up correctly, you can perform the following steps to confirm its functionality:

- Check GPG Key Availability: Ensure that you have a GPG key set up and available on your system. You can use the gpg --list-secret-keys command to list your GPG keys. Look for the key associated with your Git-related email address.

- Configure Git with GPG Key: Set your GPG key in the Git configuration using the git config --global user.signingkey <GPG Key ID> command. Replace <GPG Key ID> with the ID of your GPG key. This associates your GPG key with Git.

- Enable Commit Signing: Enable commit signing in Git by running the git config --global commit.gpgsign true command. This ensures that each commit will be signed with your GPG key.

- Make a Test Commit: Create a new commit in a Git repository. For example, you can modify a file, add it to the staging area using git add, and then commit it using git commit -m "Test commit".

- Check Commit Signature: After the commit is made, you can verify whether it was successfully signed with your GPG key. Run git log --show-signature to display the commit history with signature information. Look for the presence of "gpg: Signature made" and "gpg: Good signature" lines to confirm that the commit is signed and the signature is valid.

If you see the appropriate signature lines in the commit history, it indicates that your GPG key configuration is correctly set up, and your commits are being signed with your GPG key. This confirms that the commit signing process is functioning as expected

<h4> List all gpg key </h4>

```
gpg --list-secret-keys --keyid-format=long
git config --global user.signingkey 3AA5C34371567BD2
```

When committing changes in your local branch, add the -S flag to the git commit command:
```
$ git commit -S -m "YOUR_COMMIT_MESSAGE"
# Creates a signed commit

# try this
git config --global gpg.program "C:\Program Files (x86)\GnuPG\bin\gpg.exe"
```