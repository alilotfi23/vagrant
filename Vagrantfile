Vagrant.configure(2) do |config|
  count = 1
  svc = "test"
  node = "test"
  vmtypes= 20
  (1..count).each do |id|
    config.vm.define "#{vmtypes-id}" do |vm|
      vm.vm.box = "generic/ubuntu2004"
      vm.vm.hostname = "#{node}-#{id}-#{svc}"
      vm.vm.network "public_network"
      vm.vm.provider "virtualbox" do |v|
        v.name = "#{node}-#{id}"
        v.memory = 4096
        v.cpus = 4
      end

    end

  end

end
