# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "web" do |web|
    web.vm.box = "heroku"
    web.vm.box_url = "https://dl.dropboxusercontent.com/s/rnc0p8zl91borei/heroku.box"
    web.vm.network :forwarded_port, guest: 3030, host: 3030
    web.vm.synced_folder "app", "/vagrant"
    web.vm.provision "shell", path: "bootstrap.sh", privileged: false
  end

  config.vm.define "redis" do |redis|
    redis.vm.box = "heroku"
    redis.vm.box_url = "https://dl.dropboxusercontent.com/s/rnc0p8zl91borei/heroku.box"
    redis.vm.network :forwarded_port, guest: 6379, host: 6379
    redis.vm.provision "chef_solo" do |chef|
      chef.add_recipe "ulimit"
      chef.add_recipe "redisio::install"
      chef.add_recipe "redisio::enable"
    end
  end

end
