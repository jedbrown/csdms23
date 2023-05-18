# CSDMS'23 Sustainable Solvers

This clinic will use:

* [PETSc](https://petsc.org) for algebraic solver fundamentals

And these optional packages for more real-world examples.

* [libCEED](https://libceed.org) for fast element algebra and fluids simulation
* [Ratel](https://ratel.micromorph.org) for solid mechanics

## Installation

### Colab (cloud)

https://colab.research.google.com/drive/1SkEWDWsxZ7MzbE9D8lgOa-pSdsqLqXOq?usp=sharing

### Docker (recommended)

This is the simplest approach once you have Docker installed.

```console
$ docker run -it --rm -v $(pwd):/work registry.gitlab.com/micromorph/ratel
```

### Building from source

#### Ubuntu/Debian

```console
$ apt-get update
$ apt-get install -y --no-install-recommends \
  autoconf \
  bash-completion \
  ca-certificates \
  chrpath \
  cmake \
  curl \
  git \
  libblis-serial-dev \
  liblapack-dev \
  libopenmpi-dev \
  libtool \
  locales \
  m4 \
  make \
  pkg-config \
  python3-distutils \
  zlib1g-dev
```

#### Windows

We recommend using [WSL](https://learn.microsoft.com/en-us/windows/wsl/install) and then following the instructions for Ubuntu/Debian. If you want to create native Windows executables, you can [install PETSc using MSYS2/MinGW](https://petsc.org/main/install/windows/#installation-with-msys2-and-compilers-mingw).

#### MacOS

We recommend using [Homebrew](https://brew.sh) to install `open-mpi` or `mpich` ([details here](https://petsc.org/main/install/install/#installing-on-macos)), then proceed to install PETSc.

#### PETSc

```console
$ git clone https://gitlab.com/petsc/petsc
$ cd petsc
$ export PETSC_DIR=`pwd` PETSC_ARCH=csdms
$ ./configure
$ make
$ make check
```

#### libCEED

```console
$ git clone https://github.com/CEED/libCEED
$ make -C libCEED
```

#### Ratel

```console
$ git clone https://gitlab.com/micromorph/ratel
$ make -C ratel
```

## Visualization

We recommend [Paraview](https://www.paraview.org/) for 3D visualization. It has a binary install on all platforms (via package manager or from the website). 
