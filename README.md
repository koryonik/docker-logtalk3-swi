# Logtalk3 with SWI Prolog Docker container
[Docker](http://docker.com) container to install and run [Logtalk](http://logtalk.org) with [SWI Prolog](http://www.swi-prolog.org) backend

## Retrieve image

You can pull image from docker hub.

    $ docker pull koryonik/logtalk-swi

Or you can manually build image by below commands :

    $ git clone koryonik/docker-logtalk3-swi
    $ cd docker-logtalk3-swi
    $ ./build.sh

## Run interactive

    $ docker run --rm -i -t koryonik/logtalk-swi

    Logtalk 3.2.0
    ...
    Welcome to SWI-Prolog (Multi-threaded, 64 bits, Version 7.2.3)
    ...
    For help, use ?- help(Topic). or ?- apropos(Word).

    ?-

## Run locale sources
    $ cd my/source
    $ docker run --rm -i -t -v $(pwd):/source koryonik/logtalk-swi -f hello_world.lgt

    Hello World !

## Enter container for specific usages
    $ docker run --rm -i -t -v $(pwd):/source --entrypoint bash koryonik/logtalk3-swi
    root@2c5f42d4aae5:/source# swilgt

    Logtalk 3.2.0
    ?- 
