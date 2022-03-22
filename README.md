# WSL-2-New-Features

### WSL 2 Windows 10 下目录
```sh
\\wsl$\Ubuntu\
```
### Windows 下先备份，修改 WSL 2 Windows 10 下文件并保存
```sh
"\\wsl$\Ubuntu\etc\apt\sources.list"
```
内容修改为
```
deb https://mirrors.aliyun.com/debian/ bullseye main non-free contrib
deb-src https://mirrors.aliyun.com/debian/ bullseye main non-free contrib
deb https://mirrors.aliyun.com/debian-security/ bullseye-security main
deb-src https://mirrors.aliyun.com/debian-security/ bullseye-security main
deb https://mirrors.aliyun.com/debian/ bullseye-updates main non-free contrib
deb-src https://mirrors.aliyun.com/debian/ bullseye-updates main non-free contrib
deb https://mirrors.aliyun.com/debian/ bullseye-backports main non-free contrib
deb-src https://mirrors.aliyun.com/debian/ bullseye-backports main non-free contrib
```

### 回到 WSL 2 执行如下命令报错
```sh
sudo  apt-get update
```
报错如下：
```sh
Err:2 https://mirrors.aliyun.com/debian-security bullseye-security InRelease
  The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 112695A0E562B32A NO_PUBKEY 54404762BBB6E853
```
修复命令如下：
```sh
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 112695A0E562B32A
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 54404762BBB6E853
```
