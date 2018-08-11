# cloud-config-dev
RancherOS Cloud Config virtual DEV.

File base config VirualBox create for *[RancerOS.iso](https://github.com/rancher/os/releases/)*

#### Config manual for console after install in new VM

``` bash
$ sudo ros config set rancher.network.dns.nameservers "['192.168.1.210','192.168.1.211','8.8.8.8','8.8.4.4']"
$ sudo ros config set rancher.network.dns.search "['mydomain.com']"
$ sudo ros config set rancher.network.interfaces.eth0.address 192.168.1.219/24
$ sudo ros config set rancher.network.interfaces.eth0.gateway 192.168.1.254
$ sudo ros config set rancher.network.interfaces.eth0.dhcp false
$ sudo ros config validate -i /var/lib/rancher/config/cloud-config.yml
$ sudo ros install -c /var/lib/rancher/config/cloud-config.yml -d /dev/sda)
$ Reboot Y/N..? Yes
```

Doc info install: https://rancher.com/docs/os/v1.2/en/running-rancheros/server/install-to-disk/

Doc info cloud config: https://rancher.com/docs/os/v1.2/en/configuration/

#### Show config RancherOS 

```
$ sudo ros config export
```

#### Change Ip manual

```
$ sudo ip addr add 172.20.74.148/24 dev eth0
$ sudo route add default gw 172.20.74.254
```

#### Stop and Delete all container run
```
$ docker rm -f $(docker ps -qa)
```

#### Shell Container Run
```
docker exec -i -t 665b4a1e17b6 /bin/bash
```
