# Installation

## References
- https://gist.github.com/jsclifford/ec47b07e4c5191c00ca7cd7551327503

## Steps on Machine
- Setup WSL
  - `wsl -install`
- Install Docker as personal install after WSL is setup.
- Install coco
- Upgrade to latest PowerShell
- In Powershell, install Node https://github.com/Schniz/fnm
- In PowerShell, install Terraform https://tofuutils.github.io/tenv/
  - Setup shell integration
Install Posh-Git
Add new SSH key to GitHub: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#platform-windows
Add WTW Certificate to WSL: https://github.com/im-platform/insights-main/blob/main/scripts/corp-laptop-elevated-addons.md#add-internal-root-ca-for-https-proxy--other-internal-certificates-to-ubuntu-linux
Use oh-my-zsh setup guide in Wiki to install

## Steps in WSL
- Update distro: `sudo apt update && sudo apt upgrade -y`

### Add WTW Root Certificate
<img width="382" height="229" alt="image" src="https://github.com/user-attachments/assets/fe0a78a9-c45d-414d-9786-abfad5a7a6a8" />
```bash
sudo cp /mnt/c/certs/wtw-prod-gp-2028.crt /usr/local/share/ca-certificates/extra/wtw-prod-gp-2028.crt
sudo update-ca-certificates
```

- Install HomeBrew
