# Prerequisite:

- Unix-type OS
- [Packer](http://www.packer.io/downloads.html)
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

# Usage:

Validate Packer template:

```sh
$ packer validate template.json
Template validated successfully.
```

Build Packer template:

```sh
$ packer build template.json
```

Packer will download the VirtualBox Guest Additions ISO as well as the CentOS minimal ISO prior to building the virtual machine.
