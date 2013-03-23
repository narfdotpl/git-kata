stash
=====

15:40, Kamil Trzciński, Stand C


terminal dump
-------------

    ~/Desktop/git-kata > g clone http://at.gitkata.pl:8080/ayufan/patches.gitCloning into 'patches'...
    remote: Counting objects: 5, done.
    remote: Compressing objects: 100% (3/3), done.
    remote: Total 5 (delta 0), reused 0 (delta 0)
    Unpacking objects: 100% (5/5), done.
    ~/Desktop/git-kata > c patches
    Desktop/git-kata/patches master > l
    main.bash*
    Desktop/git-kata/patches master > e main.bash
    Desktop/git-kata/patches master > g b kittens
    Branch 'kittens' doesn't exist. Create it? y
    Switched to a new branch 'kittens'
    Desktop/git-kata/patches kittens > g c
    [kittens bc8e342] added "welcome..." message
    1 file changed, 2 insertions(+)
    Desktop/git-kata/patches kittens > g l
    Desktop/git-kata/patches kittens > g lo --graph
    fatal: cannot combine --reverse with --graph
    Desktop/git-kata/patches kittens > g log --oneline --graph                  128
    * bc8e342 added "welcome..." message
    * bd4e109 make executable
    * 0faa4c2 my application
    Desktop/git-kata/patches kittens > g bm
    Switched to branch 'master'
    Desktop/git-kata/patches master > g merge --no-ff kittens
    fatal: You cannot combine --no-ff with --ff-only.
    Desktop/git-kata/patches master > g merge --no-ff kittens                   128
    Merge made by the 'recursive' strategy.
    main.bash | 2 ++
    1 file changed, 2 insertions(+)
    Desktop/git-kata/patches master > g l
    Desktop/git-kata/patches master > g lo
    0faa4c2 my application
    bd4e109 make executable
    bc8e342 added "welcome..." message
    d6daada Merge branch 'kittens'
    Desktop/git-kata/patches master > g log --oneline --graph
    *   d6daada Merge branch 'kittens'
    |\
    | * bc8e342 added "welcome..." message
    |/
    * bd4e109 make executable
    * 0faa4c2 my application
    Desktop/git-kata/patches master > save
    Desktop/git-kata/patches master >
    Desktop/git-kata/patches master+ > g diff
    diff --git a/main.bash b/main.bash
    index 0a0db9b..3385a0e 100755
    --- a/main.bash
    +++ b/main.bash
    @@ -8,6 +8,8 @@ fi

    echo "Welcome to password script"

    +echo "bazinga!"
    +
    echo "Username: $1"
    echo -n "Password: "
    echo $2 | openssl passwd -crypt -salt 10 -stdin
    Desktop/git-kata/patches master+ > g ss
    Saved working directory and index state WIP on master: d6daada Merge branch 'kittens'
    HEAD is now at d6daada Merge branch 'kittens'
    Desktop/git-kata/patches master& > g sl
    Desktop/git-kata/patches master& > g stash drop
    Dropped refs/stash@{0} (43f3b162fb37098ab1d796a9954752b0e8fe5206)
    Desktop/git-kata/patches master > g fsck
    Checking object directories: 100% (256/256), done.
    dangling commit 43f3b162fb37098ab1d796a9954752b0e8fe5206
    Desktop/git-kata/patches master > g fsck | awk '{ print $3 }'
    Checking object directories: 100% (256/256), done.
    43f3b162fb37098ab1d796a9954752b0e8fe5206
    Desktop/git-kata/patches master > g fsck | awk '{ print $3 }' | xargs git log --oneline
    Checking object directories: 100% (256/256), done.
    43f3b16 WIP on master: d6daada Merge branch 'kittens'
    2a3659e index on master: d6daada Merge branch 'kittens'
    d6daada Merge branch 'kittens'
    bc8e342 added "welcome..." message
    bd4e109 make executable
    0faa4c2 my application
    Desktop/git-kata/patches master > g fsck | awk '{ print $3 }' | xargs git log --oneline --no-walk
    Checking object directories: 100% (256/256), done.
    43f3b16 WIP on master: d6daada Merge branch 'kittens'
    Desktop/git-kata/patches master > g cp 43f3b16
    error: Commit 43f3b162fb37098ab1d796a9954752b0e8fe5206 is a merge but no -m option was given.
    fatal: cherry-pick failed
    Desktop/git-kata/patches master > g stash apply 43f3b16                     128
    # On branch master
    # Your branch is ahead of 'origin/master' by 2 commits.
    #   (use "git push" to publish your local commits)
    #
    # Changes not staged for commit:
    #   (use "git add <file>..." to update what will be committed)
    #   (use "git checkout -- <file>..." to discard changes in working directory)
    #
    #	modified:   main.bash
    #
    no changes added to commit (use "git add" and/or "git commit -a")
    Desktop/git-kata/patches master+ > g fsck | awk '{ print $3 }' | xargs git log --oneline --no-walk
    Checking object directories: 100% (256/256), done.
    43f3b16 WIP on master: d6daada Merge branch 'kittens'
    Desktop/git-kata/patches master+ > g rh
    HEAD is now at d6daada Merge branch 'kittens'
    Desktop/git-kata/patches master > g fsck | awk '{ print $3 }' | xargs git log --oneline --no-walk
    Checking object directories: 100% (256/256), done.
    43f3b16 WIP on master: d6daada Merge branch 'kittens'
    Desktop/git-kata/patches master > g prune
    Desktop/git-kata/patches master > g fsck | awk '{ print $3 }' | xargs git log --oneline --no-walk
    Checking object directories: 100% (256/256), done.
    Desktop/git-kata/patches master >
