Vagrant.configure("2") do |config|
    config.vm.guest = :freebsd
    config.ssh.shell = "/bin/sh -"
    config.vm.box = "freebsd/FreeBSD-11.1-RELEASE"

    config.vm.base_mac = "080027A7C55B"

    config.vm.hostname = "ezjail-testhost.local"
    config.vm.synced_folder ".", "/vagrant", disabled: true

    config.vm.provider :virtualbox do |vb|
        vb.name = "vagrant_ansible_ezjail_test";
    end

    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook.yml"
      ansible.verbose = "vvvv"
    end
end
