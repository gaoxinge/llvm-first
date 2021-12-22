# llvm first

## msvc

One can use llvm/clang in msvc by visual studio, which can refer to [[1]](https://docs.microsoft.com/en-us/cpp/build/clang-support-cmake?view=msvc-170).

## prebuild

### official

Official prebuild can be found at [[2]](https://llvm.org/builds/)[[3]](https://releases.llvm.org/download.html#11.0.0). But it doesn't contain `llvm-config`.

### source code

One also can build llvm/clang from source code[[4]](https://llvm.org/docs/GettingStarted.html)[[5]](https://llvm.org/docs/CMake.html)[[6]](https://llvm.org/docs/GettingStartedVS.html)[[7]](https://zhuanlan.zhihu.com/p/150395572).

#### llvm

```
$ git clone git@github.com:llvm/llvm-project.git --depth=1
$ cmake -S llvm-project/llvm -B build/ -G "Visual Studio 16 2019" -A x64 -T host=x64 -DLLVM_TARGETS_TO_BUILD=X86
$ cmake --build build/ --config Release
$ cmake --install build/ --prefix install
```

#### clang

```
$ git clone git@github.com:llvm/llvm-project.git --depth=1
$ cmake -S llvm-project/clang -B build/ -G "Visual Studio 16 2019" -A x64 -T host=x64 -DLLVM_TARGETS_TO_BUILD=X86 -DLLVM_DIR=<llvm_install_dir>/lib/cmake/llvm
$ cmake --build build/ --config Release
$ cmake --install build/ --prefix install
```

#### llvm + clang

```
$ git clone git@github.com:llvm/llvm-project.git --depth=1
$ cmake -S llvm-project/llvm -B build/ -G "Visual Studio 16 2019" -A x64 -T host=x64 -DLLVM_TARGETS_TO_BUILD=X86 -DLLVM_ENABLE_PROJECTS=clang
$ cmake --build build/ --config Release
$ cmake --install build/ --prefix install
```
