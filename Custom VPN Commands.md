### Commands



##### \##Instance1



\#update ubuntu instance

sudo apt-get update 



\#install easy-rsa

sudo apt-get install easy-rsa -y



\#create certificate authority directory

make-cadir ~/easy-rsa

cd ~/easy-rsa





\# Initializing the easyrsa

./easyrsa init-pki

./easyrsa build-ca  # Press Enter for defaults, no password for simplicity

./easyrsa gen-req server nopass

./easyrsa sign-req server server

./easyrsa gen-dh

./easyrsa gen-req client nopass

./easyrsa sign-req client client



##### \##launch new instance 



\#install OpenVPN

sudo apt-get install OpenVPN -y



\#generate ta key

openvpn --genkey tls-auth ta.key



\#create server configuration file

sudo vi /etc/openvpn/server.conf



\#IP forwarding

sudo sysctl -w net.ipv4.ip\_forward=1



\#change to root user

sudo su



\#write the IP forwarding in sysctl configuration file

sudo echo "net.ipv4.ip\_forward = 1" >> /etc/sysctl.conf



\#creating IP Tables

sudo iptables -t nat -A POSTROUTING -s 172.31.0.0/24 -o ens5 -j MASQUERADE



\#Allow uwf firewall for udp

sudo ufw allow 1194/udp



\#Allow uwf firewall for OpenSSH

sudo ufw allow OpenSSH



\#Enable uwf firewall

sudo ufw enable



\# Edit the before.rules file by adding NAT rules before the \*filter section:

vi /etc/ufw/before.rules



\#Update /etc/default/ufw to set DEFAULT\_FORWARD\_POLICY="ACCEPT"

vi /etc/default/ufw



\#start OpenVPN server

sudo systemctl start openvpn@server # if it gets error msg



\#change the permission

sudo chown ubuntu /etc/OpenVPN 



\#start OpenVPN server

sudo systemctl start openvpn@server



\#enable OpenVPN server

sudo systemctl enable openvpn@server



\#check server status

sudo systemctl status openvpn@server



