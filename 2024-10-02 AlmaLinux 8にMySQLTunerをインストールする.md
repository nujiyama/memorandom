# AlmaLinux 8にMySQLTunerをインストールする

[major/MySQLTuner-perl: MySQLTuner is a script written in Perl that will assist you with your MySQL configuration and make recommendations for increased performance and stability.](https://github.com/major/MySQLTuner-perl)

```
$ wget http://mysqltuner.pl/ -O mysqltuner.pl
$ wget https://raw.githubusercontent.com/major/MySQLTuner-perl/master/basic_passwords.txt -O basic_passwords.txt
$ wget https://raw.githubusercontent.com/major/MySQLTuner-perl/master/vulnerabilities.csv -O vulnerabilities.csv
$ chmod +x mysqltuner.pl
$ ./mysqltuner.pl --help | head
```
