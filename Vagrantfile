VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
# General Vagrant VM configuration.
# config.vm.box = "ansible.box"
config.ssh.insert_key = false
config.vm.synced_folder ".", "/vagrant", disabled: true
config.vm.provider :virtualbox do |v|
v.memory = 512
v.linked_clone = true
end

# Ansible Controller
config.vm.define "controller" do |controller|
controller.vm.box = "centos/7"
controller.vm.hostname = "controller.test"
controller.vm.network :private_network, ip: "192.168.60.4"
controller.vm.synced_folder "/home/course_files", "/home/vagrant/ansible", type: "sshfs"
end
# LB 
config.vm.define "lb1" do |lb1|
lb1.vm.box = "centos/7"
lb1.vm.hostname = "lb1.test"
lb1.vm.network :private_network, ip: "192.168.60.5"
end
# Web server 1
config.vm.define "web1" do |web1|
web1.vm.box = "centos/7"
web1.vm.hostname = "web1.test"
web1.vm.network :private_network, ip: "192.168.60.6"
end
# Web server 2
config.vm.define "web2" do |web2|
web2.vm.box = "centos/7"
web2.vm.hostname = "web2.test"
web2.vm.network :private_network, ip: "192.168.60.7"
end
# Database server.
config.vm.define "db1" do |db1|
db1.vm.box = "centos/7"
db1.vm.hostname = "db1.test"
db1.vm.network :private_network, ip: "192.168.60.8"
end
end