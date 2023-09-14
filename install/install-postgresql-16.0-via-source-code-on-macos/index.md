# Install PostgreSQL 16.0 via source code on macOS

How to install PostgreSQL via source code on macOS with these configurations:

* PostgreSQL 16.0 with a custom directory prefix

* Options for ICU, Bonjour, SSL OpenSSL, UUID e2fs

* macOS Ventura 13.5
  
* Homebrew 4.1 for installing some system dependencies (e.g. ICU)

Feedback welcome.


## Get PostgreSQL source code

Download:

```sh
curl https://ftp.postgresql.org/pub/source/v$version/postgresql-16.0.tar.gz
```

Extract:

```sh
tar xf postgresql-16.0.tar.gz
```

Change to new directory:

```sh
cd postgresql-16.0
```

## Get International Components for Unicode (ICU)

Get the International Components for Unicode (ICU) libraries.

Install:

```sh
brew install icu4c
```

Link:

```sh
brew link icu4c --force
```

Append the ICU packages to the env var:

```sh
export PKG_CONFIG_PATH="$PKG_CONFIG_PATH:$(brew --cellar)/opt/icu4c/lib/pkgconfig"
```


## Get Xcode tools

Install macOS Xcode development tools:

```sh
xcode-select --install
```

How to show the system root path:

```sh
xcrun --show-sdk-path
```

Output example:

```sh
/Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/SDKs/MacOSX.sdk
```

Set the PostgreSQL system root:

```sh
export PG_SYSROOT=$(xcrun --show-sdk-path)
```


## Configuration options

These configuration options are the ones we prefer for this installation on a developer laptop.

<dl>

<dt>--prefix=$HOME/opt/postgresql/16.0

<dd>Build with a custom installation directory. We choose to install in a home directory because this makes it easier for a developer to try their own versions.</dd>

<dt>--with-bonjour</dt>

<dd>Build with support for Bonjour automatic service discovery. This requires Bonjour support in your operating system. Recommended on macOS.</dd>

<dt>--with-ssl=openssl</dt>

<dd>Build with support for SSL (encrypted) connections. This requires the OpenSSL package to be installed. configure will check for the required header files and libraries to make sure that your OpenSSL installation is sufficient before proceeding.</dd>

<dt>--with-uuid=e2fs</dt>

<dd>Build the uuid-ossp module (which provides functions to generate UUIDs), using the e2fs UID library created by the e2fsprogs project.</dd>

<dt>--with-lz4</dt>

<dd>Build with LZ4 compression support.</dd>

<dt>--with-zstd</dt>

<dd>Build with Zstandard compression support.</dd

</dl>


## Configure

Create a custom destination directory:

```sh
mkdir -p $HOME/postgresql/16.0
```

Configure:

```sh
./configure \
--prefix=$HOME/postgresql/16.0 \
--with-bonjour \
#--with-lz4 \
#--with-zstd \
#--with-ssl=openssl \
#--with-uuid=e2fs \
```

Make everything, including the documentation (HTML pages and man pages), and the additional modules (contrib):

```sh
make world
make install-world
```


## macOS

You may want to check if your system already has a user `postgres` or `_postgres`.

```sh
dscl . list /Users
```

Create the typical `postgres` user

```sh
sudo dscl . -create /Users/postgres
```


## Environment

Append the new directories to PATH and MANPATH:

```sh
PATH="$PATH:$HOME/opt/postgresql/16.0/bin"
export PATH

MANPATH="$MANPATH:$HOME/opt/postgresql/16.0/share/man"
export MANPATH
```
