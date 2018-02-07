```bash
$ git config --global user.name "xuhaiyan"
$ git config --global user.email "email"
$ ssh-keygen -t rsa -C “email”
```

```bash
$ pip freeze > ./requirements.txt
$ pip install -r path/requirements.txt 
```

```bash
$ apt-get install chromium-browser

```

vultr1098, spider1234,

```bash
$ apt-get install GConf-2.4
```

install chrome for ubuntu

```bash
$ wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
$ echo 'deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main' | sudo tee /etc/apt/sources.list.d/google-chrome.list
$ sudo apt-get update 
$ sudo apt-get install google-chrome-stable
```

```bash
$ sudo apt-get install xvfb
$ export DISPLAY=:10
```

remoteforspidermysql,233

If you are using `ubuntu`, you have to use the following steps to avoid this error:

1. run the command `vim /etc/mysql/my.cnf`
2. comment `bind-address = 127.0.0.1` using the # symbol
3. restart your mysql server once.
4. In Step 1, if you cannot find `bind-address` in the `my.cnf` file, look for it in `/etc/mysql/mysql.conf.d/mysqld.cnf` file.



1. \#给用户cacti赋予所有库的所有权限  
2. GRANT ALL PRIVILEGES ON *.* TO 'cacti'@'%' IDENTIFIED BY 'cacti' WITH GRANT OPTION;  
3. \#重新载入赋权表  
4. FLUSH PRIVILEGES;  
5.   
6. \#收回权限(不包含赋权权限)  
7. REVOKE ALL PRIVILEGES ON *.* FROM cacti;  
8. REVOKE ALL PRIVILEGES ON cacti.* FROM cacti;  
9. \#收回赋权权限  
10. REVOKE GRANT OPTION ON *.* FROM cacti;  
11. \#重新载入赋权表  
12. FLUSH PRIVILEGES;  