# pgmoneta

`pgmoneta` is a backup / restore solution for [PostgreSQL](https://www.postgresql.org).

`pgmoneta` is named after the Roman Goddess of Memory.

## Features

* Full backup
* Prometheus support
* Remote management
* Transport Layer Security (TLS) v1.2+ support
* Daemon mode
* User vault

See [Getting Started](./doc/GETTING_STARTED.md) on how to get started with `pgmoneta`.

See [Configuration](./doc/CONFIGURATION.md) on how to configure `pgmoneta`.

## Overview

`pgmoneta` makes use of

* Process model
* Shared memory model across processes
* [libev](http://software.schmorp.de/pkg/libev.html) for fast network interactions
* [Atomic operations](https://en.cppreference.com/w/c/atomic) are used to keep track of state
* The [PostgreSQL](https://www.postgresql.org) command line tools

See [Architecture](./doc/ARCHITECTURE.md) for the architecture of `pgmoneta`.

## Tested platforms

* [Fedora](https://getfedora.org/) 28+
* [RHEL](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux) 7.x with
  [EPEL](https://access.redhat.com/solutions/3358) and
  [DevTools](https://developers.redhat.com/products/developertoolset/overview) 8+
* [RHEL](https://www.redhat.com/en/technologies/linux-platforms/enterprise-linux) 8.x with
  [AppStream](https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/8/html/installing_managing_and_removing_user-space_components/using-appstream_using-appstream)

## Compiling the source

`pgmoneta` requires

* [gcc 8+](https://gcc.gnu.org) (C17)
* [cmake](https://cmake.org)
* [make](https://www.gnu.org/software/make/)
* [libev](http://software.schmorp.de/pkg/libev.html)
* [OpenSSL](http://www.openssl.org/)
* [systemd](https://www.freedesktop.org/wiki/Software/systemd/)
* [rst2man](https://docutils.sourceforge.io/)

```sh
dnf install gcc cmake make libev libev-devel openssl openssl-devel systemd systemd-devel python3-docutils
```

Alternative [clang 8+](https://clang.llvm.org/) can be used.

### Release build

The following commands will install `pgmoneta` in the `/usr/local` hierarchy
and run the default configuration.

```sh
git clone https://github.com/pgmoneta/pgmoneta.git
cd pgmoneta
mkdir build
cd build
cmake -DCMAKE_INSTALL_PREFIX=/usr/local ..
make
sudo make install
```

See [RPM](./doc/RPM.md) for how to build a RPM of `pgmoneta`.

### Debug build

The following commands will create a `DEBUG` version of `pgmoneta`.

```sh
git clone https://github.com/pgmoneta/pgmoneta.git
cd pgmoneta
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Debug ..
make
```

Remember to set the `log_level` configuration option to `debug5`.

## Contributing

Contributions to `pgmoneta` are managed on [GitHub.com](https://github.com/pgmoneta/pgmoneta/)

* [Ask a question](https://github.com/pgmoneta/pgmoneta/discussions)
* [Raise an issue](https://github.com/pgmoneta/pgmoneta/issues)
* [Feature request](https://github.com/pgmoneta/pgmoneta/issues)
* [Code submission](https://github.com/pgmoneta/pgmoneta/pulls)

Contributions are most welcome !

Please, consult our [Code of Conduct](./CODE_OF_CONDUCT.md) policies for interacting in our
community.

Consider giving the project a [star](https://github.com/pgmoneta/pgmoneta/stargazers) on
[GitHub](https://github.com/pgmoneta/pgmoneta/) if you find it useful.

## License

[BSD-3-Clause](https://opensource.org/licenses/BSD-3-Clause)