# راه‌اندازی اولیه سرور

این راهنما ابزارها و پکیج‌های ضروری برای ران کردن نودهای کریپتویی روی سرور Ubuntu را نصب می‌کند.

---

# آپدیت پکیج‌های سرور

قبل از نصب هر چیزی، پکیج‌های سرور را آپدیت کنید:

```bash
sudo apt-get update && sudo apt-get upgrade -y
```

---

# نصب پکیج‌های اصلی

این پکیج‌ها معمولاً برای نودها و ابزارهای لینوکسی موردنیاز هستند:

```bash
sudo apt install curl screen iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev ca-certificates -y
```

---

# نصب Python3 و Pip

```bash
sudo apt install -y python3-pip
sudo apt install pip
sudo apt install -y build-essential libssl-dev libffi-dev python3-dev
```

بررسی نسخه:

```bash
python3 --version
pip --version
```

---

# نصب Go

```bash
sudo rm -rf /usr/local/go

curl -L https://go.dev/dl/go1.22.3.linux-amd64.tar.gz | sudo tar -xzf - -C /usr/local

echo 'export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin' >> $HOME/.bash_profile

source .bash_profile

go version
```

---

# نصب NodeJS ، npm و Yarn

بررسی نسخه فعلی:

```bash
node --version
```

اگر NodeJS 18 نصب بود، این بخش را رد کنید.

حذف نسخه‌های قدیمی NodeJS:

```bash
sudo apt-get remove nodejs
sudo apt-get purge nodejs
sudo apt-get autoremove

sudo rm /etc/apt/keyrings/nodesource.gpg
sudo rm /etc/apt/sources.list.d/nodesource.list
```

نصب NodeJS 18:

```bash
sudo apt-get update

curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -

sudo apt install -y nodejs
```

بررسی نسخه‌ها:

```bash
node -v
npm -v
```

نصب npm:

```bash
sudo apt-get install npm
npm --version
```

نصب Yarn:

```bash
curl -sSL https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -

echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list

sudo apt-get update -y

sudo apt-get install yarn -y
```

---

# نصب Docker و Docker Compose

حذف نسخه‌های قدیمی Docker:

```bash
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done
```

نصب وابستگی‌های Docker:

```bash
sudo apt-get update

sudo apt-get install ca-certificates curl gnupg

sudo install -m 0755 -d /etc/apt/keyrings
```

اضافه کردن Docker GPG key:

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

اضافه کردن Docker repository:

```bash
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

نصب Docker:

```bash
sudo apt update -y && sudo apt upgrade -y

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```

تست Docker:

```bash
sudo docker run hello-world
```

---

# دستورات lsof و UFW

بررسی پورت‌های فعال:

```bash
lsof -i -P -n | grep LISTEN
```

بررسی پردازشی که از پورت 80 استفاده می‌کند:

```bash
lsof -i :80
```

باز کردن پورت:

```bash
sudo ufw allow <port>
```

مثال:

```bash
sudo ufw allow 3000
```

---

# نصب htop

برای مانیتور کردن CPU، RAM، پردازش‌ها و منابع سیستم.

نصب:

```bash
sudo apt install htop
```

اجرا:

```bash
htop
```
