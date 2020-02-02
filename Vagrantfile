$rootProvision = <<-SCRIPT
apt update
apt install -y python3-pip
SCRIPT

$userProvision = <<-SCRIPT
python3 -m pip install --upgrade virtualenv
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.synced_folder ".", "/home/vagrant/algo"
  config.vm.provision "shell", inline: $rootProvision, privileged: true
  config.vm.provision "shell", inline: $userProvision, privileged: false
end
