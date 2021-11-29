# An out-of-tree MLIR dialect

This is an example of an out-of-tree [MLIR](https://mlir.llvm.org/) dialect along with a standalone `opt`-like tool to operate on that dialect.

## Building

This setup assumes that you have built LLVM and MLIR in `$BUILD_DIR` and installed them to `$PREFIX`. To build and launch the tests, run
```sh
mkdir build && cd build
cmake -G Ninja .. -DMLIR_DIR=$PREFIX/lib/cmake/mlir -DLLVM_EXTERNAL_LIT=$BUILD_DIR/bin/llvm-lit
cmake --build . --target check-standalone
```
To build the documentation from the TableGen description of the dialect operations, run
```sh
cmake --build . --target mlir-doc
```
**Note**: Make sure to pass `-DLLVM_INSTALL_UTILS=ON` when building LLVM with CMake in order to install `FileCheck` to the chosen installation prefix.

˵���� 
* `$BUILD_DIR`��llvm��Ŀ�ı���·�������磺${YOUR_GIT_CLONE_PATH}/llvm-project/build/
* `$PREFIX`��llvm��װ·��������ڱ��밲װllvmʱͨ��cmake��`cmake_install_prefix`ָ����װ·���Ļ������Ǹ�·��������ΪĬ��ֵ��һ����`/usr/local/`.