#
# Testing environnement for ASAP project
#

servers = [
  {
    :hostname => "debian10",
    :ip => "192.168.56.10",
    :box => "generic/debian10",
    :ram => 1024,
    :cpu => 1 
  },
  {
    :hostname => "debian11",
    :ip => "192.168.56.11",
    :box => "generic/debian11",
    :ram => 1024,
    :cpu => 1
  },
  {
    :hostname => "debian12",
    :ip => "192.168.56.12",
    :box => "generic/debian12",
    :ram => 1024,
    :cpu => 1
  },  
  {
    :hostname => "ubuntu1804",
    :ip => "192.168.56.184",
    :box => "hashicorp/bionic64",
    :ram => 1024,
    :cpu => 1 
  },
  {
    :hostname => "ubuntu2004",
    :ip => "192.168.56.204",
    :box => "hashicorp/focal64",
    :ram => 1024,
    :cpu => 1
  },
  {
    :hostname => "ubuntu2204",
    :ip => "192.168.56.224",
    :box => "hashicorp/jammy64",
    :ram => 1024,
    :cpu => 1 
  },
  {
    :hostname => "ubuntu2404",
    :ip => "192.168.56.244",
    :box => "hashicorp/noble64",
    :ram => 1024,
    :cpu => 1 
  },  
]

Vagrant.configure(2) do |config|
  servers.each do |machine|
      config.vm.define machine[:hostname] do |node|
          node.vm.box = machine[:box]
          node.vm.hostname = machine[:hostname]
          node.vm.network "private_network", ip: machine[:ip]
          config.disksize.size = '10GB'
          node.vm.provider "virtualbox" do |vb|
              vb.customize ["modifyvm", :id, "--memory", machine[:ram]]
          end
      end
  end
end
