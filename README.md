node_pi
=======

two binary images of nodejs 0.8.4 for raspian

both images are compiled with hardfloats

but only the _hard image is compiled using the vfp2 patch which enables the usage of float instructions by v8 improoving the run time of 'make test' xx%.


downloads
---------

https://github.com/downloads/sebseb7/node_pi/node_hard.tar.gz

https://github.com/downloads/sebseb7/node_pi/node_soft.tar.gz


build instructions
------------------


```
nodejs build for raspberry pi with vfp2 supportexport GYP_DEFINES="armv7=0"
export CXXFLAGS='-march=armv6 -mfpu=vfp -mfloat-abi=hard -DUSE_EABI_HARDFLOAT'
export CCFLAGS='-march=armv6 -mfpu=vfp -mfloat-abi=hard -DUSE_EABI_HARDFLOAT'
./configure --shared-openssl --without-snapshot
make
```