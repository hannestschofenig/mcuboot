# Introduction

This is an experimental self-hosted MCUBOOT session that runs on a standard PC.
It emulates flash via RAM and `memcpy`. It is for testing purposes.

# Building

First, clone the repository via: 


```
% git clone --recurse-submodules https://github.com/eembc/mcuboot.git
% cd mcuboot
```

Next, build mbedtls.

```
% cd ext/mbedtls
% mkdir build
% cd build
% cmake ..
% make
% cd ../../..
```

This will create `libmbedcrypto.a` under `build/library`, which is referenced
in `CMakeFiles.txt` of the selfhostest Mcuboot directory.

Now build the `selfhosted` example:

```
% cd boot/selfhosted
% mkdir build
% cd build
% cmake ..
% make
% ./bootme
```

