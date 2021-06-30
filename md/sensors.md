# Sensors

These sensors are in a Gitolite respoitory hosted by *FPTrucha*.

## "*Sing Up*" process

1. Generate Key:

To generate a new key, type 
```bash
ssh-keygen
```
and follow the steps.

***Don't forget your key, please!***

This generates in `~/.ssh/` both public and private keys: `key_name.pub` and 
`key_name`, respectively.

2. Edit `~/.ssh/config` file:
```
Host tragaldabas-git
    User git
    Hostname fptrucha.usc.es
    IdentifyFile ~/.ssh/<key_name>
```
where `<key_name>` is the name of your file.

3. Copy your `key_name.pub` into the repository *gitolite-admin.git* from the 
same host (*tragaldabas-git*). To do this follow these steps:

```bash
ssh labcaf@fptrucha.usc.es
cd /tmp/
git clone tragaldabas-git:gitolite-admin.git  # You'll need access rights
cd gitolite-admin/keydir/
```
Copy in this `keydir/` directory your `key_name.pub` as `<user>.pub` where `<user>` 
is your *username*, and then edit `gitolite-admin/conf/gitolite.conf` file

```bash
cd ../conf  # (gitolite-admin/conf)
<fav_editor> gitolite.conf
# where <fav_editor> is in (vim emacs nano gedit ...)
```
adding your username `<user>` to the `@software` list:
```bash
@software = user_1 user_2 user_3 ... <user>
```
in the first line of `gitolite.conf`. 

Finally,
```bash
git add gitolite.conf
git commit -m "Users: Add new user <user>"
git push
cd /tmp
rm -rf gitolite-admin
```
commit and push changes.

Now you can clone on your computer any repository from
```
fptrucha.usc.es:/home/git/repositories/
```
with
```bash
git clone tragaldabas-git:<repo>.git
```

### Repositories

```
GIT
  |- gitolite-admin.git
  |- resting.git
  |- Software/
        |- easelenium.git
        |- ea??-selenium.git
        |- ...
        |- programa(s)_luis.git
        |- tragaldabas.git
        |- Tragaldabas.git
        |- TrasgoDBs.git
```



