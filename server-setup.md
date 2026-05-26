# Initial Server Setup

This guide installs the essential packages and tools required for running crypto nodes on Ubuntu VPS servers.

---

# Update Server Packages

Before installing anything, update your server packages:

```bash
sudo apt-get update && sudo apt-get upgrade -y
```

---

# Install Main Packages

These packages are commonly required for crypto nodes and Linux utilities.

```bash
sudo apt install curl screen iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev ca-certificates -y
```

---

# Install Python3 & Pip

```bash
sudo apt install -y python3-pip
sudo apt install pip
sudo apt install -y build-essential libssl-dev libffi-dev python3-dev
```

Check version:

```bash
python3 --version
pip --version
```

---

# Install Go

```bash
sudo rm -rf /usr/local/go

curl -L https://go.dev/dl/go1.22.3.linux-amd64.tar.gz | sudo tar -xzf - -C /usr/local

echo 'export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin' >> $HOME/.bash_profile

source .bash_profile

go version
```

---

# Install NodeJS, npm, Yarn

Check current version:

```bash
node --version
```

If NodeJS 18 is already installed, skip this section.

Remove old NodeJS files:

```bash
sudo apt-get remove nodejs
sudo apt-get purge nodejs
sudo apt-get autoremove

sudo rm /etc/apt/keyrings/nodesource.gpg
sudo rm /etc/apt/sources.list.d/nodesource.list
```

Install NodeJS 18:

```bash
sudo apt-get update

curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -

sudo apt install -y nodejs
```

Check versions:

```bash
node -v
npm -v
```

Install npm:

```bash
sudo apt-get install npm
npm --version
```

Install Yarn:

```bash
curl -sSL https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -

echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

sudo apt-get update -y

sudo apt-get install yarn -y
```

---

# Install Docker & Docker Compose

Remove old Docker packages:

```bash
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done
```

Install Docker dependencies:

```bash
sudo apt-get update

sudo apt-get install ca-certificates curl gnupg

sudo install -m 0755 -d /etc/apt/keyrings
```

Add Docker GPG key:

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

Add Docker repository:

```bash
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

Install Docker:

```bash
sudo apt update -y && sudo apt upgrade -y

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

Test Docker:

```bash
sudo docker run hello-world
```

---

# lsof & UFW Commands

Check used ports:

```bash
lsof -i -P -n | grep LISTEN
```

Check process using port 80:

```bash
lsof -i :80
```

Open a port:

```bash
sudo ufw allow <port>
```

Example:

```bash
sudo ufw allow 3000
```

---

# Install htop

Monitor CPU, RAM, tasks, and system usage.

Install:

```bash
sudo apt install htop
```

Run:

```bash
htop
```
