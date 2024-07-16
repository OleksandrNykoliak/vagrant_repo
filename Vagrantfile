Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/bionic64"
    config.vm.network "private_network", ip: "192.168.50.4"

    config.vm.provision "shell", inline: <<-SHELL
        apt-get update
        apt-get install -y python3 python3-pip
        pip3 install virtualenv Django 
    SHELL 

    config.vm.provision "shell", inline: <<-SHELL
        mkdir /vagrant/django_app
        cd /vagrant/django_app
        virtualenv venv
        source venv/bin/activate
        pip install Django
    SHELL
end
