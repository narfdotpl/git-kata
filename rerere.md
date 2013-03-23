rerere
======

17:20, Mateusz Grzechociński, Macoscope


terminal dump
-------------

    ~/Desktop/git-kata > g clone http://at.gitkata.pl:8080/mateusz.grzechocinski/gitkata_mgrzechocinski.git
    Cloning into 'gitkata_mgrzechocinski'...
    remote: Counting objects: 74, done.
    remote: Compressing objects: 100% (39/39), done.
    remote: Total 74 (delta 12), reused 0 (delta 0)
    Unpacking objects: 100% (74/74), done.
    ~/Desktop/git-kata > c gitkata_mgrzechocinski
    Desktop/git-kata/gitkata_mgrzechocinski master > l
    README.md
    TEST2
    build.gradle
    src/
    test
    Desktop/git-kata/gitkata_mgrzechocinski master > f Per*
    ./src/main/java/pl/gitkata/rerere/Person.java
    ./src/test/java/pl/polidea/rerere/PersonTest.java
    Desktop/git-kata/gitkata_mgrzechocinski master > ee
    2 files to edit
    Desktop/git-kata/gitkata_mgrzechocinski master > g b
    * master
    Desktop/git-kata/gitkata_mgrzechocinski master+ > g c
    [master 6839200] changed name to name1
    1 file changed, 1 insertion(+), 1 deletion(-)
    Desktop/git-kata/gitkata_mgrzechocinski master > g b topic/my_feature
    Branch 'topic/my_feature' doesn't exist. Create it? y
    Switched to a new branch 'topic/my_feature'
    Desktop/git-kata/gitkata_mgrzechocinski topic/my_feature > g bm
    Switched to branch 'master'
    Your branch is ahead of 'origin/master' by 1 commit.
    (use "git push" to publish your local commits)
    Desktop/git-kata/gitkata_mgrzechocinski master > g b -D topic/my_feature
    Deleted branch topic/my_feature (was 6839200).
    Desktop/git-kata/gitkata_mgrzechocinski master > g checkout HEAD~1 -b topic/my_feature
    Switched to a new branch 'topic/my_feature'
    Desktop/git-kata/gitkata_mgrzechocinski topic/my_feature > g l
    Desktop/git-kata/gitkata_mgrzechocinski topic/my_feature > g c
    [topic/my_feature d6e4e78] added new line
    1 file changed, 1 insertion(+)
    Desktop/git-kata/gitkata_mgrzechocinski topic/my_feature > gbm
    zsh: command not found: gbm
    Desktop/git-kata/gitkata_mgrzechocinski topic/my_feature > g bm             127
    Switched to branch 'master'
    Your branch is ahead of 'origin/master' by 1 commit.
    (use "git push" to publish your local commits)
    Desktop/git-kata/gitkata_mgrzechocinski master > g mm
    Auto-merging src/main/java/pl/gitkata/rerere/Person.java
    CONFLICT (content): Merge conflict in src/main/java/pl/gitkata/rerere/Person.java
    Automatic merge failed; fix conflicts and then commit the result.
    Desktop/git-kata/gitkata_mgrzechocinski master+ > g d                         1
    Vim: Reading from stdin...
    Desktop/git-kata/gitkata_mgrzechocinski master+ > g c
    [master 8f45f02] Merge branch 'topic/my_feature'
    Desktop/git-kata/gitkata_mgrzechocinski master > z
    Desktop/git-kata/gitkata_mgrzechocinski master > enable rerere
    enable: no such hash table element: rerere
    Desktop/git-kata/gitkata_mgrzechocinski master > g rh HEAD~1                  1
    HEAD is now at 6839200 changed name to name1
    Desktop/git-kata/gitkata_mgrzechocinski master > g merge topic/my_feature
    fatal: Not possible to fast-forward, aborting.
    Desktop/git-kata/gitkata_mgrzechocinski master > g merge topic/my_feature   128
    Auto-merging src/main/java/pl/gitkata/rerere/Person.java
    CONFLICT (content): Merge conflict in src/main/java/pl/gitkata/rerere/Person.java
    Recorded preimage for 'src/main/java/pl/gitkata/rerere/Person.java'
    Automatic merge failed; fix conflicts and then commit the result.
    Desktop/git-kata/gitkata_mgrzechocinski master+ > g rerere status             1
    src/main/java/pl/gitkata/rerere/Person.java
    Desktop/git-kata/gitkata_mgrzechocinski master+ > g rerere diff
    --- a/src/main/java/pl/gitkata/rerere/Person.java
    +++ b/src/main/java/pl/gitkata/rerere/Person.java
    @@ -2,12 +2,12 @@

    public class Person {

    -<<<<<<<
    +<<<<<<< HEAD
        private final String name1;
    =======
        private final String name;
        private final String name2;
    ->>>>>>>
    +>>>>>>> topic/my_feature

        public Person(String name) {
            this.name = name;
    Desktop/git-kata/gitkata_mgrzechocinski master+ > g c
    Recorded resolution for 'src/main/java/pl/gitkata/rerere/Person.java'.
    [master 98e665c] Merge branch 'topic/my_feature'
    Desktop/git-kata/gitkata_mgrzechocinski master > g rerere status
    Desktop/git-kata/gitkata_mgrzechocinski master > g rerere diff
    Desktop/git-kata/gitkata_mgrzechocinski master > c .git/rr-cache
    gitkata_mgrzechocinski/.git/rr-cache > l
    e8eaf33bfdd024f2176dced08dc644b95f6cedc4/
    gitkata_mgrzechocinski/.git/rr-cache > e e8eaf33bfdd024f2176dced08dc644b95f6cedc4
    gitkata_mgrzechocinski/.git/rr-cache > ,
    Desktop/git-kata/gitkata_mgrzechocinski master > g rh HEAD~1
    HEAD is now at 6839200 changed name to name1
    Desktop/git-kata/gitkata_mgrzechocinski master > f Per*
    ./src/main/java/pl/gitkata/rerere/Person.java
    ./src/test/java/pl/polidea/rerere/PersonTest.java
    Desktop/git-kata/gitkata_mgrzechocinski master > mv ./src/main/java/pl/gitkata/rerere/Person.java p.java
    Desktop/git-kata/gitkata_mgrzechocinski master+ > g a
    [master 8f3a39a] moved Person.java
    1 file changed, 0 insertions(+), 0 deletions(-)
    rename src/main/java/pl/gitkata/rerere/Person.java => p.java (100%)
    Desktop/git-kata/gitkata_mgrzechocinski master > g merge topic/my_feature
    Auto-merging p.java
    CONFLICT (content): Merge conflict in p.java
    Resolved 'p.java' using previous resolution.
    Automatic merge failed; fix conflicts and then commit the result.
    Desktop/git-kata/gitkata_mgrzechocinski master+ > g rh                        1
    HEAD is now at 8f3a39a moved Person.java
    Desktop/git-kata/gitkata_mgrzechocinski master > g rh HEAD~1
    HEAD is now at 6839200 changed name to name1
    Desktop/git-kata/gitkata_mgrzechocinski master > g merge topic/my_feature
    Auto-merging src/main/java/pl/gitkata/rerere/Person.java
    CONFLICT (content): Merge conflict in src/main/java/pl/gitkata/rerere/Person.java
    Resolved 'src/main/java/pl/gitkata/rerere/Person.java' using previous resolution.
    Automatic merge failed; fix conflicts and then commit the result.
    Desktop/git-kata/gitkata_mgrzechocinski master+ > g s                         1
    UU src/main/java/pl/gitkata/rerere/Person.java
    Desktop/git-kata/gitkata_mgrzechocinski master+ > g e
    Desktop/git-kata/gitkata_mgrzechocinski master+ >
    Desktop/git-kata/gitkata_mgrzechocinski master+ > g rh
    HEAD is now at 6839200 changed name to name1
    Desktop/git-kata/gitkata_mgrzechocinski master > g l
    Desktop/git-kata/gitkata_mgrzechocinski master > ,
    gitkata_mgrzechocinski/.git/rr-cache > l
    e8eaf33bfdd024f2176dced08dc644b95f6cedc4/
    gitkata_mgrzechocinski/.git/rr-cache > ,
    Desktop/git-kata/gitkata_mgrzechocinski master > g merge topic/my_feature
    Auto-merging src/main/java/pl/gitkata/rerere/Person.java
    CONFLICT (content): Merge conflict in src/main/java/pl/gitkata/rerere/Person.java
    Resolved 'src/main/java/pl/gitkata/rerere/Person.java' using previous resolution.
    Automatic merge failed; fix conflicts and then commit the result.
    Desktop/git-kata/gitkata_mgrzechocinski master+ > g e                         1
    Desktop/git-kata/gitkata_mgrzechocinski master+ > g rh
    HEAD is now at 6839200 changed name to name1
    Desktop/git-kata/gitkata_mgrzechocinski master > mv ./src/main/java/pl/gitkata/rerere/Person.java p.java
    Desktop/git-kata/gitkata_mgrzechocinski master+ > g a
    [master 65c2080] moved Person.java
    1 file changed, 0 insertions(+), 0 deletions(-)
    rename src/main/java/pl/gitkata/rerere/Person.java => p.java (100%)
    Desktop/git-kata/gitkata_mgrzechocinski master > g merge topic/my_feature
    Auto-merging p.java
    CONFLICT (content): Merge conflict in p.java
    Resolved 'p.java' using previous resolution.
    Automatic merge failed; fix conflicts and then commit the result.
    Desktop/git-kata/gitkata_mgrzechocinski master+ > g e                         1
    Desktop/git-kata/gitkata_mgrzechocinski master+ > g rh
    HEAD is now at 65c2080 moved Person.java
    Desktop/git-kata/gitkata_mgrzechocinski master > e p.java
    Desktop/git-kata/gitkata_mgrzechocinski master > g c
    [master 6a45ea3] dupa
    1 file changed, 1 insertion(+)
    Desktop/git-kata/gitkata_mgrzechocinski master > g merge topic/my_feature
    Auto-merging p.java
    CONFLICT (content): Merge conflict in p.java
    Resolved 'p.java' using previous resolution.
    Automatic merge failed; fix conflicts and then commit the result.
    Desktop/git-kata/gitkata_mgrzechocinski master+ > g d                         1
    Vim: Reading from stdin...
    Desktop/git-kata/gitkata_mgrzechocinski master+ > ,
    gitkata_mgrzechocinski/.git/rr-cache > e
    gitkata_mgrzechocinski/.git/rr-cache > g --version
    git version 1.8.2
    hub version 1.10.5
    gitkata_mgrzechocinski/.git/rr-cache > ,
    Desktop/git-kata/gitkata_mgrzechocinski master+ >
