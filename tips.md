## install chrome for ubuntu

```bash
$ wget -q -O - https://dl-ssl.google.com/linux/linux_signing_key.pub | sudo apt-key add -
$ echo 'deb [arch=amd64] http://dl.google.com/linux/chrome/deb/ stable main' | sudo tee /etc/apt/sources.list.d/google-chrome.list
$ sudo apt-get update 
$ sudo apt-get install google-chrome-stable
```

## mysql remote login

If you are using `ubuntu`, you have to use the following steps to avoid this error:

1. run the command `vim /etc/mysql/my.cnf`
2. comment `bind-address = 127.0.0.1` using the # symbol
3. restart your mysql server once.
4. In Step 1, if you cannot find `bind-address` in the `my.cnf` file, look for it in `/etc/mysql/mysql.conf.d/mysqld.cnf` file.



1. 给用户 username 赋予所有库的所有权限  
```bash
GRANT ALL PRIVILEGES ON *.* TO 'username'@'%' IDENTIFIED BY 'username' WITH GRANT OPTION;  
```
2. 重新载入赋权表  
```
FLUSH PRIVILEGES;
```
3. 收回权限(不包含赋权权限)  
```bash
REVOKE ALL PRIVILEGES ON *.* FROM username;
REVOKE ALL PRIVILEGES ON username.* FROM username;
```
4. 收回赋权权限
```bash  
REVOKE GRANT OPTION ON *.* FROM username;
```
5. 重新载入赋权表  
```bash
FLUSH PRIVILEGES;
```

## python packages
```bash
$ pip freeze > ./requirements.txt
$ pip install -r path/requirements.txt 
```
