# enable google bbr on ubuntu 16.04
5715e31e-9f87-4e02-a283-2a46f472faf3

sudo apt update

sudo apt install linux-generic-hwe-16.04

sudo shutdown -r now

sudo modprobe tcp_bbr

echo "tcp_bbr" >> /etc/modules-load.d/modules.conf

echo "net.core.default_qdisc=fq" >> /etc/sysctl.conf

echo "net.ipv4.tcp_congestion_control=bbr" >> /etc/sysctl.conf

sysctl -p

sysctl net.ipv4.tcp_available_congestion_control

sysctl net.ipv4.tcp_congestion_control

lsmod | grep bbr



netch version 181
