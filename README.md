vagrant-salt-masterless-boilerplate
===================================

Salt masterless starter kit for Vagrant

Install
-------
1. Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
2. Install [Vagrant](http://vagrantup.com/), either [by package](http://downloads.vagrantup.com/) or `gem install vagrant`
3. Write some states!
4. `vagrant up`

Development
-----------

* Define states as shown in the [Salt Masterless Quickstart](http://docs.saltstack.com/en/latest/topics/tutorials/quickstart.html#salt-masterless-quickstart).
* Pillars can be used by states as shown in [Pillar Walkthrough](http://docs.saltstack.com/en/latest/topics/tutorials/pillar.html). This project expects pillar files at `states/pillar` which should be managed by another repo.
* Formulas can be used by states as shown in [Salt Formulas](http://docs.saltstack.com/en/latest/topics/development/conventions/formulas.html). GitFS does not work with masterless salt yet [saltstack/salt#6660](https://github.com/saltstack/salt/issues/6660), so install them to `states/formulas` using [Adding a Formula directory manually](http://docs.saltstack.com/en/latest/topics/development/conventions/formulas.html#adding-a-formula-directory-manually).

Notes
-----
* Vagrant's salt provisioner has some [logging issues](https://github.com/mitchellh/vagrant/issues/3754). Set `salt.verbose = true` to get output from `salt.highstate` and `salt.log_level = "info"` to limit that output.
* All files in `states` are copied to `/srv` on your VM, the default salt states location. 
