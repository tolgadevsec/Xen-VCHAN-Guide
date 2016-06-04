# Xen VCHAN Guide

Tested on:
* Ubuntu 16.04 64-Bit (Dom0)
* Debian 8 64-Bit (DomU)
* Xen 4.6.0

## Building and Installing Xen Tools

Do not forget to build the dependencies first:
http://wiki.xenproject.org/wiki/Compiling_Xen_From_Source#Build_Dependencies

```
make build-tools
make install-tools
```

## Run Xen VCHAN examples

The following example is taken from here:
http://lists.xenproject.org/archives/html/xen-users/2014-01/msg00162.html

### Server-VM

Run the following:
```
/xen-4.6.0/tools/libvchan/$ sudo ./vchan-node1 server read 0 data/vchan
```

### Client-VM

Run the following:
```
/xen-4.6.0/tools/libvchan/$ sudo ./vchan-node1 client write 0 /local/domain/0/data/vchan
```

![Example](https://github.com/tolgauen/Xen-VCHAN-Guide/blob/master/xen-vchan.png)
