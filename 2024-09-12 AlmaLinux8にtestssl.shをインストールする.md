# AlmaLinux8にtestssl.shをインストールする

[/bin/bash based SSL/TLS tester: testssl.sh](https://testssl.sh/)  
ApacheでSSLなんちゃらの設定を確認するのに使う。

```
$ sudo dnf install bind-utils

$ git clone --depth 1 https://github.com/drwetter/testssl.sh.git
$ cd testssl.sh/
$ ./testssl.sh -v
```
