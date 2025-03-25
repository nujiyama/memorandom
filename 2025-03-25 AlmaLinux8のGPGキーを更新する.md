# AlmaLinux8のGPGキーを更新する

古めの AlmaLinux 8（8.8-3.el8 より前）で `dnf install` したときに「エラー: GPG の確認に失敗しました」とかなるやつ、AlmaLinux で障害があってパッケージの署名に使っている GPG キーが使えなくなったことが原因。
[AlmaLinux OS - Forever-Free Enterprise-Grade Operating System](https://almalinux.org/blog/2023-12-20-almalinux-8-key-update/)

新しい GPG キーをインポートすれば解消する。

```shell
dnf clean all
rpm --import https://repo.almalinux.org/almalinux/RPM-GPG-KEY-AlmaLinux
```
