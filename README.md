vagrant-docker
==============

Base Vagrant repo to run a Docker container in Vagrant.

Uses the [phusion / baseimage](https://registry.hub.docker.com/u/phusion/baseimage/)
Docker image which can properly run within Vagrant.

## How to start / run?

*Tested in an Ubuntu VM which itself runs in a Vagrant VM on OS X - should also work
in "barebone" Ubuntu*

0. Install [Docker](https://www.docker.com/) and [Vagrant](https://www.vagrantup.com/)
1. clone this repository
2. `$ cd` into this directory (the one contains this README file)
3. `$ vagrant up --provider=docker`

This will download the *phusion/baseimage* docker image if it's not yet
available on your machine, start it in Docker and
configure it to accept ssh connection through *vagrant ssh*.

Once it's ready you can log in the regular way:

  $ vagrant ssh

Every normal vagrant command should work:

* `$ vagrant up` starts the container (first time you have to use `vagrant up --provider=docker`).
* `$ vagrant ssh` to log into the container through SSH.
* `$ vagrant halt` stops the container.
* `$ vagrant destroy` to destroy (remove) the Docker container.
