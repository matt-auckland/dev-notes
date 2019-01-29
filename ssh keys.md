# Generate an SSH key

## Generate

- Open Terminal.

- Paste the text below, substituting in your GitHub email address.

```ssh-keygen -t rsa -b 4096 -C "your_email@example.com"```

- This creates a new ssh key, using the provided email as a label.

- Generating public/private rsa key pair.

- When you're prompted to `Enter a file in which to save the key,` press Enter. This accepts the default file location.

- Enter a file in which to save the key ```(/Users/you/.ssh/id_rsa): [Press enter]```

- At the prompt, type a secure passphrase. For more information, see `Working with SSH key passphrases`.

- Enter passphrase (empty for no passphrase): [Type a passphrase]
- Enter same passphrase again: [Type passphrase again]



## Add key to the ssh-agent



    Start the ssh-agent in the background.
```
    eval "$(ssh-agent -s)"
    Agent pid 59566
```
    If you're using macOS Sierra 10.12.2 or later, you will need to modify your ~/.ssh/config file to automatically load keys into the ssh-agent and store passphrases in your keychain.
```
    Host *
     AddKeysToAgent yes
     UseKeychain yes
     IdentityFile ~/.ssh/id_rsa
```
    Add your SSH private key to the ssh-agent and store your passphrase in the keychain. If you created your key with a different name, or if you are adding an existing key that has a different name, replace id_rsa in the command with the name of your private key file.

    ```ssh-add -K ~/.ssh/id_rsa```

    Note: The -K option is Apple's standard version of ssh-add, which stores the passphrase in your keychain for you when you add an ssh key to the ssh-agent.

    If you don't have Apple's standard version installed, you may receive an error. For more information on resolving this error, see "Error: ssh-add: illegal option -- K."

    Add the SSH key to your GitHub account.



## Add the key to Github
`sudo apt-get install xclip`

`xclip -target ~/.ssh/id_rsa.pub -target clipboard`