Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"
  config.vm.network "forwarded_port", guest: 8080, host: 8484
  config.vm.synced_folder ".", "/home/vagrant/sync", disabled: true
  config.vm.provision :shell, path: "bootstrap.sh"
  config.vm.provision :file, source: "target/spring-petclinic-2.2.0.BUILD-SNAPSHOT.jar", destination: "/tmp/spring-petclinic-2.2.0.BUILD-SNAPSHOT.jar", run:"always"
  config.vm.provision :shell, inline: "java -jar /tmp/spring-petclinic-2.2.0.BUILD-SNAPSHOT.jar &", run:"always"
end