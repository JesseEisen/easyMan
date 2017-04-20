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


