```
$ cmake -B build/ -G "Visual Studio 16 2019" -A x64 -T host=x64 -DLLVM_TARGETS_TO_BUILD=X86 -DLLVM_DIR=<llvm_install_dir>/lib/cmake/llvm
$ cmake --build build/ --config Release
$ ./build/Release/main.exe
```
