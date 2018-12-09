# Vagrant for WireShark

This is a Vagrantfile for generating WireShark environment on Ubuntu 16.04.

## Requirement

- VirtualBox
- Vagrant
- X server

## Install

Clone this repo to wherever you like. And type the following command.

```
$ vagrant up
```

Then you can log in the virtual machine via ssh by using the following command.

```
$ vagrant ssh
```

You can use WireShark!

```
vagrant@ubuntu-xenial:~$ wireshark
```
