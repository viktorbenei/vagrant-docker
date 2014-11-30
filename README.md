vagrant-docker
==============

Base Vagrant repo to run a Docker container in Vagrant.

Uses the [phusion / baseimage](https://registry.hub.docker.com/u/phusion/baseimage/)
Docker image which can properly run with Vagrant (as a Vagrant "VM").

## How to start / run?

*Tested in an Ubuntu VM which itself runs in a Vagrant VM on OS X - should also work
on a "barebone" Ubuntu host.*

0. Install [Docker](https://www.docker.com/) and [Vagrant](https://www.vagrantup.com/) - *install these on the host which will actually run the docker container. If you're not on Linux and you want to run the docker container inside a VM like I do then you have to install Docker and Vagrant **inside** the VM*.
1. clone this repository
2. `$ cd` into this directory (the one contains this README file)
3. `$ vagrant up --provider=docker`

This will download the *phusion/baseimage* docker image if it's not yet
available on your machine; will start it in Docker and
configure it to accept ssh connection through *vagrant ssh*.

Once it's ready you can log in the regular way:

  $ vagrant ssh

Every normal vagrant command should work:

* `$ vagrant up` starts the container (first time you have to use `vagrant up --provider=docker`).
* `$ vagrant ssh` to log into the container through SSH.
* `$ vagrant halt` stops the container.
* `$ vagrant destroy` to destroy (remove) the Docker container.

## Notes

* You can use Vagrant's Shared Folder feature pretty much the same as you would with a normal VM
  * something like: `config.vm.synced_folder "~/steps", "/steps"`

