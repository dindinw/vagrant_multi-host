# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # Every Vagrant virtual environment requires a box to build off of.
  config.vm.box = "precise64"
  [ { 'devstack' => 
        { 'memory' => 512,
          # can't use ip .1, beacuase the ip is reservced for the v-net
          'ip' => '172.20.0.2',
          'script' => '
           uname -a
           echo "called from $(hostname)"
           echo "ok!"
           ' 
        }
    } ,
    { 'nova' => 
        { 'memory' => 2048,
          'ip' => '172.20.0.3',
          'script' => '
           echo "called from $(hostname)"
          '
        }
    } 
  ].each do |conf|
    name = conf.keys.first
    settings = conf.values.first
    config.vm.define name.intern do |host|
        host.vm.host_name = "mylab-#{name}"
        host.vm.network :private_network, ip: settings['ip']
        host.vm.provider :virtualbox do |vb|
            vb.customize ["modifyvm", :id, "--memory", settings['memory'] || 1024 ]
        end
        host.vm.provision :shell, :inline => <<-SCRIPT
        echo "Begin excuting the provsion script for #{name}"
        #{settings['script']}
        echo "End excuting the provsion script for #{name}"
        SCRIPT

    end
  end
end
