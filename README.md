# Vagrant Puppet Dev Environment

This is a simple vagrant project that can be used when developing Puppet modules, or testing Puppet manifests.

It currently supports the following operating systems:

  * CentOS 6
  * CentOS 7
  * Ubuntu 16.04

### Usage

Once you clone this repository, simply `vagrant up` the operating system you want to test.  The puppet-release-pc1 repository is installed, along with puppet-agent.

Once the target vm is up, `vagrant ssh` to it and switch to root (i.e `sudo -i` or similar). From there, you should be able to us `pa /path/to/manifest` to run `puppet apply` using the given manifest.

### Hiera

You can use hiera by creating a file named 'common.yaml' in the hiera directory, and placing your hiera values in there. The `pa` script uses a hiera configuration that will search for the file as the sole hiera backend.

### Modules

You can place all modules you want to be available to manifests in the modules directory.  The contents of this directory are excluded in the gitignore file.
