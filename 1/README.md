```
$ git clone git@github.com:llvm/llvm-project.git --depth=1 
$ cmake -B build/ -G "Visual Studio 16 2019" -A x64 -T host=x64 -DLLVM_TARGETS_TO_BUILD=X86
$ cmake --build build/
$ ./build/Debug/main.exe
```
