# Docker Build Envrionment for Debian 10 - Buster

Build and get deb files

```
$ docker build -t rtpengine:build .
$ docker create --name rtpengine-build rtpengine:build
$ docker cp rtpengine-build:/opt/deb .
```

Install RTPengine

Copy deb files to host machine and then:

```
$ sudo dpkg -i ngcp-rtpengine-daemon_*.deb
$ sudo apt-get install -f
$ sudo dpkg -i ngcp-rtpengine-recording-daemon_*.deb
$ sudo apt-get install -f
$ sudo dpkg -i ngcp-rtpengine-utils_*.deb
$ sudo apt-get install -f
$ sudo dpkg -i ngcp-rtpengine-iptables_*.deb
$ sudo apt-get install -f
$ sudo dpkg -i ngcp-rtpengine-kernel-dkms_*.deb
$ sudo dpkg -i ngcp-rtpengine_*.deb
```

(Running apt-get install -f repeatedly is to add any missing dependancies)
