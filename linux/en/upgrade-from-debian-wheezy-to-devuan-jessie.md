
# upgrade how to

## Prepare the upgrade

## disable the Debian repositories

* move old sources lists into old-debian directory
```
# mkdir /etc/apt/sources.list.d/old-debian
# mv /etc/apt/sources.list.d/* /etc/apt/sources.list.d/old-debian/
```

## setup the Devuan repositories

* edit source list / create a new jessie.list for devuan/jessie
```
# touch /etc/apt/sources.list.d/jessie.list
# chmod a+r /etc/apt/sources.list.d/jessie.list
# editor /etc/apt/sources.list.d/jessie.list
deb http://auto.mirror.devuan.org/merged jessie          main contrib non-free
deb http://auto.mirror.devuan.org/merged jessie-updates  main contrib non-free
deb http://auto.mirror.devuan.org/merged jessie-security main contrib non-free
```

## Disable config done to stay on wheezy, allow to move on jessie

* disable pinning
```
# mv /etc/apt/preferences.d/wheezy.pref{,.disabled}
```

* disable default release
```
# editor /etc/apt/apt.conf.d/default-release.conf
```
prefix line by //


```
# apt-get update
```

## install the devuan keyring

```
# apt-get install devuan-keyring
```
confirme with 'y'

## make an first upgrade

Simulation, download ...

```
# apt-get upgrade -s
# apt-get upgrade -dy
...
Fetched 396 MB in 4min 47s (1,378 kB/s)
```

```
# apt-get dist-upgrade -dy  // apt-get dist-upgrade -s
...
Calculating upgrade... Failed
The following packages have unmet dependencies:
 modemmanager : Breaks: network-manager (< 0.9.8.2-1) but 0.9.4.0-10 is to be installed
 network-manager-gnome : Depends: network-manager (>= 0.9.10) but 0.9.4.0-10 is to be installed
E: Error, pkgProblemResolver::Resolve generated breaks, this may be caused by held packages.
```

``` 
# screen
# apt-get upgrade 
[...long processing...]
```

The upgrade is ended.

## fix dist-upgrade issue

```
# apt-get purge -s modemmanager
The following packages will be REMOVED:
  modemmanager*
0 upgraded, 0 newly installed, 1 to remove and 881 not upgraded.
Purg modemmanager [0.5.2.0-2]
```

```
# apt-get purge modemmanager
The following packages will be REMOVED:
  modemmanager*
0 upgraded, 0 newly installed, 1 to remove and 881 not upgraded.
After this operation, 1,134 kB disk space will be freed.
Do you want to continue [Y/n]? 
y
```

```
# apt-get purge -s network-manager-gnome
# apt-get purge network-manager-gnome

# apt-get purge ppp

# apt-get purge network-manager
```

Issues fixed.

##

```
# apt-get dist-upgrade -s
```
success

```
# apt-get dist-upgrade -dy
```

```
# apt-get dist-upgrade
```


## kernel + headers

```
# apt-cache search linux-image-3 |grep 686 |grep pae |grep -v dbg
```

```
# apt-get install linux-image-3.16.0-4-686-pae linux-headers-3.16.0-4-686-pae
```

## non-free amd/ati driver

See https://wiki.debian.org/fr/ATIProprietary#Debian_8_.2BAKs_Jessie_.2BALs-

```
# apt-get install fglrx-driver fglrx-modules-dkms
```


See https://wiki.debian.org/fr/ATIProprietary#configure

```
# mkdir /etc/X11/xorg.conf.d
# editor /etc/X11/xorg.conf.d/20-fglrx.conf
Section "Device"
	Identifier "My GPU"
	Driver "fglrx"
EndSection
```



