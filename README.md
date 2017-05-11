# budget_app
A refactor of the budget app, to be built on Laravel and optimized for mobile devices.

## Localhost Setup
1. Install vagrant

1. Pull in Homestead via composer: 
 1. `cd ~/path/to/this/repo/`
 1. `composer require laravel/homestead --dev`

1. Add budget.app to hosts:
 1. `vi /etc/hosts`
 1. Add line to hosts file: `127.0.0.1 budget.app`
 
1. Map budget app path to the VM: 
 1. `vi Homestead.yaml`
 2. Change the "map:" line to your local budget app path
 
1. Bring up the VM:
 1. `vagrant up`
 
1. Verify budget app loads:
 1. http://budget.app:8000
 
1. Code can be accessed from inside the VM with:
 1. `vagrant ssh`
 1. Once inside VM: `cd /vagrant`
 
### Troubleshooting

####"No input file specified" message

This happens when you're Homestead.yaml "to:" paths do not match up to the path to your code from inside the VM. So if your Homestead.yaml `sites: to:` entry is `/vagrant/public`, you should be able to `vagrant ssh` into the VM, and `ls /vagrant/public` and see an index.php file.