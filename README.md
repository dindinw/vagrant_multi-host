vagrant_multi-host
==================

The vagrant dev enviorment for supporting multiple machines.

## Usage

Start all vm

    vagrant up

Start a vm by name

    vagrant up <host_name>
    vagrant up host1

Provision all or by vm name

    vagrant provision host1
    vagarnt provision

## Executing Log

```
   vagrant up
   Bringing machine 'host1' up with 'virtualbox' provider...
   Bringing machine 'host2' up with 'virtualbox' provider...
   [host1] Importing base box 'precise64'...
   [host1] Matching MAC address for NAT networking...
   [host1] Setting the name of the VM...
   [host1] Clearing any previously set forwarded ports...
   [host1] Fixed port collision for 22 => 2222. Now on port 2200.
   [host1] Clearing any previously set network interfaces...
   [host1] Preparing network interfaces based on configuration...
   [host1] Forwarding ports...
   [host1] -- 22 => 2200 (adapter 1)
   [host1] Running 'pre-boot' VM customizations...
   [host1] Booting VM...
   [host1] Waiting for machine to boot. This may take a few minutes...
   DL is deprecated, please use Fiddle
   [host1] Machine booted and ready!
   [host1] The guest additions on this VM do not match the installed version of
   VirtualBox! In most cases this is fine, but in rare cases it can
   cause things such as shared folders to not work properly. If you see
   shared folder errors, please make sure the guest additions within the
   virtual machine match the version of VirtualBox you have installed on
   your host and reload your VM.

   Guest Additions Version: 4.2.0
   VirtualBox Version: 4.3
   [host1] Setting hostname...
   [host1] Configuring and enabling network interfaces...
   [host1] Mounting shared folders...
   [host1] -- /vagrant
   [host1] Running provisioner: shell...
   [host1] Running: inline script
   stdin: is not a tty
   Begin excuting the provsion script for host1
   Linux mylab-host1 3.2.0-23-generic #36-Ubuntu SMP Tue Apr 10 20:39:51 UTC 2012 x86_64 x86_64 x86_64 GNU/Linux
   called from mylab-host1
   ok!
   End excuting the provsion script for host1
   [host2] Importing base box 'precise64'...
   [host2] Matching MAC address for NAT networking...
   [host2] Setting the name of the VM...
   [host2] Clearing any previously set forwarded ports...
   [host2] Fixed port collision for 22 => 2200. Now on port 2201.
   [host2] Clearing any previously set network interfaces...
   [host2] Preparing network interfaces based on configuration...
   [host2] Forwarding ports...
   [host2] -- 22 => 2201 (adapter 1)
   [host2] Running 'pre-boot' VM customizations...
   [host2] Booting VM...
   [host2] Waiting for machine to boot. This may take a few minutes...
   [host2] Machine booted and ready!
   [host2] The guest additions on this VM do not match the installed version of
   VirtualBox! In most cases this is fine, but in rare cases it can
   cause things such as shared folders to not work properly. If you see
   shared folder errors, please make sure the guest additions within the
   virtual machine match the version of VirtualBox you have installed on
   your host and reload your VM.

   Guest Additions Version: 4.2.0
   VirtualBox Version: 4.3
   [host2] Setting hostname...
   [host2] Configuring and enabling network interfaces...
   [host2] Mounting shared folders...
   [host2] -- /vagrant
   [host2] Running provisioner: shell...
   [host2] Running: inline script
   stdin: is not a tty
   Begin excuting the provsion script for host2
   called from mylab-host2
   End excuting the provsion script for host2
```

