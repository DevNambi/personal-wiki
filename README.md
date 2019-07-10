# personal-wiki

Code to create a personal wiki based on [MDwiki](http://mdwiki.info/)

# Installation

### Download and Setup MDwiki

Let's assume you're using OS X, Dropbox to sync your files, and your username is ```YourUserNameHere```.

**Make a directory, 'personalwiki'**

Make a folder, ```personalwiki```, under your root Dropbox folder:

```
mkdir -p /Users/YourUserNameHere/Dropbox/personalwiki
```


**Set up the mdwiki base site**

* Download the zip file from the [releases page](https://github.com/Dynalon/mdwiki/releases)
* Copy the zip file and its mdwiki.html file to the personalwiki directory
* Rename mdwiki.html to index.html


### Install and Configure Nginx

I'm going to assume you're using Homebrew

```
brew install nginx
sudo nginx
cd /usr/local/etc/nginx/
```

Navigate to http://localhost:8080/ to confirm that it's working. 


**Secure Nginx**

* Make an Nginx config file (```nginx.conf```) that limits access to localhost. Use [my configuration file](nginx-laptop.conf) if you'd like.
* Copy the nginx config file to ```/usr/local/etc/nginx``` . Make sure it's named ```nginx.conf```

**Auto-Start Nginx**

To have launchd start nginx now and restart at login:

```
brew services start nginx
```

**Resources**

* [Installing Nginx in Mac OS X Maverick With Homebrew](https://medium.com/@ThomasTan/installing-nginx-in-mac-os-x-maverick-with-homebrew-d8867b7e8a5a)
* [Allow only local users in nginx](https://serverfault.com/questions/667798/allow-only-local-users-in-nginx)
* [How to Host a Static Website with Nginx](https://medium.com/@jasonrigden/how-to-host-a-static-website-with-nginx-8b2dd0c5b301)


# Configuration

Once you have MDwiki and Nginx installed, you need to set up your site! I made a basic configuration using 3 files:

1. [index.md](index.md) - The home page for my site. My version is quite sparse, using HTML tables + links extensively.
2. [navigation.md](navigation.md) - What would a navigation menu have in it? Put it in here. I made menu links for my pages about Health, Music, Work, People, Living, and Career.
3. [config.json](config.json) - defines a title, enables side menus, and sets an anchor character.


There are useful resources on configuring [MDwiki](http://mdwiki.info/) available on its [Quickstart page](http://dynalon.github.io/mdwiki/#!quickstart.md)

