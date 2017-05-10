# digitalocean-init

```bash
#!/bin/bash
USER=<user>
PASSWORD=<password>
adduser $USER --gecos ",,," --disabled-password
echo "$USER:$PASSWORD" | chpasswd
usermod -aG sudo $USER
sed -i 's/PermitRootLogin yes/PermitRootLogin no/g' /etc/ssh/sshd_config
sudo service ssh restart
```
