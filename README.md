#How I made this page appear
> obviously the README.md has been expanded vs the one line in the example, but the principle is the same

###add new repository
```shell
# !!! must make repository via website first !!! #

# make a dummy directory
mkdir /Volumes/github; cd /Volumes/github
mkdir demo; cd demo

# initialize local
git init

# populate local
echo "# this is a dummy demo" >> README.md
git add README.md
git commit -m "first commit"

# make remotely
git remote add origin https://github.com/martincarroll87/demo.git
#git remote add origin git@github.com:martincarroll87/demo.git  
# git remote -v

# populate remote
#git remote set-url origin git://github.com/martincarroll87/demo.git
#git remote set-url origin https://github.com/martincarroll87/demo.git
git push origin master
```

===================================
###push an existing repository 

```shell
git remote add origin https://github.com/martincarroll87/demo.git
git push -u origin master
```

===================================
###remove repository

```shell
rm -rf ./.git*
rm -rf ./*
git remote rm origin
```

===================================
###update repository

```shell
echo "# ... more info about this or that ..." >> README.md
git add README.md
git commit -m "second commit"
git push origin master
```

-----------------------------------
# other

###make ssh key
```shell
#https://help.github.com/articles/generating-an-ssh-key/

ls -al ~/.ssh
ssh-keygen -t rsa -b 4096 -C "martincarroll87@gmail.com"
# saved to /Volumes/github/id_rsa

eval "$(ssh-agent -s)"
ssh-add /Volumes/github/id_rsa

# manually add to github
pbcopy < ~/.ssh/id_rsa.pub
#https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/

ssh -T git@github.com
```

-----------------------------------

