# gold

Linked Data server for Go

[![Build Status](https://travis-ci.org/linkeddata/gold.png)](https://travis-ci.org/linkeddata/gold)

## Install

### From docker repository:

    sudo docker pull linkeddata/gold

    sudo docker run -p ip:port:443 linkeddata/gold

Replace `ip` and `port` with your host computer's IP address and port number.

To check the status of the container, type:

    sudo docker ps

`IMPORTANT`: if you want to mount a host directory into the container, you can use the -v parameter:

    sudo docker run -p ip:port:443 -v /var/www:/gold-data linkeddata/gold

This will mount the host directory, `/var/www/`, into the container as the `/gold-data/` directory. Doing this will allow you to reuse the data directory without worrying about persistence inside the container.


### From Github:

Setup Go + dependencies:

    # on OSX eg.
    brew install go raptor libmagic

    # on Ubuntu eg.
    sudo apt-get install golang-go libraptor2-dev libmagic-dev 

    mkdir ~/go; export GOPATH=~/go

Use the `go get` command:

    go get github.com/linkeddata/gold/server
    
Optionally, you can install some extra dependencies used by the tests:

    go get github.com/drewolson/testflight
    go get github.com/stretchr/testify/assert

Run the server:

    $GOPATH/bin/server -help

## License

[MIT](http://joe.mit-license.org/)
