Vagrant.configure("2") do |config|
  config.vm.box = "peru/ubuntu-14.04-server-amd64"

  config.vm.define "vmMysql" do |vmbanco|
     vmbanco.vm.network "private_network", ip: "192.168.122.10"
    #vmbanco.vm.synced_folder "./configs", "/configs"
    vmbanco.vm.synced_folder ".", "/vagrant", disabled: true
    vmbanco.vm.provider "libvirt" do |vb|
      vb.memory = 1024
      vb.cpus = 2
    end

  end

   config.vm.define "wordpress" do |wordpress|
      wordpress.vm.network "public_network"
      wordpress.vm.network "private_network", ip: "192.168.122.11"
      #wordpress.vm.synced_folder "./configs", "/configs"
      wordpress.vm.synced_folder ".", "/vagrant", disabled: true
      wordpress.vm.provider "libvirt" do |vb|
        vb.memory = 1024
        vb.cpus = 2
      end

   end
end
