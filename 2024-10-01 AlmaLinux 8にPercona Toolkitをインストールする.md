# AlmaLinux 8にPercona Toolkitをインストールする

```
$ sudo dnf install https://repo.percona.com/yum/percona-release-latest.noarch.rpm
$ sudo percona-release setup pt
$ sudo dnf install percona-toolkit
$ pt-query-digest --version
```

pt-query-digestしか使ったことがない…
