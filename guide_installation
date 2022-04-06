## Pre-installation packages and libraries
PETSC (v3.12.3)\
OpenMPI\
mpi4py\
hdf5 (v1.8.12)\
h5py (v2.9.0)\
lavavu\
swig (v3.0.12)\
git (default available)\
libxml-dev (default available)\
scons (v3.1.2)\
numpy\

## Getting started
```
module load centos7.3/lib/openmpi/3.0.0-gcc-7.0.1

export CDIR=/truba/home/<username>
```
\
**Installing the packages sequentially**

### Anaconda
```
cd /truba/sw/src
./Anaconda3-2020.07-Linux-x86_64.sh
```

### lavavu & mpi4py
```shell
pip3 install lavavu
pip3 install mpi4py
```
\
**Add the following to PYTHONPATH:**
```
/truba/home/username/anaconda3/lib/python3.8/site-packages/mpi4py/mpi4py-3.0.3.dist-info
```

### swig
```shell
wget https://sourceforge.net/projects/swig/files/swig/swig-3.0.12/swig-3.0.12.tar.gz $CDIR
tar -zxvf swig-3.0.12.tar.gz
cd $CDIR/swig-3.0.12
./configure --prefix=~/swig-3.0.12
make
make install
```

### PETSC
```shell
cd $CDIR
git clone -b v3.12.3 https://gitlab.com/petsc/petsc.git petsc
cd $CDIR/petsc
python3 ./configure  --prefix=/truba/home/username/PETSC  --with-cc=mpicc --with-cxx=mpicxx --with-fc=mpif90  --download-fblaslapack=1 --download-mumps=1 --download-parmetis=1 --download-metis=1 --download-superlu=1 --download-hypre=1 --download-scalapack=1 --download-superlu_dist=1 --download-superlu=1 1 --with-hdf5=1 --with-shared-libraries
```

```shell
make PETSC_DIR=/truba/home/username/PETSC/petsc PETSC_ARCH=arch-linux-c-debug all
make PETSC_DIR=/truba/home/username/PETSC/petsc PETSC_ARCH=arch-linux-c-debug install
```
\
**Add the followings to .bash_profile**
```
export PETSC_DIR=/truba/home/username/PETSC/petsc
export PETSC_ARCH=/truba/home/username/PETSC/petsc/arch-linux-c-debug
```

### hdf5
```shell
wget https://support.hdfgroup.org/ftp/HDF5/releases/hdf5-1.8/hdf5-1.8.12/src/hdf5-1.8.12.tar.gz $CDIR
cd $CDIR
tar -zxvf hdf5-1.8.12.tar.gz
cd $CDIR/hdf5-1.8.12
```

```shell
CC=/truba/sw/centos7.3/lib/openmpi/3.0.0-gcc-7.0.1/bin/mpicc
FC=/truba/sw/centos7.3/lib/openmpi/3.0.0-gcc-7.0.1/bin/mpif90
./configure --enable-shared --enable-parallel --enable-fortran --prefix=/truba/home/username/hdf5-1.8.12
make
make install
```

### h5py
```shell
CC=/truba/sw/centos7.3/lib/openmpi/3.0.0-gcc-7.0.1/bin/mpicc HDF5_MPI="ON"  HDF5_DIR=/truba/home/username/hdf5-1.8.12/ pip3 install --no-binary=h5py h5py==2.9.0
```

### scons
```shell
pip3 install SCons==3.1.2
```
\
**Add the following to PYTHONPATH:**
```
/truba/home/username/anaconda3/lib/python3.8/site-packages/scons-3.1.2.dist-info:
```

### Underworld2 (v2.10.0b)
Add `export PYTHON_DIR=/truba/home/username/anaconda3` to .bash_profile

```shell
git clone -b v2.10.0b https://github.com/underworldcode/underworld2.git

cd $CDIR/underworld2/underworld/libUnderworld
python3 ./configure.py --prefix=/truba/home/username/underworld2
python3 ./compile.py --jobs=4
python3 ./scons.py install
```

### UWGeoydnamics (v2.10.2)
```shell
cd $CDIR
git clone -b v2.10.2 https://github.com/underworldcode/UWGeodynamics.git

pip3 install UWGeodynamics/
```
