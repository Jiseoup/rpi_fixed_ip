# Raspberry Pi Fixed IP Allocation
This document describes how to allocate a fixed IP to `Raspberry pi`.

Used Model : Raspberry Pi 3 Model B+  
<img src="/img/rpi.jpg" width="50%" height="50%"/>

## 1. Check the ip address
```bash
$ ifconfig
```

## 2. Modify network settings file
```bash
$ sudo vim /etc/dhcpcd.conf
```

### Edit here from a file
* Note : eth0(wired) / wlan0(wireless)
```bash
# Example static IP configuration:
interface wlan0
static ip_address=192.168.1.49    # Your ip address
#static ip6_address=fd51:42f8:caae:d92e::ff/64
static routers=192.168.1.1        # Your gateway address
static domain_name_servers=192.168.1.1 8.8.8.8 fd51:42f8:caae:d92e::1
static netmask=255.255.255.0
```

## 3. Reboot the network
```bash
$ sudo /etc/init.d/networking restart
```

## 4. Reboot the Raspberry pi
```bash
$ sudo reboot
```

## 5. Check the ip address again
```bash
$ ifconfig
```
