# vim: set ft=ruby:
Vagrant.configure("2") do |config|
  # centos 7
  config.vm.define "centos-7" do |centos|
    centos.vm.hostname = "centos-7.local"
    centos.vm.box = "bento/centos-7.3"
    config.vm.provision "shell", inline: <<-SHELL
      yum install -y -q \
        https://yum.puppetlabs.com/puppetlabs-release-pc1-el-7.noarch.rpm \
        2>&1 > /dev/null
      yum install -y -q epel-release puppet-agent git 2>&1 > /dev/null
      echo "PATH=/vagrant:$PATH" >> /root/.bashrc
      rm -rf /etc/puppetlabs/code/environments/production
      ln -s /vagrant/ /etc/puppetlabs/code/environments/production
    SHELL
  end

  # centos 6
  config.vm.define "centos-6" do |centos|
    centos.vm.hostname = "centos-6.local"
    centos.vm.box = "bento/centos-6.9"
    config.vm.provision "shell", inline: <<-SHELL
      yum install -y -q \
        https://yum.puppetlabs.com/puppetlabs-release-pc1-el-6.noarch.rpm \
        2>&1 > /dev/null
      yum install -y -q epel-release puppet-agent git 2>&1 > /dev/null
      echo "PATH=/vagrant:$PATH" >> /root/.bashrc
      rm -rf /etc/puppetlabs/code/environments/production
      ln -s /vagrant/ /etc/puppetlabs/code/environments/production
   SHELL
  end

  # ubuntu 16.04
  config.vm.define "ubuntu-16.04" do |ubuntu|
    ubuntu.vm.hostname = "ubuntu-1604.local"
    ubuntu.vm.box = "bento/ubuntu-16.04"
    ubuntu.vm.provision "shell", inline: <<-SHELL
      curl -so /tmp/puppetlabs-release-pc1-xenial.deb \
        https://apt.puppetlabs.com/puppetlabs-release-pc1-xenial.deb
      dpkg -i /tmp/puppetlabs-release-pc1-xenial.deb 2>&1 > /dev/null
      apt-get update 2>&1 > /dev/null
      apt-get install -qq puppet-agent git 2>&1 > /dev/null
      echo "PATH=/vagrant:$PATH" >> /root/.bashrc
      rm -rf /etc/puppetlabs/code/environments/production
      ln -s /vagrant/ /etc/puppetlabs/code/environments/production
   SHELL
  end

end
