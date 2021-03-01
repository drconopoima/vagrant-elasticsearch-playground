# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define "master1", primary: true do |master1|
    master1.vm.box = "centos/7"
    master1.vm.provision "shell", inline: <<-SHELL
      hostnamectl set-hostname master1
      yum -y update
      rpm --import https://artifacts.elastic.co/GPG-KEY-elasticsearch
      cat <<-EOF >/etc/yum.repos.d/elasticsearch.repo
[elasticsearch-7.x]
name=Elasticsearch repository for 7.x packages
baseurl=https://artifacts.elastic.co/packages/oss-7.x/yum
gpgcheck=1
gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch
enabled=1
autorefresh=1
type=rpm-md
EOF
      yum install -y elasticsearch-oss
      systemctl daemon-reload
      systemctl enable elasticsearch.service
      systemctl start elasticsearch.service
    SHELL
  end

  config.vm.define "data1" do |data1|
    data1.vm.box = "centos/7"
    data1.vm.provision "shell", inline: <<-SHELL
      hostnamectl set-hostname data1
      yum -y update
      rpm --import https://artifacts.elastic.co/GPG-KEY-elasticsearch
      cat <<-EOF >/etc/yum.repos.d/elasticsearch.repo
[elasticsearch-7.x]
name=Elasticsearch repository for 7.x packages
baseurl=https://artifacts.elastic.co/packages/oss-7.x/yum
gpgcheck=1
gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch
enabled=1
autorefresh=1
type=rpm-md
EOF
      yum install -y elasticsearch-oss
      systemctl daemon-reload
      systemctl enable elasticsearch.service
      systemctl start elasticsearch.service
    SHELL
  end

  config.vm.define "data2" do |data2|
    data2.vm.box = "centos/7"
    data2.vm.provision "shell", inline: <<-SHELL
      hostnamectl set-hostname data2
      yum -y update
      rpm --import https://artifacts.elastic.co/GPG-KEY-elasticsearch
      cat <<-EOF >/etc/yum.repos.d/elasticsearch.repo
[elasticsearch-7.x]
name=Elasticsearch repository for 7.x packages
baseurl=https://artifacts.elastic.co/packages/oss-7.x/yum
gpgcheck=1
gpgkey=https://artifacts.elastic.co/GPG-KEY-elasticsearch
enabled=1
autorefresh=1
type=rpm-md
EOF
      yum install -y elasticsearch-oss
      systemctl daemon-reload
      systemctl enable elasticsearch.service
      systemctl start elasticsearch.service
    SHELL
  end

end
