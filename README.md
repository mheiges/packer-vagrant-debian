
````
packer build x86_64-virtualbox-base.json
````

````
packer build x86_64-virtualbox-vagrant.json
````

```
vagrant box add file://builds/virtualbox/vagrant/debian-9-64/debian-9-64.box --name mheiges/debian-9-64 --force
```
