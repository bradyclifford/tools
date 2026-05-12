Reference https://gist.github.com/jsclifford/ec47b07e4c5191c00ca7cd7551327503

- Install Docker as personal install after WSL is setup.
- In Powershell, Node https://github.com/jasongin/nvs
Install Posh-Git
Add new SSH key to GitHub: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#platform-windows
Add WTW Certificate to WSL: https://github.com/im-platform/insights-main/blob/main/scripts/corp-laptop-elevated-addons.md#add-internal-root-ca-for-https-proxy--other-internal-certificates-to-ubuntu-linux
Use oh-my-zsh setup guide in Wiki to install

# Symbolic Links

Add to user path:
```
ln -s "$(pwd)/dev-login.sh" ~/bin/ffm-dev-login
``

# Search Text
```
tail file.log -f | grep pattern
```

https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/4/html/Step_by_Step_Guide/s1-viewingtext-terminal.html

