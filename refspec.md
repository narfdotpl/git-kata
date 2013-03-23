refspec
=======

12:20, Mateusz Grzechociński, Stand A

This time I was sitting right next to the mentor. :)


notes
-----

### multiple fetch refs

    [remote "origin"]
        fetch = +refs/heads/master:refs/remotes/origin/master
        fetch = +refs/heads/foo/*:refs/remotes/origin/foo/*


### force update local repo

    git pull origin +master:master


### force update remote repo

    git push --force origin master

is the same as

    git push origin +master:master
