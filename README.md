# Vagrant VirtualBox Setup

This repository contains a Vagrant configuration for setting up an Ubuntu virtual machine (VM) using VirtualBox.

## Prerequisites

Before you begin, ensure you have the following installed on your system:

- [Vagrant](https://www.vagrantup.com/downloads) (version 2.0 or higher)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads) (version 5.0 or higher)

## Installing the Ubuntu Box

To add the Ubuntu 20.04 box to your Vagrant environment, run the following command:

```bash
vagrant box add generic/ubuntu2004


## Setting Up and Provisioning Your Virtual Machine

1. **Initialize the Vagrant environment**:
   This command creates a new `Vagrantfile` in your current directory.

   ```bash
   vagrant init generic/ubuntu2004
   ```

2. **Start the VM**:
   Use the following command to start the VM and automatically provision it.

   ```bash
   vagrant up
   ```

## Accessing Your Virtual Machine

To log into your newly created virtual machine, use:

```bash
vagrant ssh
```

## Creating Multiple Virtual Machines

If you want to create multiple VMs, you can specify a count in the Vagrantfile. Here’s how to do it:

1. Open the `Vagrantfile` in a text editor.
2. Modify the configuration to include multiple instances. For example, to create 3 VMs, add the following code snippet:

   ```ruby
   Vagrant.configure("2") do |config|
     (1..3).each do |i|
       config.vm.define "ubuntu_vm_#{i}" do |vm|
         vm.box = "generic/ubuntu2004"
       end
     end
   end
   ```

3. Run `vagrant up` again to start all defined VMs.

## Conclusion

You now have a basic setup for using Vagrant with VirtualBox to create and manage Ubuntu virtual machines. For further customization and advanced configurations, refer to the [Vagrant documentation](https://www.vagrantup.com/docs).

Feel free to contribute or raise issues if you encounter any problems!
