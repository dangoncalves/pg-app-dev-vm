### What is it?

A Vagrant configuration that starts up a PostgreSQL database in a virtual machine for local application development.
This project is mainly inspired by this [Original project].

### Installation

First install [Vagrant] and a supported provider (default is Virtualbox but libvirt, HyperV, or Parallel are supported).

Then, run the following to create a new PostgreSQL app dev virtual machine:

	# Clone it locally:
    $ git clone https://github.com/dangoncalves/pg-app-dev-vm myapp

    # Enter the cloned directory:
    $ cd myapp

    # Delete the old .git and README:
    $ rm -rf README.md .git

    # Optionally edit the database name/username/password:
    $ $EDITOR Vagrantfile

### Usage

    # Start up the virtual machine:
    $ vagrant up

    # Stop the virtual machine:
    $ vagrant halt

### What does it do?

It creates a virtual server running Ubuntu 22.04 with the specified version of PostgreSQL (*as of writing 14 is default*) installed. It also edits the PostgreSQL configuration files to allow network access and creates a database users/databases for your applications to use.

Once it has start, you can acces to your databases by accessing on port 5432 (IP is customizable in Vagrantfile).

### Why use the ansible provisioner?

[Original project] uses shell provisioner. So why using [Ansible]?

Mainly because it's simple and anybody with a basic [Ansible] knowledge can tweak the `provision.yml` to their liking.

### License

This is released under the MIT license. See the file [LICENSE](LICENSE).

[Original project]: https://github.com/jackdb/pg-app-dev-vm/
[Vagrant]: http://www.vagrantup.com/
[Ansible]: https://www.ansible.com/
