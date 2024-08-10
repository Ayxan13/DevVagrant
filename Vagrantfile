Vagrant.configure("2") do |config|
  config.vm.box = "debian/bookworm64"
  config.vm.network "private_network", ip: "192.168.56.43"
  config.vm.provider "libvirt" do |v|
    v.memory = 8162
    v.cpus = 4
  end

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y build-essential ninja-build git vim fish kmod clangd linux-headers-$(uname -r)
    chsh -s $(which fish) vagrant
  SHELL
end

