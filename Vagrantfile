Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 3
  end
  config.vm.box = "mrvantage/centos7-minikube"
  config.vm.network "private_network", ip: "192.168.33.33"

  config.vm.provision "shell", privileged: true, inline: <<-EOF
    yum install -y git
    git clone https://github.com/nygamichal/K8S.git
    cd K8S/vote-app
    sh 01_run-vote-app.sh
  EOF
end
