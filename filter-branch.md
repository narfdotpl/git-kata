filter-branch
=============

11:30, Grzegorz Kubiak, Stand B

I was sitting too far away from the mentor and didn't hear a word. :/
I gave up after ~20 minutes.


terminal dump
-------------

    ~ > d
    ~/Desktop > g clone http://at.gitkata.pl:8080/gkubiak/filter-branch.git
    Cloning into 'filter-branch'...
    remote: Counting objects: 1142, done.
    remote: Compressing objects: 100% (150/150), done.
    remote: Total 1142 (delta 11), reused 1142 (delta 11)
    Receiving objects: 100% (1142/1142), 58.35 KiB, done.
    Resolving deltas: 100% (11/11), done.
    ~/Desktop > c fil
    c:cd: no such file or directory: fil
    ~/Desktop > c filter-branch                                                   1
    ~/Desktop/filter-branch master > g l
    ~/Desktop/filter-branch master > g lo
    65788bc katana 1
    bb34fb7 katana 1
    1f7790b katana 2
    7098e30 katana 3
    2683406 katana 4
    71f604d katana 5
    7ea0701 katana 6
    519a5f3 katana 7
    592af30 katana 8
    ddf3901 katana 9
    ab44466 Add some modifications to password.txt files
    1ba1c54 Rename directories
    ~/Desktop/filter-branch master > g b
    * master
    ~/Desktop/filter-branch master > g co tree-filter
    Branch tree-filter set up to track remote branch tree-filter from origin.
    Switched to a new branch 'tree-filter'
    ~/Desktop/filter-branch tree-filter > g x
    Unable to find application named 'gitx'
    ~/Desktop/filter-branch tree-filter > gitk                                    1
    ~/Desktop/filter-branch tree-filter > g filter-branch --tree-filter 'rm -f passw~/Desktop/filter-branch tree-filter > g filter-branch --tree-filter 'rm -f password.txt' HEAD
    Rewrite 46910a4c4b4179b2684f30179550df1ea3c81af5 (12/12)
    WARNING: Ref 'refs/heads/tree-filter' is unchanged
    ~/Desktop/filter-branch tree-filter > g lo
    65788bc katana 1
    bb34fb7 katana 1
    fc8f709 katana 2
    af90e44 katana 3
    2df9e7c katana 4
    0b14331 katana 5
    2b1ae47 katana 6
    12c58c8 katana 7
    0859e82 katana 8
    1c6d341 katana 9
    27cb716 Add some modifications to password.txt files
    46910a4 Rename directories
    ~/Desktop/filter-branch tree-filter > g filter-branch --tree-filter 'find . -name password.txt' HEAD
    Rewrite bb34fb74bb4a6f1f1c1d533eb9413f42a14de4bf (2/12)./kata1/password.txt
    Rewrite fc8f709ada45cdd2afe194c0e7facffbcfb0c4eb (3/12)./kata1/password.txt
    ./kata2/password.txt
    Rewrite af90e44d6530d8b52b5af2f8f4260b2fc686f8b4 (4/12)./kata1/password.txt
    ./kata2/password.txt
    ./kata3/password.txt
    Rewrite 2df9e7c7d3928fd966af973883d23f5fa4fd296f (5/12)./kata1/password.txt
    ./kata2/password.txt
    ./kata3/password.txt
    ./kata4/password.txt
    Rewrite 0b14331e44ce61a3fdb98e43506eaf480794f77a (6/12)./kata1/password.txt
    ./kata2/password.txt
    ./kata3/password.txt
    ./kata4/password.txt
    ./kata5/password.txt
    Rewrite 2b1ae470b5342fc3822d138b5e13aafa6afff349 (7/12)./kata1/password.txt
    ./kata2/password.txt
    ./kata3/password.txt
    ./kata4/password.txt
    ./kata5/password.txt
    ./kata6/password.txt
    Rewrite 12c58c8fcf43e6b323ea555414757a491513e0df (8/12)./kata1/password.txt
    ./kata2/password.txt
    ./kata3/password.txt
    ./kata4/password.txt
    ./kata5/password.txt
    ./kata6/password.txt
    ./kata7/password.txt
    Rewrite 0859e8246e2df69a026227d20ae2de8b8072c68f (9/12)./kata1/password.txt
    ./kata2/password.txt
    ./kata3/password.txt
    ./kata4/password.txt
    ./kata5/password.txt
    ./kata6/password.txt
    ./kata7/password.txt
    ./kata8/password.txt
    Rewrite 1c6d341c2ebe754fc2932ab8c7ce5dbe49ce1fd6 (10/12)./kata1/password.txt
    ./kata2/password.txt
    ./kata3/password.txt
    ./kata4/password.txt
    ./kata5/password.txt
    ./kata6/password.txt
    ./kata7/password.txt
    ./kata8/password.txt
    ./kata9/password.txt
    Rewrite 27cb716ade4c9e1bd85ea41997d638b8d55edb0c (11/12)./kata1/password.txt
    ./kata2/password.txt
    ./kata3/password.txt
    ./kata4/password.txt
    ./kata5/password.txt
    ./kata6/password.txt
    ./kata7/password.txt
    ./kata8/password.txt
    ./kata9/password.txt
    Rewrite 46910a4c4b4179b2684f30179550df1ea3c81af5 (12/12)./kata_1/password.txt
    ./kata_2/password.txt
    ./kata_3/password.txt
    ./kata_4/password.txt
    ./kata_5/password.txt
    ./kata_6/password.txt
    ./kata_7/password.txt
    ./kata_8/password.txt
    ./kata_9/password.txt

    WARNING: Ref 'refs/heads/tree-filter' is unchanged
    ~/Desktop/filter-branch tree-filter > g filter-branch --tree-filter 'find . -name password.txt -delete' HEAD
    Rewrite 46910a4c4b4179b2684f30179550df1ea3c81af5 (12/12)
    Ref 'refs/heads/tree-filter' was rewritten
    ~/Desktop/filter-branch tree-filter > g lo
    65788bc katana 1
    08216ce katana 1
    573adae katana 2
    b1ffbb0 katana 3
    08669b7 katana 4
    821e446 katana 5
    1cb1d43 katana 6
    9fcfd22 katana 7
    4505a7b katana 8
    84c7f66 katana 9
    fa7a967 Add some modifications to password.txt files
    5663e2a Rename directories
