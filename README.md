This PoC of Old Plain Runtime in Docker (OPRID)

Quick how to:

```
mkdir devs
cd devs
git clone https://github.com/rjsocha/oprid-runtime.git
mkdir www
cd oprid-runtime
docker-compose up -d
cd ..
cd www
mkdir -p example.vhost/public
```

Other options:

Create configuration for Laravel project (vhost name will be example2.vhost)
```
mkdir -p example2.vhost.laravel/public
```

DNS

Manual:
```
#Add entry to /etc/hosts
127.0.0.1 example2.vhost example.vhost
```

Automatic DNS on Linux:
```
# Enable OPRID DNS support
sudo mv /etc/resolv.conf /etc/resolv.conf.oprid

# Disable OPRID DNS support
sudo mv /etc/resolv.conf.oprid /etc/resolv.conf
```

Automatic DNS on Mac OS X:

In System Prefrences->Network->Advanced->DNS (for current connection for ex: Ethernet or Wi-Fi)
Add new nameserver to the list (as first entry).
