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

# Notes:

The `packer_cache` directory is used to store downloaded ISOs. You may want to place a local version of an ISO in this directory and create symlinks to the various URLs used to retrieve the ISO. The filename is simply a SHA256 hash of the URL.

Example: Calculate cache filename based on SHA256 hash

URL: `http://centos.gravityfish.com/6/isos/x86_64/CentOS-6.5-x86_64-minimal.iso`

```sh
$ cd packer_cache
$ echo -n "http://centos.gravityfish.com/6/isos/x86_64/CentOS-6.5-x86_64-minimal.iso" | openssl sha256
(stdin)= 56ba30f9f920b6ab6082bc8520368e278eafedccccbba2af6eb8d85445ca4aa9
$ ln -s CentOS-6.5-x86_64-minimal.iso 56ba30f9f920b6ab6082bc8520368e278eafedccccbba2af6eb8d85445ca4aa9.iso
```

For reference:

```sh
$ echo -n "http://download.virtualbox.org/virtualbox/4.3.6/VBoxGuestAdditions_4.3.6.iso" | openssl sha256
(stdin)= f87be3a86ef0ad0b827a59806c87425c162190cb9dab8df9ea60030a344a9016
```
