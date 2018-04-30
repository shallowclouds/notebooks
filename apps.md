#### mysql

```bash
$ sudo apt-get install mysql-server mysql-client
```

#### shadowsocks-libev

```bash
$ sudo apt-get install software-properties-common	 	 
$ sudo add-apt-repository ppa:max-c-lv/shadowsocks-libev
$ sudo apt-get update
$ sudo apt-get install shadowsocks-libev
$ sudo systemctl start/stop/restart shadowsocks-libev.service
```

#### golang

```bash
# $ tar -C /usr/local -xzf go$VERSION.$OS-$ARCH.tar.gz
$ sudo apt-get update
$ sudo apt-get install golang-go
# add to /etc/profile
export PATH=$PATH:/usr/local/go/bin
export GOPATH=/home/gopath
export PATH="$GOPATH/bin:$PATH"

$ export PATH=$PATH:/usr/local/go/bin
```

#### beego

```bash
$ go get -u github.com/astaxie/beego
$ go get -u github.com/beego/bee
```

