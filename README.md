# AnsibleWebFarm

Es un despliegue de una Granja Web escalable horizontalmente con Vagrant y Ansible. Quedando como despliegue de IaC Ifraestructure as Code como en la imagen.

![vagrant6](https://user-images.githubusercontent.com/64685260/174110243-de33bc97-7352-41c6-94f8-34bc964ad86e.png)


## Requisitos de instalación para Vagrant: 

``` console
$ curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
$ sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
$ sudo apt-get update && sudo apt-get install vagrant
```

## Requisitos de instalación para libvirt de proveedor Vagrant: 

``` console
$ sudo apt-get build-dep vagrant ruby-libvirt
$ sudo apt-get install qemu libvirt-daemon-system libvirt-clients ebtables dnsmasq-base
$ sudo apt-get install libxslt-dev libxml2-dev libvirt-dev zlib1g-dev ruby-dev
$ sudo apt-get install libguestfs-tools
```
