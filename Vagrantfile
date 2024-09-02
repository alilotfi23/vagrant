# Vagrant configuration block, version 2
Vagrant.configure(2) do |config|
  # Define the number of VMs to create
  count = 1
  # Service name for the VMs
  svc = "test"
  # Base name for the VM nodes
  node = "test"
  # Number of VM types to create (not directly used in this loop)
  vmtypes = 20

  # Loop to create 'count' number of VMs
  (1..count).each do |id|
    # Define a new VM with a unique name based on the loop index
    config.vm.define "#{vmtypes - id}" do |vm|
      # Specify the base box to use for the VM
      vm.vm.box = "generic/ubuntu2004"
      # Set the hostname for the VM, combining node, id, and service name
      vm.vm.hostname = "#{node}-#{id}-#{svc}"
      # Configure the VM to use a public network
      vm.vm.network "public_network"
      # Provider-specific configuration for VirtualBox
      vm.vm.provider "virtualbox" do |v|
        # Set the name of the VirtualBox instance
        v.name = "#{node}-#{id}"
        # Allocate 4096 MB of memory to the VM
        v.memory = 4096
        # Allocate 4 CPU cores to the VM
        v.cpus = 4
      end
    end
  end
end
