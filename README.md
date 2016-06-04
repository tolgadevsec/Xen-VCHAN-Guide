# Xen vchan Guide

Tested on:
* Ubuntu 16.04 64-Bit (Dom0)
* Debian 8 64-Bit (DomU)
* Xen 4.6.0

## Building and installing Xen tools

Do not forget to build the dependencies first:
http://wiki.xenproject.org/wiki/Compiling_Xen_From_Source#Build_Dependencies

```
make build-tools
make install-tools
```

## Run Xen vchan examples

The following example is taken from here:
http://lists.xenproject.org/archives/html/xen-users/2014-01/msg00162.html

Load the following Xen kernel modules on both VMs:
```
$ sudo modprobe xen-evtchn
$ sudo modprobe xen-gntalloc
$ sudo modprobe xen-gntdev
```
In the following example, the Client-VM has the Domain ID 1 and the 
Server-VM the Domain ID 0. 

### Server-VM

Run the following:
```
/xen-4.6.0/tools/libvchan/$ sudo ./vchan-node1 server read 1 data/vchan
```

### Client-VM

Run the following:
```
/xen-4.6.0/tools/libvchan/$ sudo ./vchan-node1 client write 0 /local/domain/0/data/vchan
```

![Example](https://github.com/tolgauen/Xen-VCHAN-Guide/blob/master/xen-vchan.png)

## Projects/Code using the Xen vchan protocol
* ocaml-vchan - https://github.com/mirage/ocaml-vchan
* vchan-aes - https://github.com/tklengyel/vchan-aes
* Qubes OS - http://blog.invisiblethings.org/2015/10/01/qubes-30.html
