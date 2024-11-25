Vagrant.configure("2") do |config|
  config.vm.box = "ictpinu82/ubuntu24.04lts"

  # Set a static IP address for your VM (ensure it's within your local network range)
  config.vm.network "private_network", type: "dhcp", ip: "192.168.33.10"  # Example static IP

  # Forward HTTP (port 80) and HTTPS (port 443) to the VM
  config.vm.network "forwarded_port", guest: 80, host: 8080   # HTTP
  config.vm.network "forwarded_port", guest: 443, host: 8443  # HTTPS (if needed)

  # Provision the VM with a shell script (or ansible) to deploy the app
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "deploy_django.yml"
  end
end
