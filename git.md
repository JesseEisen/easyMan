## Git

### Generate Key
    
    ssh-keygen -T rsa -C "email"

### Https visit

    git config --global http.sslverify false
    git config --global credential.helper 'cache --timeout=900'

### Remote

    git remote add remote_name remote_url  # add a remote repo
    git remote -v  # list all remote repo

### Tag
    
    git tag -a <tagname> -m "tag message"     # create tag on current commit
    git tag -a <tagname> -m "tag message" <commit id>  # create tag on specify commit

    git push origin <tagname>  
    git push origin --tags   # push all tags

    git tag -d <tagname>
    git push origin :refs/tags/<tagsname>  # delete remote tag

### commit amend

    git commit --amend --no-edit   # for forget add  a file

### subtree
    
    git remote add -f <子仓库名> <子仓库地址>
    git subtree add --prefix=<子目录名> <子仓库名> <分支> --squash

 --squash的意思是把subtree的改动合并成一次commit则不用拉取子项目的完整提交历史

    git fetch <远程仓库名> <分支>
    git subtree pull --prefix=<子目录名> <远程分支> <分支> --suqash

 推送到远程仓库
    
    git subtree push --prefix=<子目录名> <远程分支名> 分支




