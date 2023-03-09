# wsl2-proxy
wsl2 Ubuntu 22.04 使用 windows 物理机代理的自动设置脚本

## 使用方法

```shell
chmod u+x proxy.sh # 为代理设置脚本 proxy.sh 添加执行权限

./proxy.sh set # 设置代理
./proxy.sh unset # 取消代理
./proxy.sh test # 测试代理是否可用
```

## 更好的使用方法

1. 将 `proxy.sh` 保存的自己用户目录下的可执行文件目录（我这里设置的目录名为 `~/.hbin`）下，并将该可执行文件目录添加到用户环境变量中；
2. 向 `.bashrc`、`.zshrc` 等用户登录执行脚本添加 `~/.hbin/proxy.sh set`，实现每次登录终端自动设置代理

```shell
git clone https://github.com/HuberWong/wsl2-proxy.git # 克隆本项目
cp ./wsl2-proxy/proxy.sh ~/.hbin/ # 记得将 .hbin 改成自己设置的可执行文件目录名称
cd ~/.hbin # 记得将 .hbin 改成自己设置的可执行文件目录名称

chmod u+x 为 proxy.sh # 文件添加可执行权限

# 在 .bashrc .zshrc 等用户登录执行脚本中添加如下内容
export PATH=$HOME/.hbin/:$PATH # 将自己的可执行文件目录添加到用户环境变量，记得将 .hbin 改成自己设置的可执行文件目录名称
~/.hbin/proxy.sh set # 每次启动终端都自动执行 proxy.sh 脚本

```
