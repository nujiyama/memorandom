# AlmaLinux 8にPython3をインストールする

確認した環境。

```bash
$ cat /etc/redhat-release
AlmaLinux release 8.10 (Cerulean Leopard)
$
```

## インストール

使用可能なバージョンを確認する。

```bash
$ dnf search python3 | grep -E '^python3[\.0-9]+\.x86_64'
Last metadata expiration check: 0:22:21 ago on Mon Oct 21 18:43:23 2024.
python3.11.x86_64 : Version 3.11 of the Python interpreter
python3.12.x86_64 : Version 3.12 of the Python interpreter
python36.x86_64 : Interpreter of the Python programming language
python38.x86_64 : Interpreter of the Python programming language
python39.x86_64 : Version 3.9 of the Python interpreter
$
```

インストールする。

```bash
$ sudo dnf install -y python3.12 python3.12-pip
```

確認。

```bash
$ python3 -V
Python 3.12.5
$ which python3
/usr/bin/python3
$ ls -l /usr/bin/python*
lrwxrwxrwx 1 root root   25 Oct 21 19:08 /usr/bin/python3 -> /etc/alternatives/python3
-rwxr-xr-x 1 root root 7752 Sep 24 03:17 /usr/bin/python3.12
$
$
$
$ pip3 -V
pip 23.2.1 from /usr/lib/python3.12/site-packages/pip (python 3.12)
$ which pip3
/usr/bin/pip3
$ ls -l /usr/bin/pip*
lrwxrwxrwx 1 root root  23 Oct 21 19:20 /usr/bin/pip-3 -> /etc/alternatives/pip-3
lrwxrwxrwx 1 root root   9 Apr  8  2024 /usr/bin/pip-3.12 -> ./pip3.12
lrwxrwxrwx 1 root root  22 Oct 21 19:20 /usr/bin/pip3 -> /etc/alternatives/pip3
-rwxr-xr-x 1 root root 224 Apr  8  2024 /usr/bin/pip3.12
$
```

## 疑問

dnf module listだとpython3.11、python3.12が出力されないのはなぜか？

```bash
$ dnf module list python3*
Last metadata expiration check: 0:29:17 ago on Mon Oct 21 18:43:23 2024.
AlmaLinux 8 - AppStream
Name                 Stream             Profiles                     Summary
python36             3.6 [d]            build, common [d]            Python programming language, version 3.6
python38             3.8 [d]            build, common [d]            Python programming language, version 3.8
python39             3.9 [d]            build, common [d]            Python programming language, version 3.9

Hint: [d]efault, [e]nabled, [x]disabled, [i]nstalled
$
```
