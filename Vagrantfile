# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define "master1", primary: true do |master1|
    master1.vm.box = "centos/7"
    master1.vm.network "private_network", ip: "172.29.1.10"
    master1.vm.provision "shell", inline: <<-SHELL
      hostnamectl set-hostname master1
      yum -y update
      rpm --import https://artifacts.elastic.co/GPG-KEY-elasticsearch
      cat <<-EOF >/etc/yum.repos.d/elasticsearch.repo
#{File.read(File.expand_path('./config/elasticsearch.repo'))}
EOF
      yum install -y elasticsearch-oss
      cat <<-EOF > /etc/elasticsearch/elasticsearch.yml
#{File.read(File.expand_path('./config/master1.elasticsearch.yml'))}
EOF
      systemctl daemon-reload
      systemctl enable elasticsearch.service
      systemctl restart elasticsearch.service
    SHELL
  end

  config.vm.define "data1" do |data1|
    data1.vm.box = "centos/7"
    data1.vm.network "private_network", ip: "172.29.1.20"
    data1.vm.provision "shell", inline: <<-SHELL
      hostnamectl set-hostname data1
      yum -y update
      rpm --import https://artifacts.elastic.co/GPG-KEY-elasticsearch
      cat <<-EOF >/etc/yum.repos.d/elasticsearch.repo
#{File.read(File.expand_path('./config/elasticsearch.repo'))}
EOF
      yum install -y elasticsearch-oss
      cat <<-EOF > /etc/elasticsearch/elasticsearch.yml
#{File.read(File.expand_path('./config/data1.elasticsearch.yml'))}
EOF
      systemctl daemon-reload
      systemctl enable elasticsearch.service
      systemctl restart elasticsearch.service
    SHELL
  end

  config.vm.define "data2" do |data2|
    data2.vm.box = "centos/7"
    data2.vm.network "private_network", ip: "172.29.1.30"
    data2.vm.provision "shell", inline: <<-SHELL
      hostnamectl set-hostname data2
      yum -y update
      rpm --import https://artifacts.elastic.co/GPG-KEY-elasticsearch
      cat <<-EOF >/etc/yum.repos.d/elasticsearch.repo
#{File.read(File.expand_path('./config/elasticsearch.repo'))}
EOF
      yum install -y elasticsearch-oss
      cat <<-EOF > /etc/elasticsearch/elasticsearch.yml
#{File.read(File.expand_path('./config/data2.elasticsearch.yml'))}
EOF
      systemctl daemon-reload
      systemctl enable elasticsearch.service
      systemctl restart elasticsearch.service
    SHELL
  end

end
