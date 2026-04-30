# Packer Fedora 44

This box is based on the initial Fedora 44 release.

Get the Packer software.

* [https://www.packer.io/downloads](https://www.packer.io/downloads)

To build the VirtualBox box add the Packer software to your path, switch to the root of the Packer build directory and run the Packer command. Amend your paths as needed.

```
set PATH=%USERPROFILE%\u01\software\hashicorp\packer_1.15.3_windows_amd64;%PATH%
cd \git\oraclebase\vagrant\packer\f44

packer build -only virtualbox-iso f44.json
```

This will create a box called "f44-x86_64-virtualbox.box" in the "build" directory.

You can then upload the resulting box to Vagrant Cloud, or just use it locally by adding it to you local box list.

```
vagrant box remove oraclebase/fedora-44
vagrant box add build/f44-x86_64-virtualbox.box --name oraclebase/fedora-44
```
