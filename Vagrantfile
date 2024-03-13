IMAGE_NAME = "geerlingguy/ubuntu2004"
VM_COUNT = 3
NODE_CPU = 1 
NODE_MEM = 1024

IP_BASE = "192.168.56."

Vagrant.configure("2") do |config|
      (1..VM_COUNT).each do |i|      
        config.vm.define "target-#{i}" do |target|
            target.vm.box = IMAGE_NAME
            target.vm.network "private_network", ip: "#{IP_BASE}#{i + 10}"
            target.vm.network "public_network"
            target.vm.hostname = "target-#{i}"
            target.ssh.forward_agent = true
            target.vm.provider "virtualbox" do |v|
                v.memory = NODE_MEM
                v.cpus = NODE_CPU
            end            
        end
    end
end
