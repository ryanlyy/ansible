yum install -y epel-release
yum update
ln -s /usr/share/zoneinfo/Asia/Shanghai /etc/localtime
systemctl stop firewalld
systemctl disable firewalld
systemctl restart chrony
hwclock --systohc

# uncomment this to disable SSH key host checking (/etc/ansible/ansible.cfg)
host_key_checking = False

