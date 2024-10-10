# Python仮想環境（venv）を使用する

参考：  
[仮想環境: Python環境構築ガイド - python.jp](https://www.python.jp/install/macos/virtualenv.html)

## プロジェクトの初期化

```bash
$ mkdir myproject
$ cd myproject/
$ python3 -m venv .venv
$ echo ".venv/" >> .gitignore
```

## 仮想環境の有効化

```bash
$ source .venv/bin/activate
```

## パッケージのインストール

```bash
(.venv) $ pip install requests
(.venv) $ pip freeze > requirements.txt
```

## 既存のrequirements.txtからパッケージをインストール

```bash
(.venv) $ pip install -r requirements.txt
```

## 仮想環境の無効化

```bash
(.venv) $ deactivate
```
