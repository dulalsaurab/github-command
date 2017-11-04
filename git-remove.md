
### To ignore some files/directorys being commited to GitHub repo 

```
cd  /.git/info/ 
```

info directory by default consist a file named - **exclude**

```info$ cat exclude 
git ls-files --others --exclude-from=.git/info/exclude
# Lines that start with '#' are comments.
# For a project mostly in C, the following would be a good set of
# exclude patterns (uncomment them if you want to use them):
 *.[oa]
# *
 .docx                                             #To exclude file/s by extension 
 .idea/


somefile.txt                                       #To exclude by file by name 


bin/
include/
lib                                                 #To exclude directory  
.idea/
ola/
```

Now, to remove some directories or file/s from the GitHub repo but not from the local directory   

First edit **exclude** file to add directory/file that you want to remove from GitHub repo - but not locally

```
user:info$ vi exclude 

#To exclude: put the directory name or the file name on the exclude file as shown below

somedirectory/
somefile.txt
```
Now run the following command on the repository 
```
git rm – –cached –r somedirecoty 
git add . 
git commit –m “message”
git push 
```
voila! there you go, your directory is available locally but is removed from the GitHub repo

Same can be achieved by creating a **.gitignore (e.g. a.gitignore)** file inside a git repo and following the same step as above

More info about git ignore - https://git-scm.com/docs/gitignore 

 
