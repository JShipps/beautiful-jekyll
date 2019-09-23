---
layout: post
title: Using Let's Encrypt with Apache on Ubuntu 16.04
date: 2019-09-13 20:36:08
category: Guide
tags: HTTPS, EFF, CertBot
---

I look back fondly at a time before Let's Encrypt - when if you wanted to use SSL you needed to fork out the cash to do so. Those were the good old days! Said no one ever... But on a more serious note - Let's Encrypt is absolutely awesome! If you own a domain name you should have a signed certificate since everything on the internet is pretty much aiming for HTTPS this day and age.

Before we dive headfirst into the shallow end of this pool we're going to want to make sure we've got our server setup properly. That means we're ready to serve web content and we've setup our Apache instance accurately.

### Installing CertBot

Let's Encrypt certificates are grabbed via a client software running on your own server. This may come stock in your version of Ubuntu but we're going to add this repository because of beta updates and the idea that the direct source is more often quicker than not when it comes to releases.

```shell
sudo add-apt-repository ppa:certbot/certbot
```

Once we've added the repository we're going to run a standard update, this isn't anything that is new to anyone.

```shell
sudo apt update
```

Finally, we're going to install CertBot - I know, I know, this is the part you've all been waiting for!

```shell
sudo apt install python-certbot-apache
```

### Creating the SSL Certificate

Now generating your certificate with CertBot is incredibly simple and straightforward. THe CertBot client is going to automatically obtain/install a new SSL Certificate to the domains provided.

To make all of this happen all we're going to do is run the following command

```shell
sudo certbot --apache -d example.com
```

In this case, **example.com** is going to be changed to your domain name.

If you'd like to install a single certificate which is valid for multiple domains and subdomains you can pass them as additional paramaters to the command. The first domain will always be considered the base domain. For that reason it's always suggested that you use the bare domain, **example.com** as opposed to **www.example.com**. Though we can create a catch all by registering both!

```shell
sudo certbot --apache -d example.com -d www.example.com
```

As we discussed just above, **example.com** is the base domain in this particular case.

If you're dealing with multiple virtualhosts you should run CertBot for every individual virtualhost.

Now you're in the step-by-step portion Let's Encrypt has baked up and let's be honest - this is incredibly easy. Do we want to force the certificate to be used? Well, obviously... no one wants to not use SSL these days!

When the installation is finished, you should be able to find the generated certificate files at _/etc/letsencrypt/live_. You can verify the status of your SSL certificate with the following link (don’t forget to replace example.com with your base domain):

```shell
http://ssllabs.com/ssltest/analyze.html?d=example.com&latest
```

### Conclusion

You should now have a fancy little SSL Certificate for your website and people should trust you a little bit more! Or not, who knows if you're trustworthy or not!