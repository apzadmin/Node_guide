# Linux Commands Guide

Basic Linux commands commonly used for VPS servers and crypto node setups.

---

# ls — List Directories

Display files and directories.

## List directories

```bash
ls
```

## List all directories including hidden files

```bash
ls -a
```

---

# mkdir — Create Directories

Create new folders.

## Create a folder

```bash
mkdir <folder-name>
```

## Create multiple folders

```bash
mkdir <folder-name> <folder-name2>
```

## Example

```bash
mkdir shahin
```

---

# cd — Change Directory

Navigate between folders.

## Go to home directory

```bash
cd
```

## Go to a custom directory

```bash
cd <directory-path>
```

## Example

```bash
cd shahin
```

## Go to parent directory

```bash
cd ..
```

---

# mv — Move Files & Directories

Move or rename files and folders.

## Syntax

```bash
mv <source> <destination>
```

---

# rm — Remove Files

Delete files and directories.

## Remove a file

```bash
rm -rf <file>
```

## Remove a file inside a directory

```bash
rm -rf <directory/file>
```

---

# nano — File Editor

Open and edit files directly in terminal.

## Open or create a file

```bash
nano <file>
```

## Save & Exit

```text
CTRL + X → Y → ENTER
```

---

# git — Clone GitHub Repositories

Transfer a GitHub repository into your Linux server.

## Clone repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY
```

## Example

```bash
git clone https://github.com/shahin/linux-node-guide
```

---

# screen — Background Sessions

Screen allows processes to continue running after exiting the terminal or VPS session.

Useful for running crypto nodes in the background.

---

## Install Screen

```bash
sudo apt install screen
```

## Create a new screen

```bash
screen -S <screen-name>
```

## Detach from screen

```text
CTRL + A + D
```

## List active screens

```bash
screen -ls
```

## Reconnect to a screen

```bash
screen -r <screen-name>
```
# Useful Linux Resources

- [101 Linux Commands Open-source eBook](https://github.com/bobbyiliev/101-linux-commands#basics)

- [Linux Bash Commands Repository](https://github.com/trinib/Linux-Bash-Commands)

- [Important Linux Commands Guide](https://www.digitalocean.com/community/tutorials/linux-commands#the-wget-command-in-linux)
