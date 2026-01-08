# How Do You Handle Security Requirements Like SSH and GPG Keys?

## Introduction

Before pushing code to GitHub or signing commits, authentication is required. GitHub supports secure authentication and verification using **SSH keys** and **GPG keys**. Both methods are based on public–private key cryptography, which provides strong security.

---

## Public and Private Key Concept

Both SSH and GPG use a **public–private key pair**:

* **Private key**: Stays on your local machine and must never be shared
* **Public key**: Shared with services like GitHub to verify your identity

The private key performs the action (authentication or signing), while the public key verifies that the action is valid.

---

## What Are GPG Keys?

**GPG (Gnu Privacy Guard)** keys are mainly used to:

* Sign commits
* Sign files
* Verify that content has not been modified

When a commit is signed with a GPG key, others can use your public key to confirm that the commit truly came from you and was not tampered with.

---

## What Are SSH Keys?

**SSH (Secure Shell)** keys are primarily used to:

* Authenticate secure connections to remote servers
* Push and pull repositories without entering credentials repeatedly

GitHub also supports using SSH keys to **sign commits**, which is a newer feature.

---

## Generating a GPG Key

To generate a GPG key, run:

gpg --full-generate-key

You will be prompted to choose options and set a passphrase. Using a passphrase is optional but strongly recommended.

---

## Generating an SSH Key

To generate an SSH key, run:

ssh-keygen -t ed25519 -C "[your_email@example.com](mailto:your_email@example.com)"

Make sure to use your real email address. You will also be asked to set a passphrase for additional security.

---

## SSH Key Files

SSH keys generate two files:

* **Private key** (no extension)
* **Public key** (ends with `.pub`)

These files are stored in the `~/.ssh` directory. Only the public key should ever be shared.

---

## Listing and Exporting GPG Keys

To list your GPG keys and get the key ID:

gpg --list-secret-keys --keyid-format=long

To export your public GPG key:

gpg --armor --export "<key id>"

The public key is uploaded to GitHub, not the private key.

---

## Signing Commits with a GPG Key

After uploading your public GPG key to GitHub, configure Git to use it:

git config --global user.signingkey <your_gpg_key_id>

To sign a single commit:

git commit -S -m "message"

To automatically sign all commits:

git config --global commit.gpgsign true

---

## Signing Commits with an SSH Key

To sign commits using an SSH key:

1. Upload your public SSH key to GitHub
2. Set Git to use SSH signing format:

git config --global gpg.format ssh

3. Configure the signing key using the file path:

git config --global user.signingkey <path_to_your_ssh_key>

4. Enable automatic signing if desired

---

## Verified Commits

Once SSH or GPG signing is configured, your commits will appear as **verified** on GitHub and display a verification badge. This improves trust and security in collaborative projects.

---

## Summary

SSH and GPG keys provide secure authentication and commit verification in Git. Private keys remain on your machine, while public keys are shared with GitHub. With proper setup, you can securely push code and create verified commits that confirm your identity and protect your work.
