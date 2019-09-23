---
title: Installing Hexo on Ubuntu 16.04
layout: post
categories: Guide
date: 2019-09-08 17:09:00
---
Over the years I've used a lot of different CMS platforms - Ghost happens to be one of my favorites but recently I've decided I wanted something a little more lightweight.

What could be more lightweight than static pages? Enter [Hexo](https://hexo.io)!

Let's get a little bit of background here on Hexo because I'm sure some people out there aren't too familiar, if at all.

Hexo, much like some PHP driven CMS frameworks offers a lot of power - though Hexo is more SEO friendly right out of the box. Not to mention it runs on NodeJS. Let's not be confused though, Hexo is NOT a PHP driven blog framework!

With that being said, let's get into the real meat of this guide!
___
### Installing Ruby

```bash
sudo apt update
sudo apt install curl git
```

Once we've got these two packages installed we're ready to add some repositories, in this case NodeJS and Yarn.

```bash
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
```

Now that we've added all that, let's get our dependancies installed!

```bash
sudo apt-get update
sudo apt-get install nodejs yarn zlib1g-dev build-essential libpq-dev libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev software-properties-common libffi-dev
```

After we've added the repositories and dependancies, we can go ahead and get Ruby installed via __rbenv__.

```bash
cd ~/
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
exec $SHELL

git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL
```

Once we've run the above commands we're ready to actually install Ruby __2.5.3__.

*We can use 2.5.3 or we can use the most recent version, if you'd like to use a newer version available, if any, visit [this site](https://www.ruby-lang.org/en/downloads/) and change the version numbering.*

```bash
rbenv install 2.5.3
rbenv global 2.5.3
```

Once that is all said and done, we can now verify we've got Ruby installed!

```bash
ruby -v
```

Running this command should yield something similar to that below:

```bash
ruby 2.5.3p105 (2018-10-18 revision 65156) [x86_64-linux]
```
___
### Install NodeJS

Now that we've got our Ruby environment setup and confirmed, we're going to need to install NodeJS!

```bash
curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs
```

We can also verify the version of NodeJS we've got installed by running the following:

```bash
node -v
```

Viola! We've got NodeJS installed, now here comes the most enjoyable part!
___
### Installing Hexo

Since we've finally got our environment fully setup, we've confirmed Ruby is installed and the same goes for NodeJS, let's get down in it and install Hexo.

```bash
sudo npm install hexo-cli -g
cd ~/
hexo init hexo
```

*You can name the Hexo folder whatever it is you'd like, you're not limited to just naming it Hexo.*

Once we've got the project folder created we're going to move into that folder and start our Hexo server from there!

```bash
cd hexo
sudo npm install
hexo server -d
```

After a short period, all necessary packages should be installed and you'll then be able to access your Hexo server! If you're doing this on a local machine;

**localhost:4000**

![alt text](https://deadcode.cf/image/hexohome.png "Hexo home page")

You should then see the Hexo homepage!

___
### Conclusion

Once you've completed all the steps above, you should have a fully operational version of Hexo running. Be sure to keep an eye out for the next steps here on deadcode!

As an addendum - if you're stuck I recommend looking at the homepage of your Hexo installation. This explains quite plainly how to deploy or generate all of your content. Hexo is a full featured suite and definitely can do anything you want it to!