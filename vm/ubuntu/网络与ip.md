
ping: www.baidu.com: Temporary failure in name resolution
vim /etc/resolv.conf

## 添加如下内容：
nameserver 8.8.8.8

## 远程登陆 远程失败  远程登录失败
```shell
su root
apt-get install openssh-server
# 将/etc/ssh/sshd_config文件中的PermitRootLogin prohibit-password注释掉，
# 然后加上本段代码：
echo PermitRootLogin yes >> /etc/ssh/sshd_config
# 设置完成后重新启动SSH服务
sudo service ssh restart
```

## g++ not found
```shell
apt-get install build-essential
```

## 虚拟机使用的是此版本 VMware Workstation 不支持的硬件版本。  模块“Upgrade”启动失败。  未能启动虚拟机。
找到xxx.vmx
修改19 -> 16版本
virtualHW.version = "16"

```shell
sudo nano /etc/netplan/00-installer-config.yaml
```
### 设置ip
此时vm NAT设置网关ip是192.168.0.2
完成更改后，按CTRL + X保存文件，然后输入Y以确认要保存更改。
使用以下命令将新配置应用于系统:
```yaml
network:
  version: 2
  renderer: NetworkManager
  ethernets:
    ens33:
      dhcp4: false
      addresses: [192.168.0.131/24]
      optional: true
      routes:
        - to: default
          via: 192.168.0.2
      nameservers:
        addresses: [8.8.8.8]
```

```shell
sudo netplan apply
```