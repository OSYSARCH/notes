# Notes



## Howto check virtualisation type

From: https://www.baeldung.com/linux/determine-virtualization-tech

`sudo dmidecode -s system-product-name`
`sudo lshw -class system`
`systemd-detect-virt`
`hostnamectl`


### Examples
```
sudo dmidecode -s system-product-name
H87-D3H

sudo dmidecode -s system-product-name
VirtualBox

sudo dmidecode -s system-product-name
KVM

sudo dmidecode -s system-product-name
VMware Virtual Platform

sudo lshw -class system
yk-arch                     
    description: Desktop Computer
    product: H87-D3H (To be filled by O.E.M.)
    vendor: Gigabyte Technology Co., Ltd.
    version: To be filled by O.E.M.
    serial: To be filled by O.E.M.
    width: 64 bits
    capabilities: smbios-2.7 dmi-2.7 smp vsyscall32
    configuration: administrator_password=disabled boot=normal ...

sudo lshw -class system
myVbox.test                     
    description: Computer
    product: VirtualBox
    vendor: Oracle
    version: 1.2
    serial: 0
    width: 64 bits
    capabilities: smbios-2.5 dmi-2.5 smp vsyscall32
    configuration: family=Virtual Machine uuid=......

sudo lshw -class system
myKvm.test                     
    description: Computer
    product: KVM
    vendor: Red Hat
    version: 1.2
    serial: 0
    width: 64 bits
    capabilities: smbios-2.4 dmi-2.4 smp vsyscall32
    configuration: family=Virtual Machine uuid=......

 sudo lshw -class system
myVmware.test                     
    description: Computer
    product: VMware Virtual Platform
    vendor: VMware, Inc.
    version: 1.2
    serial: 0
    width: 64 bits
    capabilities: smbios-2.4 dmi-2.4 smp vsyscall32
    configuration: family=Virtual Machine uuid=......

 systemd-detect-virt
none

systemd-detect-virt
oracle

systemd-detect-virt
kvm

systemd-detect-virt
vmware

systemd-detect-virt --list
none
kvm
qemu
bochs
xen
uml
vmware
oracle
microsoft
...

hostnamectl
   Static hostname: YK-Arch
         Icon name: computer-desktop
           Chassis: desktop
        Machine ID: d0fdfacb84184cee9507e0e1ac518e73
           Boot ID: 9f88561ec0864abfa51575e8ec74732f
  Operating System: Arch Linux
            Kernel: Linux 5.7.9-arch1-1
      Architecture: x86-64

hostnamectl
   Static hostname: myVbox.test
         Icon name: computer-vm
           Chassis: vm
        Machine ID: b4998efc50ae499881b024c258934223
           Boot ID: f885614223a240b3b3b04cef3a934f18
    Virtualization: oracle
  Operating System: CentOS Linux 7 (Core)
            Kernel: Linux 3.10.0-514.10.2.el7.x86_64
      Architecture: x86-64

hostnamectl
   Static hostname: myKvm.test
         Icon name: computer-vm
           Chassis: vm
        Machine ID: 55296cb0566a4aaca10b8e3a4b28b432
           Boot ID: 1bb259b0eb064d9eb8a22d112211b334
    Virtualization: kvm
  Operating System: Ubuntu 19.10
            Kernel: Linux 5.3.0-59-generic
      Architecture: x86-64


```
