ec2-gentoo-kernels
==================

* Update to latest kernel (as root)

```bash 
$ KER_VER=$(curl -sk 'https://github.com/pigfoot/ec2-gentoo-kernels/releases' | sed -rn 's@^.*"\/pigfoot\/ec2-gentoo-kernels\/releases\/download\/v([[:digit:].]+)/kernel-genkernel-x86_64-([[:digit:].]+)-gentoo\.tar\.xz".*$@\1@p' | sort -t. -k 1,1n -k 2,2n -k 3,3n -k 4,4n | sed '$!d')
$ KER_URL="https://github.com/pigfoot/ec2-gentoo-kernels/releases/download/v${KER_VER}/kernel-genkernel-x86_64-${KER_VER}-gentoo.tar.xz"
$ pushd /
$ curl -sLk ${KER_URL} | tar -Jxvf -
$ popd
```
