Packages are provided for Debian (stretch, jessie) and Ubuntu (zesty, xenial)

## Debian

### Packages

- [burstcoincg - Burstcoin wallet powered by CryptoGuru based on MariaDB.](https://github.com/ac0v/burstcoin)
- [creepminer - The creepMiner is a client application for mining Burst on a pool or solo.](https://github.com/Creepsky/creepMiner)

### Quick Install

Copy & Paste this line into your terminal:

```
\wget -q -O - http://package.cryptoguru.org/debian/init.sh | bash
```

and now you can install packages like:

```
apt-get install burstcoincg
```

!!! Info
	The wallet is started automatically after installation.

### Shell Script

The Quick- Install downloads a shell script and executes it directly. If you're really concerned about the argument that it may contain nefarious activities within, you can easily review it before you run it.

```
wget http://package.cryptoguru.org/debian/init.sh
less install.sh
bash install.sh
```

and now you can install packages like:

```
apt-get install burstcoincg
```

### Add to sources

- **stretch**

	Add the following stuff to your sources.list
	```
	deb https://package.cryptoguru.org/debian/stretch stretch main
	```
	sometimes you will need to play with package pining

- **jessie**

	Add the following stuff to your sources.list
	```
	deb https://package.cryptoguru.org/debian/jessie jessie main
	```
	sometimes you will need to play with package pining and you may have to add
	```
	deb http://ftp.debian.org/debian jessie-backports main
  ```

---

## Ubuntu

### Packages

- [burstcoincg - Burstcoin wallet powered by CryptoGuru based on MariaDB.](https://github.com/ac0v/burstcoin)
- [creepminer - The creepMiner is a client application for mining Burst on a pool or solo.](https://github.com/Creepsky/creepMiner)

### Quick Install


Copy & Paste this line into your terminal:
```
\wget -q -O - http://package.cryptoguru.org/ubuntu/init.sh | bash
```

and now you can install packages like:

```
apt-get install burstcoincg
```

!!! Info
	The wallet is started automatically after installation.

### Shell Script

The Quick- Install downloads a shell script and executes it directly. If you're really concerned about the argument that it may contain nefarious activities within, you can easily review it before you run it.

```
wget http://package.cryptoguru.org/ubuntu/init.sh
less install.sh
bash install.sh
```

and now you can install packages like:

```
apt-get install burstcoincg
```

### Add to sources


- **zesty**

	Add the following stuff to your sources.list
	```
	deb https://package.cryptoguru.org/ubuntu/zesty zesty main
	```
	sometimes you will need to play with package pining

- **xenial**

	Add the following stuff to your sources.list
	```
	deb https://package.cryptoguru.org/ubuntu/xenial xenial main
	```
	sometimes you will need to play with package pining


### Found an Issue?


!!! Bug
	Please report all bugs at [GitHub](https://github.com/PoC-Consortium/burstcoin/issues). You can also discuss your problems and get support using [Discord](https://discord.gg/NKXGM6N)

!!! Info
	The Android robot is reproduced or modified from work created and shared by Google and used according to terms described in the [Creative Commons](https://creativecommons.org/licenses/by/3.0/)3.0 Attribution License. &middot; Ubuntu is a registered trademark of Canonical Ltd.
