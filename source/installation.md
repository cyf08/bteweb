# 3. Installation


## 3.1 Requirement

- C++ compiler (gcc is recommended)
- Cmake
- MPI library (openmpi is recommended)
- Linux environment is recommended
 
 
## 3.2 Install and compile

### Step 1. Install all required packages

All packages are widely used packages. The installation of these packages can be easily found in web.

**Ensure that the C++ compiler is installed**

Type in command line

`$ g++ -v`

Correct output like:

`gcc version x.x.x xxxxxx`

**Ensure that the MPI library is installed**

Type in command line

`$ which mpirun`

Correct output like:

`/usr/bin/mpirun`

**Ensure that the Cmake is installed**

Type in command line

`$ which cmake`

Correct output like:

`$ /usr/bin/cmake`

### Step 2. Download source

You can download the package from the git repository as: [https://github.com/Gift-BTE-developer/Gift-BTE.git](https://github.com/Gift-BTE-developer/Gift-BTE.git)

`$ unzip GiftBTE-master.zip`

Or directly clone the repository by git (may need installation)

```
$ git clone https://github.com/Gift-BTE-developer/Gift-BTE.git
$ git Checkout master
```

### Step 3. Build by CMake

Type in the command line under the GiftBTE folder\

```
$ cd GiftBTE
$ cmake -B cpu-build -S.  -DCMAKE_BUILD_TYPE=Release
$ cd cpu-build
$ make
```

Correct output in command line

```
-- The CXX compiler identification is GNU 8.3.1
-- The C compiler identification is GNU 8.3.1
-- The Fortran compiler identification is GNU 8.3.1
-- Detecting CXX compiler ABI info
-- Detecting CXX compiler ABI info - done
-- Check for working CXX compiler: /usr/bin/c++ - skipped
-- Detecting CXX compile features
-- Detecting CXX compile features - done
-- Detecting C compiler ABI info
-- Detecting C compiler ABI info - done
-- Check for working C compiler: /usr/bin/cc - skipped
-- Detecting C compile features
-- Detecting C compile features - done
-- Detecting Fortran compiler ABI info
-- Detecting Fortran compiler ABI info - done
-- Check for working Fortran compiler: /usr/bin/gfortran - skipped
-- Checking whether /usr/bin/gfortran supports Fortran 90
-- Checking whether /usr/bin/gfortran supports Fortran 90 - yes
-- Found MPI_C: /dssg/opt/icelake/linux-centos8-icelake/gcc-8.3.1/openmpi-4.1.1-me4z4iiamxv3l6efci5wcmjd2pk4rvye/lib/libmpi.so (found version "3.1") 
-- Found MPI_CXX: /dssg/opt/icelake/linux-centos8-icelake/gcc-8.3.1/openmpi-4.1.1-me4z4iiamxv3l6efci5wcmjd2pk4rvye/lib/libmpi_cxx.so (found version "3.1") 
-- Found MPI_Fortran: /dssg/opt/icelake/linux-centos8-icelake/gcc-8.3.1/openmpi-4.1.1-me4z4iiamxv3l6efci5wcmjd2pk4rvye/lib/libmpi_usempif08.so (found version "3.1") 
-- Found MPI: TRUE (found version "3.1")  
-- Configuring done
-- Generating done
-- Build files have been written to: /dssg/home/acct-umjbh/umjbh-b/GiftBTE/cpu-build
[  3%] Building CXX object src/utility/CMakeFiles/BTEutility.dir/utility.cpp.o
[  7%] Linking CXX static library ../../../lib/libBTEutility.a
[  7%] Built target BTEutility
[ 11%] Building CXX object src/BTEAngle/CMakeFiles/BTEAngle.dir/BTEAngle.cpp.o
[ 15%] Linking CXX static library ../../../lib/libBTEAngle.a
[ 15%] Built target BTEAngle
[ 19%] Building CXX object src/BTEBand/CMakeFiles/BTEBand.dir/BTEBand.cpp.o
[ 23%] Linking CXX static library ../../../lib/libBTEBand.a
[ 23%] Built target BTEBand
[ 26%] Building CXX object src/BTEBoundaryCondition/CMakeFiles/BTEBoundaryCondition.dir/BTEBoundaryCondition.cpp.o
[ 30%] Linking CXX static library ../../../lib/libBTEBoundaryCondition.a
[ 30%] Built target BTEBoundaryCondition
[ 34%] Building CXX object src/BTEMesh/CMakeFiles/BTEMesh.dir/BTEMesh.cpp.o
[ 38%] Building CXX object src/BTEMesh/CMakeFiles/BTEMesh.dir/COMSOL.cpp.o
[ 42%] Building CXX object src/BTEMesh/CMakeFiles/BTEMesh.dir/oneD.cpp.o
[ 46%] Building CXX object src/BTEMesh/CMakeFiles/BTEMesh.dir/Distribute.cpp.o
[ 50%] Building CXX object src/BTEMesh/CMakeFiles/BTEMesh.dir/ReadinMesh.cpp.o
[ 53%] Linking CXX static library ../../../lib/libBTEMesh.a
[ 53%] Built target BTEMesh
[ 57%] Building CXX object src/StaticBTESynthetic/CMakeFiles/StaticBTESynthetic.dir/StaticBTESynthetic.cpp.o
[ 61%] Building CXX object src/StaticBTESynthetic/CMakeFiles/StaticBTESynthetic.dir/StaticBTESyntheticSolver.cpp.o
[ 65%] Linking CXX static library ../../../lib/libStaticBTESynthetic.a
[ 65%] Built target StaticBTESynthetic
[ 69%] Building CXX object src/StaticFourier/CMakeFiles/StaticFourier.dir/StaticFourier.cpp.o
[ 73%] Linking CXX static library ../../../lib/libStaticFourier.a
[ 73%] Built target StaticFourier
[ 76%] Building CXX object src/TransientBTE/CMakeFiles/TransientBTE.dir/transient.cpp.o
[ 80%] Building CXX object src/TransientBTE/CMakeFiles/TransientBTE.dir/TransientSolver.cpp.o
[ 84%] Linking CXX static library ../../../lib/libTransientBTE.a
[ 84%] Built target TransientBTE
[ 88%] Building CXX object src/Solution/CMakeFiles/Solution.dir/Solution.cpp.o
[ 92%] Linking CXX static library ../../../lib/libSolution.a
[ 92%] Built target Solution
[ 96%] Building CXX object src/CMakeFiles/BTE_CPU.dir/BTEMain.cpp.o
[100%] Linking CXX executable ../../bin/BTE_CPU
[100%] Built target BTE_CPU
```

An executable file BTE_CPU  is created in bin/

Common error:
- C++ compiler not found: the C++ compiler is not installed
- MPI not found: the MPI library is not installed
 
### Step 4. Run example

GiftBTE provides many examples under bin/examples. One can choose an example to test. For example: 

```
$ cd bin
$ cd examples
$ cd FinFET
$ cd 1e-7
$ mpirun -np 4 ../../../BTE_CPU
```