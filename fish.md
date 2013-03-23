fish
====

14:50, Mateusz Grzechociński, Stand A


installation
------------

    git clone https://github.com/fish-shell/fish-shell
    cd fish-shell
    xcodebuild install
    mkdir -p /usr/local/Cellar/fish/github
    cd !$
    cp -r /tmp/fish.dst/usr/local/* .
    brew switch fish github

not

    brew install fish

:unamused:


WTF moment
----------

    ~ > fish
    Welcome to fish, the friendly interactive shell
    Type help for instructions on how to use fish
    narf@Air ~> cd dotfiles/
    cd: The directory 'dotfiles/' does not exist
    narf@Air ~> cd ./dotfiles/
    narf@Air ~/dotfiles>
