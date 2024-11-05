# PHP PDOでMySQLサーバーへの接続確認をするワンライナー

なぜか、mysqlコマンドはないけどphpはあるホストでMySQLサーバーへの接続確認をしたい時がある。

```bash
php -r 'new PDO("mysql:host=対象ホスト;dbname=対象DB", "MySQLユーザー", "MySQLユーザーのパスワード"); echo "接続成功\n";'
```
