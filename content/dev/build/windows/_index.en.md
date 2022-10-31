---
title: Windows
weight: 20
---

## Dependencies

### C++ build environment

Download [msvc](https://visualstudio.microsoft.com/) and install.

### Rust develop environment
Download [rustup-init.exe](https://static.rust-lang.org/rustup/dist/x86_64-pc-windows-msvc/rustup-init.exe) and install.

### vcpkg

Use [git-bash](https://git-scm.com/download/win) to run the following commands， download `vcpkg`, install `libvpx`, `libyuv`, `opus`.

```shell
  git clone https://github.com/microsoft/vcpkg
  vcpkg/bootstrap-vcpkg.bat
  export VCPKG_ROOT=$PWD/vcpkg
  vcpkg/vcpkg install libvpx:x64-windows-static libyuv:x64-windows-static opus:x64-windows-static
```

Add environment variable `VCPKG_ROOT`=`<path>\vcpkg`.

![](/docs/en/dev/build/windows/images/env.png)

### sciter

Desktop versions use [sciter](https://sciter.com/) for GUI, please download [sciter.dll](https://raw.githubusercontent.com/c-smile/sciter-sdk/master/bin.win/x64/sciter.dll)

### llvm

rust-bindgen depends on clang,  download [llvm](https://github.com/llvm/llvm-project/releases) and install，add environment variable `LIBCLANG_PATH`=`<llvm_install_dir>/bin`.



## Build

### Default

```sh
git clone https://github.com/rustdesk/rustdesk
cd rustdesk
mkdir -p target/debug
mv sciter.dll target/debug
cargo run
```
