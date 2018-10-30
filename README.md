# strimzi-lab
A lab focused on deploying streaming applications on top of Strimzi

## Requirements

* VirtualBox 5.2 installed
* Vagrant 2.x installed
* Java 1.8
* Maven 3
* A GitHub account
* the ability to run a 6GB VM on your laptop.
* your favorite IDE

## Build the Projects

In order to obtain all the needed Maven dependencies before coming to
the workshop, run the following builds once:

    mvn clean install -f eventr/pom.xml
    mvn clean install -f ticket-msa/invoice/pom.xml
    mvn clean install -f ticket-msa/order/pom.xml
    mvn clean install -f debezium-thorntail-demo/pom.xml

## Provision Vagrant Box

Change to the _vm-setup_ directory:

    cd vm-setup

Note: The VM definition (in _Vagrantfile_) uses a fixed IP of
192.168.33.10.
Please change it to a different value in the same network, should this
address already be used by a different machine.

Provision the VM using Vagrant:

    vagrant up

This will download the box and start it up.
Once that's done, you should be able to SSH into the box:

    vagrant ssh

Verify you can run `sudo su - build`. After that, exit the box and shut
it down:

    vagrant destroy