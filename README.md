# Installation

## References
- https://gist.github.com/jsclifford/ec47b07e4c5191c00ca7cd7551327503

## Steps on Machine
- Setup WSL
  - `wsl -install`
- Install Docker as personal install after WSL is setup.
- Install coco
- Upgrade to latest PowerShell
- Install real winget (see below)
- Install Posh-Git
  - Add to all profiles: `Install-Module posh-git -Scope CurrentUser -Force`
- Add new SSH key to GitHub: https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent#platform-windows
- Add WTW Certificate to WSL: 
Use oh-my-zsh setup guide in Wiki to install

### Install Active Directory Users and Computers
```
Add-WindowsCapability -Online -Name Rsat.ActiveDirectory.DS-LDS.Tools~~~~0.0.1.0
Install-WindowsFeature RSAT-AD-PowerShell
```

## Steps in WSL
- Update distro: `sudo apt update && sudo apt upgrade -y`
- Setup Oh My Zsh (install first so the evals are added to .zshrc correctly)
  - https://github.com/ohmyzsh/ohmyzsh
- Install HomeBrew
- Install PowerShell

### Updating to Git repo

```
sudo add-apt-repository ppa:git-core/ppa
sudo apt update; sudo apt install git -y
```

### Add Company Root Certificate

_Example_

<img width="382" height="229" alt="image" src="https://github.com/user-attachments/assets/fe0a78a9-c45d-414d-9786-abfad5a7a6a8" />

```bash
sudo cp /mnt/c/certs/wtw-prod-gp-2028.crt /usr/local/share/ca-certificates/extra/wtw-prod-gp-2028.crt
sudo update-ca-certificates
```

> https://github.com/im-platform/insights-main/blob/main/scripts/corp-laptop-elevated-addons.md#add-internal-root-ca-for-https-proxy--other-internal-certificates-to-ubuntu-linux

## Tools

- Node https://github.com/Schniz/fnm
  - Setup shell integration (see instructions)
- Terraform https://tofuutils.github.io/tenv/
  - Setup shell integration (see instructions)
 
### Real Winget

```bash
#region Install Winget
# get latest download url
$URL = "https://api.github.com/repos/microsoft/winget-cli/releases/latest"
$URL = (Invoke-WebRequest -Uri $URL).Content | ConvertFrom-Json |
        Select-Object -ExpandProperty "assets" |
        Where-Object "browser_download_url" -Match '.msixbundle' |
        Select-Object -ExpandProperty "browser_download_url"
# download
Invoke-WebRequest -Uri $URL -OutFile "Setup.msix" -UseBasicParsing
# install
Add-AppxPackage -Path "Setup.msix"
# delete file
Remove-Item "Setup.msix"

winget --version

# Fix winget sources.
Add-AppxPackage -Path https://cdn.winget.microsoft.com/cache/source.msix
#endregion
```
