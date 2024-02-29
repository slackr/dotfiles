# Install

```
# docker-ce repos
printf '%s\n' "deb https://download.docker.com/linux/debian bookworm stable" |
  sudo tee /etc/apt/sources.list.d/docker-ce.list

curl -fsSL https://download.docker.com/linux/debian/gpg |
  sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/docker-ce-archive-keyring.gpg

# ms code repos
sudo apt-get install wget gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg
sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'
rm -f packages.microsoft.gpg

sudo apt update

sudo apt install apt-transport-https
sudo apt install code # or code-insiders
sudo apt install -y docker-ce docker-ce-cli containerd.io

# copy dotfiles into $HOME
cp -r . ~/

# maybe?
sudo apt install -y kali-desktop-gnome



