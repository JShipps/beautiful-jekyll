---
layout: post
title: Upgrading Node.JS on Ubuntu/Debian
date: 2019-09-20 10:36:08
category: Guide
tags: HTTPS, EFF, CertBot
---

Updating Node.JS in place is kind of counter intuitive unless you know what it is you're doing __exactly__. Luckily NodeSource has all of this laid out, though I tend to have a difficult time finding [This](https://github.com/nodesource/distributions#installation-instructions) when I really need it. 

### Node.js v12.x
```shell
# Using Ubuntu
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
sudo apt-get install -y nodejs
```


```shell
# Using Debian, as root
curl -sL https://deb.nodesource.com/setup_12.x | bash -
apt-get install -y nodejs
```

### Node.js v11.x
```shell
# Using Ubuntu
curl -sL https://deb.nodesource.com/setup_11.x | sudo -E bash -
sudo apt-get install -y nodejs
```

```shell
# Using Debian, as root
curl -sL https://deb.nodesource.com/setup_11.x | bash -
apt-get install -y nodejs
```

### Node.js v10.x
```shell
# Using Ubuntu
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt-get install -y nodejs
```

```shell
# Using Debian, as root
curl -sL https://deb.nodesource.com/setup_10.x | bash -
apt-get install -y nodejs
```

### Node.js v9.x
```shell
# Using Ubuntu
curl -sL https://deb.nodesource.com/setup_9.x | sudo -E bash -
sudo apt-get install -y nodejs
```

```shell
# Using Debian, as root
curl -sL https://deb.nodesource.com/setup_9.x | bash -
apt-get install -y nodejs
```

### Node.js v8.x
```shell
# Using Ubuntu
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
```

```shell
# Using Debian, as root
curl -sL https://deb.nodesource.com/setup_8.x | bash -
apt-get install -y nodejs
```

### Node.js v7.x
```shell
# Using Ubuntu
curl -sL https://deb.nodesource.com/setup_7.x | sudo -E bash -
sudo apt-get install -y nodejs
```

```shell
# Using Debian, as root
curl -sL https://deb.nodesource.com/setup_7.x | bash -
apt-get install -y nodejs
```

### Node.js v6.x
```shell
# Using Ubuntu
curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
sudo apt-get install -y nodejs
```

```shell
# Using Debian, as root
curl -sL https://deb.nodesource.com/setup_6.x | bash -
apt-get install -y nodejs
```

### Node.js v5.x
```shell
# Using Ubuntu
curl -sL https://deb.nodesource.com/setup_5.x | sudo -E bash -
sudo apt-get install -y nodejs
```

```shell
# Using Debian, as root
curl -sL https://deb.nodesource.com/setup_5.x | bash -
apt-get install -y nodejs
```

### Node.js v4.x
```shell
# Using Ubuntu
curl -sL https://deb.nodesource.com/setup_4.x | sudo -E bash -
sudo apt-get install -y nodejs
```

```shell
# Using Debian, as root
curl -sL https://deb.nodesource.com/setup_4.x | bash -
apt-get install -y nodejs
```

### Node.js v0.12
```shell
# Using Ubuntu
curl -sL https://deb.nodesource.com/setup_0.12 | sudo -E bash -
sudo apt-get install -y nodejs
```

```shell
# Using Debian, as root
curl -sL https://deb.nodesource.com/setup_0.12 | bash -
apt-get install -y nodejs
```

### Node.js v0.10
```shell
# Using Ubuntu
curl -sL https://deb.nodesource.com/setup_0.10 | sudo -E bash -
sudo apt-get install -y nodejs
```

```shell
# Using Debian, as root
curl -sL https://deb.nodesource.com/setup_0.10 | bash -
apt-get install -y nodejs
```

### io.js v3.x
```shell
# Using Ubuntu
curl -sL https://deb.nodesource.com/setup_iojs_3.x | sudo -E bash -
sudo apt-get install -y iojs
```

```shell
# Using Debian, as root
curl -sL https://deb.nodesource.com/setup_iojs_3.x | bash -
apt-get install -y iojs
```

### io.js v2.x
```shell
# Using Ubuntu
curl -sL https://deb.nodesource.com/setup_iojs_2.x | sudo -E bash -
sudo apt-get install -y iojs
```

```shell
# Using Debian, as root
curl -sL https://deb.nodesource.com/setup_iojs_2.x | bash -
apt-get install -y iojs
```

### io.js v1.x
_Note: this branch of io.js is not actively maintained and is not recommended for production use._

```shell
# Using Ubuntu
curl -sL https://deb.nodesource.com/setup_iojs_1.x | sudo -E bash -
sudo apt-get install -y iojs
```

```shell
# Using Debian, as root
curl -sL https://deb.nodesource.com/setup_iojs_1.x | bash -
apt-get install -y iojs
```

Optional: install build tools

To compile and install native addons from npm you may also need to install build tools:

```shell
# use `sudo` on Ubuntu or run this as root on debian
apt-get install -y build-essential
```

### Conclusion

I've thrown this together because there have been numerous times when I'll fresh install a node I'm working on and suddenly I'm getting Node versioning issues due to the standard repo not having the most up-to-date version. 

Hopefully this is beneficial to anyone other than myself.