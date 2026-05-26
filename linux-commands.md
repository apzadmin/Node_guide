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
mkdir moei
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
cd moei
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
git clone https://github.com/0xmoei/Linux_Node_Gu
