# Installation

## References
- https://gist.github.com/jsclifford/ec47b07e4c5191c00ca7cd7551327503

## Steps on Machine
- Setup WSL
  - `wsl -install`
- Install Docker as personal install after WSL is setup.
- Install coco
- Upgrade to latest PowerShell
- In Powershell, Node https://github.com/jasongin/nvs
Install Posh-Git
Add new SSH key to GitHub: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#platform-windows
Add WTW Certificate to WSL: https://github.com/im-platform/insights-main/blob/main/scripts/corp-laptop-elevated-addons.md#add-internal-root-ca-for-https-proxy--other-internal-certificates-to-ubuntu-linux
Use oh-my-zsh setup guide in Wiki to install

## Steps in WSL
- Update distro: `sudo apt update && sudo apt upgrade -y`
- Install HomeBrew
