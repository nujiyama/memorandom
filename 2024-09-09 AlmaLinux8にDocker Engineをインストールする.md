# AlmaLinux 8にDocker Engineをインストールする

ここではWSL2上のAlmaLinux 8に対してDocker Engineをインストールする。

## WSLでsystemdを有効化する

WSLのAlmaLinuxではデフォルトだとsystemctlコマンドが使えないので、使えるようにsystemdを有効化する。  
もちろんWSLでなければこれは不要。

参考：  
[systemd を使用して WSL で Linux サービスを管理する | Microsoft Learn](https://learn.microsoft.com/ja-jp/windows/wsl/systemd)


```
$ sudo vi /etc/wsl.conf
```

wsl.confファイルに以下を記述する。

```ini
[boot]
systemd=true
```

wsl.confファイルを保存したら、WindowsからWSLをシャットダウンする。

```
> wsl --shutdown
```

シャットダウン後、WSLのAlmaLinuxを起動してsystemctlコマンドが実行できることを確認する。

```
$ systemctl list-unit-files --type=service
```

## docker-ceリポジトリを追加する

以降参考：  
[Install Docker Engine on RHEL | Docker Docs](https://docs.docker.com/engine/install/rhel/)

```
$ sudo dnf config-manager --add-repo https://download.docker.com/linux/rhel/docker-ce.repo
```

## Docker Engineをインストールする

`Hello from Docker!`が出力されればOK。

```
$ sudo dnf install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
$ sudo systemctl start docker
$ sudo docker run hello-world
```

## dockerサービスの自動起動を有効化する

以降参考：  
[Linux post-installation steps for Docker Engine | Docker Docs](https://docs.docker.com/engine/install/linux-postinstall/)

```
$ sudo systemctl enable docker
$ sudo systemctl enable containerd
```

## 非rootユーザーがdockerを管理できるようにする

```
$ sudo usermod -aG docker $USER
```

非rootユーザーで再ログイン後、dockerの実行を確認する。  
`Hello from Docker!`が出力されればOK。

```
$ docker run hello-world
```
