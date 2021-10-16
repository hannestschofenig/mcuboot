# Introduction

This is an experimental, self-hosted Mcuboot version that runs on a standard PC.
It emulates flash via RAM and `memcpy`. It is for testing purposes.

# Building

First, clone the Mcuboot repository via: 

```
% git clone --recurse-submodules https://github.com/eembc/mcuboot.git
% cd mcuboot
% make generated_files
```

Next, build MbedTLS.

```
% cd ext/mbedtls
% mkdir build
% cd build
% cmake ..
% make
% cd ../../..
```

These commands will create `libmbedcrypto.a` under `build/library`, which is referenced
in `CMakeFiles.txt` of the selfhosted example app.

Finally, build the selfhosted example app called 'bootme':

```
% cd boot/selfhosted
% mkdir build
% cd build
% cmake ..
% make
% ./bootme
```

