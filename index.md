Jack Dong's Blog

# [Jack Dong's Blog](/)

## [A modern stylish theme for Hexo](/)

[Home](/) [Archives](/archives) [Categories](/categories) [Tags](/tags) [About](/about)

[2021-02-12](/2021/02/12/kubernetes/)

[Kubernetes](/categories/Kubernetes/)

# [Kubernetes (K8s)](/2021/02/12/kubernetes/)

[![GoPkg Widget](https://pkg.go.dev/badge/k8s.io/kubernetes.svg)](https://pkg.go.dev/k8s.io/kubernetes) [![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/569/badge)](https://bestpractices.coreinfrastructure.org/projects/569)

![](https://github.com/kubernetes/kubernetes/raw/master/logo/logo.png)

---

Kubernetes, also known as K8s, is an open source system for managing [containerized applications](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/)  
across multiple hosts. It provides basic mechanisms for deployment, maintenance,  
and scaling of applications.

Kubernetes builds upon a decade and a half of experience at Google running  
production workloads at scale using a system called [Borg](https://research.google.com/pubs/pub43438.html),  
combined with best-of-breed ideas and practices from the community.

Kubernetes is hosted by the Cloud Native Computing Foundation ([CNCF](https://www.cncf.io/about)).  
If your company wants to help shape the evolution of  
technologies that are container-packaged, dynamically scheduled,  
and microservices-oriented, consider joining the CNCF.  
For details about who’s involved and how Kubernetes plays a role,  
read the CNCF [announcement](https://cncf.io/news/announcement/2015/07/new-cloud-native-computing-foundation-drive-alignment-among-container).

---

## [](#To-start-using-K8s "To start using K8s")To start using K8s

See our documentation on [kubernetes.io](https://kubernetes.io/).

Try our [interactive tutorial](https://kubernetes.io/docs/tutorials/kubernetes-basics).

Take a free course on [Scalable Microservices with Kubernetes](https://www.udacity.com/course/scalable-microservices-with-kubernetes--ud615).

To use Kubernetes code as a library in other applications, see the [list of published components](https://git.k8s.io/kubernetes/staging/README.md).  
Use of the `k8s.io/kubernetes` module or `k8s.io/kubernetes/...` packages as libraries is not supported.

## [](#To-start-developing-K8s "To start developing K8s")To start developing K8s

The [community repository](https://git.k8s.io/community) hosts all information about  
building Kubernetes from source, how to contribute code  
and documentation, who to contact about what, etc.

If you want to build Kubernetes right away there are two options:

##### [](#You-have-a-working-Go-environment "You have a working Go environment.")You have a working [Go environment](https://golang.org/doc/install).

1  
2  
3  
4  
5

mkdir -p $GOPATH/src/k8s.io  
cd $GOPATH/src/k8s.io  
git clone https://github.com/kubernetes/kubernetes  
cd kubernetes  
make

##### [](#You-have-a-working-Docker-environment "You have a working Docker environment.")You have a working [Docker environment](https://docs.docker.com/engine).

1  
2  
3

git clone https://github.com/kubernetes/kubernetes  
cd kubernetes  
make quick-release

For the full story, head over to the [developer’s documentation](https://git.k8s.io/community/contributors/devel#readme).

## [](#Support "Support")Support

If you need support, start with the [troubleshooting guide](https://kubernetes.io/docs/tasks/debug-application-cluster/troubleshooting/),  
and work your way through the process that we’ve outlined.

That said, if you have questions, reach out to us  
[one way or another](https://git.k8s.io/community/communication).

Share

- [Docker](/tags/Docker/)
- [Go](/tags/Go/)
- [Kubernetes](/tags/Kubernetes/)

[2021-02-11](/2021/02/11/php/)

[PHP](/categories/PHP/)

# [PHP](/2021/02/11/php/)

[![PHP](https://www.php.net/images/logos/new-php-logo.svg)](https://php.net)

# [](#The-PHP-Interpreter "The PHP Interpreter")The PHP Interpreter

PHP is a popular general-purpose scripting language that is especially suited to  
web development. Fast, flexible and pragmatic, PHP powers everything from your  
blog to the most popular websites in the world. PHP is distributed under the  
[PHP License v3.01](LICENSE).

[![Build status](https://travis-ci.org/php/php-src.svg?branch=master)](https://travis-ci.org/php/php-src)  
[![Build status](https://ci.appveyor.com/api/projects/status/meyur6fviaxgdwdy/branch/master?svg=true)](https://ci.appveyor.com/project/php/php-src)  
[![Build Status](https://dev.azure.com/phpazuredevops/php/_apis/build/status/php.php-src?branchName=master)](https://dev.azure.com/phpazuredevops/php/_build/latest?definitionId=1&branchName=master)  
[![Fuzzing Status](https://oss-fuzz-build-logs.storage.googleapis.com/badges/php.svg)](https://bugs.chromium.org/p/oss-fuzz/issues/list?sort=-opened&can=1&q=proj:php)

## [](#Documentation "Documentation")Documentation

The PHP manual is available at [php.net/docs](https://php.net/docs).

## [](#Installation "Installation")Installation

### [](#Prebuilt-packages-and-binaries "Prebuilt packages and binaries")Prebuilt packages and binaries

Prebuilt packages and binaries can be used to get up and running fast with PHP.

For Windows, the PHP binaries can be obtained from  
[windows.php.net](https://windows.php.net/). After extracting the archive the  
`*.exe` files are ready to use.

For other systems, see the [installation chapter](https://php.net/install).

### [](#Building-PHP-source-code "Building PHP source code")Building PHP source code

_For Windows, see [Build your own PHP on Windows](https://wiki.php.net/internals/windows/stepbystepbuild_sdk_2)._

For a minimal PHP build from Git, you will need autoconf, bison, and re2c. For  
a default build, you will additionally need libxml2 and libsqlite3.

On Ubuntu, you can install these using:

    sudo apt install -y pkg-config build-essential autoconf bison re2c \
                        libxml2-dev libsqlite3-dev

On Fedora, you can install these using:

    sudo dnf install re2c bison autoconf make libtool ccache libxml2-devel sqlite-devel

Generate configure:

    ./buildconf

Configure your build. `--enable-debug` is recommended for development, see  
`./configure --help` for a full list of options.

    # For development
    ./configure --enable-debug
    # For production
    ./configure

Build PHP. To speed up the build, specify the maximum number of jobs using `-j`:

    make -j4

The number of jobs should usually match the number of available cores, which  
can be determined using `nproc`.

## [](#Testing-PHP-source-code "Testing PHP source code")Testing PHP source code

PHP ships with an extensive test suite, the command `make test` is used after  
successful compilation of the sources to run this test suite.

It is possible to run tests using multiple cores by setting `-jN` in  
`TEST_PHP_ARGS`:

    make TEST_PHP_ARGS=-j4 test

Shall run `make test` with a maximum of 4 concurrent jobs: Generally the maximum  
number of jobs should not exceed the number of cores available.

The [qa.php.net](https://qa.php.net/) site provides more detailed info about  
testing and quality assurance.

## [](#Installing-PHP-built-from-source "Installing PHP built from source")Installing PHP built from source

After a successful build (and test), PHP may be installed with:

    make install

Depending on your permissions and prefix, `make install` may need super user  
permissions.

## [](#PHP-extensions "PHP extensions")PHP extensions

Extensions provide additional functionality on top of PHP. PHP consists of many  
essential bundled extensions. Additional extensions can be found in the PHP  
Extension Community Library - [PECL](https://pecl.php.net/).

## [](#Contributing "Contributing")Contributing

The PHP source code is located in the Git repository at  
[git.php.net](https://git.php.net/). Contributions are most welcome by forking  
the [GitHub mirror repository](https://github.com/php/php-src) and sending a  
pull request.

Discussions are done on GitHub, but depending on the topic can also be relayed  
to the official PHP developer mailing list [internals@lists.php.net](mailto:internals@lists.php.net).

New features require an RFC and must be accepted by the developers. See  
[Request for comments - RFC](https://wiki.php.net/rfc) and  
[Voting on PHP features](https://wiki.php.net/rfc/voting) for more information  
on the process.

Bug fixes **do not** require an RFC but require a bug tracker ticket. Open a  
ticket at [bugs.php.net](https://bugs.php.net/) and reference the bug id using  
`#NNNNNN`.

    Fix #55371: get_magic_quotes_gpc() throws deprecation warning

    After removing magic quotes, the get_magic_quotes_gpc function caused a
    deprecated warning. get_magic_quotes_gpc can be used to detect the
    magic_quotes behavior and therefore should not raise a warning at any time.
    The patch removes this warning.

Pull requests are not merged directly on GitHub. All PRs will be pulled and  
pushed through [git.php.net](https://git.php.net/). See  
[Git workflow](https://wiki.php.net/vcs/gitworkflow) for more details.

### [](#Guidelines-for-contributors "Guidelines for contributors")Guidelines for contributors

See further documents in the repository for more information on how to  
contribute:

- [Contributing to PHP](/CONTRIBUTING.md)
- [PHP coding standards](/CODING_STANDARDS.md)
- [Mailinglist rules](/docs/mailinglist-rules.md)
- [PHP release process](/docs/release-process.md)

## [](#Credits "Credits")Credits

For the list of people who’ve put work into PHP, please see the  
[PHP credits page](https://php.net/credits.php).

Share

- [php](/tags/php/)

[2021-02-02](/2021/02/02/about/)

# [About](/2021/02/02/about/)

### [](#Preview "Preview")[Preview](https://autoload.github.io/)

## [](#Install "Install")Install

### [](#For-hexo-lt-5-0 "For hexo < 5.0")For hexo < 5.0

1

git clone https://github.com/autoload/hexo-theme-auto.git themes/auto

### [](#For-hexo-gt-5-0 "For hexo >= 5.0")For hexo >= 5.0

1

npm i hexo-theme-ayer -S

- If this theme is newly installed, a `_config.auto.yml` file will be generated in the root directory after the installation is complete, and you can directly edit the `_config.auto.yml` file for configuration.
- If it is a theme upgrade, you can use the configuration method of hexo < 5.0, or you can move the original configuration file to the root directory and rename it to `_config.auto.yml`.

## [](#Enable "Enable")Enable

Modify `theme` setting in `_config.yml` to `auto`

1

theme: auto

## [](#Update "Update")Update

1  
2

cd themes/auto  
git pull

## [](#Multi-Language-Support "Multi Language Support")Multi Language Support

zh-CN（Simplified Chinese） en（English） zh-TW（traditional Chinese） ja（Japanese） es（Spanish） de（German） fr（French） ru（Russian） ko（Korean） vi（Vietnamese） nl（Dutch） no（Norwegian） pt（Portuguese）

English is default languge, if you want to change, modify `language` option in `_config.yml` file in your blog’s root folder.

## [](#Configuration "Configuration")Configuration

1  
2  
3  
4  
5  
6  
7  
8  
9  
10  
11  
12  
13  
14  
15

\# Menu-Sidebar  
menu:  
 Home: /  
 Archives: /archives  
 Categories: /categories  
 Tags: /tags  
 About: /about

\# Sidebar  
sidebar: right  
widgets:

- tag
- recent_posts
- category
- archive

---

## [](#License "License")License

MIT License

Copyright © 2020 [David Wan](http://autoload.github.io/)

Share

[2021-01-12](/2021/01/12/redis/)

[Redis](/categories/Redis/)

# [Redis](/2021/01/12/redis/)

This README is just a fast _quick start_ document. You can find more detailed documentation at [redis.io](https://redis.io/).

## [](#What-is-Redis "What is Redis?")What is Redis?

Redis is often referred to as a _data structures_ server. What this means is that Redis provides access to mutable data structures via a set of commands, which are sent using a _server-client_ model with TCP sockets and a simple protocol. So different processes can query and modify the same data structures in a shared way.

Data structures implemented into Redis have a few special properties:

- Redis cares to store them on disk, even if they are always served and modified into the server memory. This means that Redis is fast, but that it is also non-volatile.
- The implementation of data structures emphasizes memory efficiency, so data structures inside Redis will likely use less memory compared to the same data structure modelled using a high-level programming language.
- Redis offers a number of features that are natural to find in a database, like replication, tunable levels of durability, clustering, and high availability.

Another good example is to think of Redis as a more complex version of memcached, where the operations are not just SETs and GETs, but operations that work with complex data types like Lists, Sets, ordered data structures, and so forth.

If you want to know more, this is a list of selected starting points:

- Introduction to Redis data types. [http://redis.io/topics/data-types-intro](http://redis.io/topics/data-types-intro)
- Try Redis directly inside your browser. [http://try.redis.io](http://try.redis.io/)
- The full list of Redis commands. [http://redis.io/commands](http://redis.io/commands)
- There is much more inside the official Redis documentation. [http://redis.io/documentation](http://redis.io/documentation)

## [](#Building-Redis "Building Redis")Building Redis

Redis can be compiled and used on Linux, OSX, OpenBSD, NetBSD, FreeBSD.  
We support big endian and little endian architectures, and both 32 bit  
and 64 bit systems.

It may compile on Solaris derived systems (for instance SmartOS) but our  
support for this platform is _best effort_ and Redis is not guaranteed to  
work as well as in Linux, OSX, and \*BSD.

It is as simple as:

    % make

To build with TLS support, you’ll need OpenSSL development libraries (e.g.  
libssl-dev on Debian/Ubuntu) and run:

    % make BUILD_TLS=yes

To build with systemd support, you’ll need systemd development libraries (such  
as libsystemd-dev on Debian/Ubuntu or systemd-devel on CentOS) and run:

    % make USE_SYSTEMD=yes

To append a suffix to Redis program names, use:

    % make PROG_SUFFIX="-alt"

You can run a 32 bit Redis binary using:

    % make 32bit

After building Redis, it is a good idea to test it using:

    % make test

If TLS is built, running the tests with TLS enabled (you will need `tcl-tls`  
installed):

    % ./utils/gen-test-certs.sh
    % ./runtest --tls

## [](#Fixing-build-problems-with-dependencies-or-cached-build-options "Fixing build problems with dependencies or cached build options")Fixing build problems with dependencies or cached build options

Redis has some dependencies which are included in the `deps` directory.  
`make` does not automatically rebuild dependencies even if something in  
the source code of dependencies changes.

When you update the source code with `git pull` or when code inside the  
dependencies tree is modified in any other way, make sure to use the following  
command in order to really clean everything and rebuild from scratch:

    make distclean

This will clean: jemalloc, lua, hiredis, linenoise.

Also if you force certain build options like 32bit target, no C compiler  
optimizations (for debugging purposes), and other similar build time options,  
those options are cached indefinitely until you issue a `make distclean`  
command.

## [](#Fixing-problems-building-32-bit-binaries "Fixing problems building 32 bit binaries")Fixing problems building 32 bit binaries

If after building Redis with a 32 bit target you need to rebuild it  
with a 64 bit target, or the other way around, you need to perform a  
`make distclean` in the root directory of the Redis distribution.

In case of build errors when trying to build a 32 bit binary of Redis, try  
the following steps:

- Install the package libc6-dev-i386 (also try g++-multilib).
- Try using the following command line instead of `make 32bit`:  
  `make CFLAGS="-m32 -march=native" LDFLAGS="-m32"`

## [](#Allocator "Allocator")Allocator

Selecting a non-default memory allocator when building Redis is done by setting  
the `MALLOC` environment variable. Redis is compiled and linked against libc  
malloc by default, with the exception of jemalloc being the default on Linux  
systems. This default was picked because jemalloc has proven to have fewer  
fragmentation problems than libc malloc.

To force compiling against libc malloc, use:

    % make MALLOC=libc

To compile against jemalloc on Mac OS X systems, use:

    % make MALLOC=jemalloc

## [](#Monotonic-clock "Monotonic clock")Monotonic clock

By default, Redis will build using the POSIX clock_gettime function as the  
monotonic clock source. On most modern systems, the internal processor clock  
can be used to improve performance. Cautions can be found here:  
[http://oliveryang.net/2015/09/pitfalls-of-TSC-usage/](http://oliveryang.net/2015/09/pitfalls-of-TSC-usage/)

To build with support for the processor’s internal instruction clock, use:

    % make CFLAGS="-DUSE_PROCESSOR_CLOCK"

## [](#Verbose-build "Verbose build")Verbose build

Redis will build with a user-friendly colorized output by default.  
If you want to see a more verbose output, use the following:

    % make V=1

## [](#Running-Redis "Running Redis")Running Redis

To run Redis with the default configuration, just type:

    % cd src
    % ./redis-server

If you want to provide your redis.conf, you have to run it using an additional  
parameter (the path of the configuration file):

    % cd src
    % ./redis-server /path/to/redis.conf

It is possible to alter the Redis configuration by passing parameters directly  
as options using the command line. Examples:

    % ./redis-server --port 9999 --replicaof 127.0.0.1 6379
    % ./redis-server /etc/redis/6379.conf --loglevel debug

All the options in redis.conf are also supported as options using the command  
line, with exactly the same name.

## [](#Running-Redis-with-TLS "Running Redis with TLS:")Running Redis with TLS:

Please consult the [TLS.md](TLS.md) file for more information on  
how to use Redis with TLS.

## [](#Playing-with-Redis "Playing with Redis")Playing with Redis

You can use redis-cli to play with Redis. Start a redis-server instance,  
then in another terminal try the following:

    % cd src
    % ./redis-cli
    redis> ping
    PONG
    redis> set foo bar
    OK
    redis> get foo
    "bar"
    redis> incr mycounter
    (integer) 1
    redis> incr mycounter
    (integer) 2
    redis>

You can find the list of all the available commands at [http://redis.io/commands](http://redis.io/commands).

## [](#Installing-Redis "Installing Redis")Installing Redis

In order to install Redis binaries into /usr/local/bin, just use:

    % make install

You can use `make PREFIX=/some/other/directory install` if you wish to use a  
different destination.

Make install will just install binaries in your system, but will not configure  
init scripts and configuration files in the appropriate place. This is not  
needed if you just want to play a bit with Redis, but if you are installing  
it the proper way for a production system, we have a script that does this  
for Ubuntu and Debian systems:

    % cd utils
    % ./install_server.sh

_Note_: `install_server.sh` will not work on Mac OSX; it is built for Linux only.

The script will ask you a few questions and will setup everything you need  
to run Redis properly as a background daemon that will start again on  
system reboots.

You’ll be able to stop and start Redis using the script named  
`/etc/init.d/redis_<portnumber>`, for instance `/etc/init.d/redis_6379`.

## [](#Code-contributions "Code contributions")Code contributions

Note: By contributing code to the Redis project in any form, including sending  
a pull request via Github, a code fragment or patch via private email or  
public discussion groups, you agree to release your code under the terms  
of the BSD license that you can find in the [COPYING](https://github.com/redis/redis/blob/unstable/COPYING) file included in the Redis  
source distribution.

Please see the [CONTRIBUTING](https://github.com/redis/redis/blob/unstable/CONTRIBUTING) file in this source distribution for more  
information, including details on our process for security bugs/vulnerabilities.

# [](#Redis-internals "Redis internals")Redis internals

If you are reading this README you are likely in front of a Github page  
or you just untarred the Redis distribution tar ball. In both the cases  
you are basically one step away from the source code, so here we explain  
the Redis source code layout, what is in each file as a general idea, the  
most important functions and structures inside the Redis server and so forth.  
We keep all the discussion at a high level without digging into the details  
since this document would be huge otherwise and our code base changes  
continuously, but a general idea should be a good starting point to  
understand more. Moreover most of the code is heavily commented and easy  
to follow.

## [](#Source-code-layout "Source code layout")Source code layout

The Redis root directory just contains this README, the Makefile which  
calls the real Makefile inside the `src` directory and an example  
configuration for Redis and Sentinel. You can find a few shell  
scripts that are used in order to execute the Redis, Redis Cluster and  
Redis Sentinel unit tests, which are implemented inside the `tests`  
directory.

Inside the root are the following important directories:

- `src`: contains the Redis implementation, written in C.
- `tests`: contains the unit tests, implemented in Tcl.
- `deps`: contains libraries Redis uses. Everything needed to compile Redis is inside this directory; your system just needs to provide `libc`, a POSIX compatible interface and a C compiler. Notably `deps` contains a copy of `jemalloc`, which is the default allocator of Redis under Linux. Note that under `deps` there are also things which started with the Redis project, but for which the main repository is not `redis/redis`.

There are a few more directories but they are not very important for our goals  
here. We’ll focus mostly on `src`, where the Redis implementation is contained,  
exploring what there is inside each file. The order in which files are  
exposed is the logical one to follow in order to disclose different layers  
of complexity incrementally.

Note: lately Redis was refactored quite a bit. Function names and file  
names have been changed, so you may find that this documentation reflects the  
`unstable` branch more closely. For instance, in Redis 3.0 the `server.c`  
and `server.h` files were named `redis.c` and `redis.h`. However the overall  
structure is the same. Keep in mind that all the new developments and pull  
requests should be performed against the `unstable` branch.

## [](#server-h "server.h")server.h

The simplest way to understand how a program works is to understand the  
data structures it uses. So we’ll start from the main header file of  
Redis, which is `server.h`.

All the server configuration and in general all the shared state is  
defined in a global structure called `server`, of type `struct redisServer`.  
A few important fields in this structure are:

- `server.db` is an array of Redis databases, where data is stored.
- `server.commands` is the command table.
- `server.clients` is a linked list of clients connected to the server.
- `server.master` is a special client, the master, if the instance is a replica.

There are tons of other fields. Most fields are commented directly inside  
the structure definition.

Another important Redis data structure is the one defining a client.  
In the past it was called `redisClient`, now just `client`. The structure  
has many fields, here we’ll just show the main ones:

    struct client {
        int fd;
        sds querybuf;
        int argc;
        robj **argv;
        redisDb *db;
        int flags;
        list *reply;
        char buf[PROTO_REPLY_CHUNK_BYTES];
        ... many other fields ...
    }

The client structure defines a _connected client_:

- The `fd` field is the client socket file descriptor.
- `argc` and `argv` are populated with the command the client is executing, so that functions implementing a given Redis command can read the arguments.
- `querybuf` accumulates the requests from the client, which are parsed by the Redis server according to the Redis protocol and executed by calling the implementations of the commands the client is executing.
- `reply` and `buf` are dynamic and static buffers that accumulate the replies the server sends to the client. These buffers are incrementally written to the socket as soon as the file descriptor is writeable.

As you can see in the client structure above, arguments in a command  
are described as `robj` structures. The following is the full `robj`  
structure, which defines a _Redis object_:

    typedef struct redisObject {
        unsigned type:4;
        unsigned encoding:4;
        unsigned lru:LRU_BITS; /* lru time (relative to server.lruclock) */
        int refcount;
        void *ptr;
    } robj;

Basically this structure can represent all the basic Redis data types like  
strings, lists, sets, sorted sets and so forth. The interesting thing is that  
it has a `type` field, so that it is possible to know what type a given  
object has, and a `refcount`, so that the same object can be referenced  
in multiple places without allocating it multiple times. Finally the `ptr`  
field points to the actual representation of the object, which might vary  
even for the same type, depending on the `encoding` used.

Redis objects are used extensively in the Redis internals, however in order  
to avoid the overhead of indirect accesses, recently in many places  
we just use plain dynamic strings not wrapped inside a Redis object.

## [](#server-c "server.c")server.c

This is the entry point of the Redis server, where the `main()` function  
is defined. The following are the most important steps in order to startup  
the Redis server.

- `initServerConfig()` sets up the default values of the `server` structure.
- `initServer()` allocates the data structures needed to operate, setup the listening socket, and so forth.
- `aeMain()` starts the event loop which listens for new connections.

There are two special functions called periodically by the event loop:

1.  `serverCron()` is called periodically (according to `server.hz` frequency), and performs tasks that must be performed from time to time, like checking for timed out clients.
2.  `beforeSleep()` is called every time the event loop fired, Redis served a few requests, and is returning back into the event loop.

Inside server.c you can find code that handles other vital things of the Redis server:

- `call()` is used in order to call a given command in the context of a given client.
- `activeExpireCycle()` handles eviction of keys with a time to live set via the `EXPIRE` command.
- `performEvictions()` is called when a new write command should be performed but Redis is out of memory according to the `maxmemory` directive.
- The global variable `redisCommandTable` defines all the Redis commands, specifying the name of the command, the function implementing the command, the number of arguments required, and other properties of each command.

## [](#networking-c "networking.c")networking.c

This file defines all the I/O functions with clients, masters and replicas  
(which in Redis are just special clients):

- `createClient()` allocates and initializes a new client.
- the `addReply*()` family of functions are used by command implementations in order to append data to the client structure, that will be transmitted to the client as a reply for a given command executed.
- `writeToClient()` transmits the data pending in the output buffers to the client and is called by the _writable event handler_ `sendReplyToClient()`.
- `readQueryFromClient()` is the _readable event handler_ and accumulates data read from the client into the query buffer.
- `processInputBuffer()` is the entry point in order to parse the client query buffer according to the Redis protocol. Once commands are ready to be processed, it calls `processCommand()` which is defined inside `server.c` in order to actually execute the command.
- `freeClient()` deallocates, disconnects and removes a client.

## [](#aof-c-and-rdb-c "aof.c and rdb.c")aof.c and rdb.c

As you can guess from the names, these files implement the RDB and AOF  
persistence for Redis. Redis uses a persistence model based on the `fork()`  
system call in order to create a thread with the same (shared) memory  
content of the main Redis thread. This secondary thread dumps the content  
of the memory on disk. This is used by `rdb.c` to create the snapshots  
on disk and by `aof.c` in order to perform the AOF rewrite when the  
append only file gets too big.

The implementation inside `aof.c` has additional functions in order to  
implement an API that allows commands to append new commands into the AOF  
file as clients execute them.

The `call()` function defined inside `server.c` is responsible for calling  
the functions that in turn will write the commands into the AOF.

## [](#db-c "db.c")db.c

Certain Redis commands operate on specific data types; others are general.  
Examples of generic commands are `DEL` and `EXPIRE`. They operate on keys  
and not on their values specifically. All those generic commands are  
defined inside `db.c`.

Moreover `db.c` implements an API in order to perform certain operations  
on the Redis dataset without directly accessing the internal data structures.

The most important functions inside `db.c` which are used in many command  
implementations are the following:

- `lookupKeyRead()` and `lookupKeyWrite()` are used in order to get a pointer to the value associated to a given key, or `NULL` if the key does not exist.
- `dbAdd()` and its higher level counterpart `setKey()` create a new key in a Redis database.
- `dbDelete()` removes a key and its associated value.
- `emptyDb()` removes an entire single database or all the databases defined.

The rest of the file implements the generic commands exposed to the client.

## [](#object-c "object.c")object.c

The `robj` structure defining Redis objects was already described. Inside  
`object.c` there are all the functions that operate with Redis objects at  
a basic level, like functions to allocate new objects, handle the reference  
counting and so forth. Notable functions inside this file:

- `incrRefCount()` and `decrRefCount()` are used in order to increment or decrement an object reference count. When it drops to 0 the object is finally freed.
- `createObject()` allocates a new object. There are also specialized functions to allocate string objects having a specific content, like `createStringObjectFromLongLong()` and similar functions.

This file also implements the `OBJECT` command.

## [](#replication-c "replication.c")replication.c

This is one of the most complex files inside Redis, it is recommended to  
approach it only after getting a bit familiar with the rest of the code base.  
In this file there is the implementation of both the master and replica role  
of Redis.

One of the most important functions inside this file is `replicationFeedSlaves()` that writes commands to the clients representing replica instances connected  
to our master, so that the replicas can get the writes performed by the clients:  
this way their data set will remain synchronized with the one in the master.

This file also implements both the `SYNC` and `PSYNC` commands that are  
used in order to perform the first synchronization between masters and  
replicas, or to continue the replication after a disconnection.

## [](#Other-C-files "Other C files")Other C files

- `t_hash.c`, `t_list.c`, `t_set.c`, `t_string.c`, `t_zset.c` and `t_stream.c` contains the implementation of the Redis data types. They implement both an API to access a given data type, and the client command implementations for these data types.
- `ae.c` implements the Redis event loop, it’s a self contained library which is simple to read and understand.
- `sds.c` is the Redis string library, check [http://github.com/antirez/sds](http://github.com/antirez/sds) for more information.
- `anet.c` is a library to use POSIX networking in a simpler way compared to the raw interface exposed by the kernel.
- `dict.c` is an implementation of a non-blocking hash table which rehashes incrementally.
- `scripting.c` implements Lua scripting. It is completely self-contained and isolated from the rest of the Redis implementation and is simple enough to understand if you are familiar with the Lua API.
- `cluster.c` implements the Redis Cluster. Probably a good read only after being very familiar with the rest of the Redis code base. If you want to read `cluster.c` make sure to read the [Redis Cluster specification](http://redis.io/topics/cluster-spec).

## [](#Anatomy-of-a-Redis-command "Anatomy of a Redis command")Anatomy of a Redis command

All the Redis commands are defined in the following way:

    void foobarCommand(client *c) {
        printf("%s",c->argv[1]->ptr); /* Do something with the argument. */
        addReply(c,shared.ok); /* Reply something to the client. */
    }

The command is then referenced inside `server.c` in the command table:

    {"foobar",foobarCommand,2,"rtF",0,NULL,0,0,0,0,0},

In the above example `2` is the number of arguments the command takes,  
while `"rtF"` are the command flags, as documented in the command table  
top comment inside `server.c`.

After the command operates in some way, it returns a reply to the client,  
usually using `addReply()` or a similar function defined inside `networking.c`.

There are tons of command implementations inside the Redis source code  
that can serve as examples of actual commands implementations. Writing  
a few toy commands can be a good exercise to get familiar with the code base.

There are also many other files not described here, but it is useless to  
cover everything. We just want to help you with the first steps.  
Eventually you’ll find your way inside the Redis code base :-)

Enjoy!

Share

- [C](/tags/C/)
- [NoSQL](/tags/NoSQL/)
- [redis](/tags/redis/)

[2021-01-11](/2021/01/11/postman/)

[Postman](/categories/Postman/)

# [Postman](/2021/01/11/postman/)

[![](https://assets.getpostman.com/common-share/postman-logo-horizontal-320x132.png)](https://www.postman.com/)

_Manage all of your organization’s APIs in Postman, with the industry’s most complete API development environment._

# [](#Postman-App-Support "Postman App Support")Postman App Support

If you have a feature request, a new integration idea or you would like to file a bug report, please use this [Github issue tracker](https://github.com/postmanlabs/postman-app-support/issues).

We _recommend_ that you search the issue tracker to check if someone else has already reported the issue and whether there is a known solution that you can use. This would be the fastest way for you to find a solution to any issue that you are currently facing.

If you are adding a bug report, please add detailed steps to reproduce the bug, the Postman version you’re using, and your OS version. Any additional files (collections, data dumps, console errors, screenshots) would be very helpful and would help us to narrow down the issue as quickly as possible.

We have compiled a quick set of [guidelines for reporting issues](#guidelines-for-reporting-issues).

> **Account Specific Queries:**
>
> If you have any billing or account-specific queries, reach out to us at [help@postman.com](mailto:help@postman.com).

We are also there as [@getpostman](https://www.twitter.com/getpostman) on Twitter. Feel free to drop in a line wherever it is easiest for you. Twitter would be the best place for you to stay updated with the latest news, features, and releases regarding Postman.

### [](#The-Community "The Community")The Community

![](https://avatars1.githubusercontent.com/u/3220138?v=3&s=120) [The Postman Community Forum](https://community.postman.com) offers you different ways to engage with other Postman enthusiasts. Feel free to drop by and say hello.

Sign in using your Postman account to participate in the discussions. Don’t want to log in? Then lurk on the sidelines and absorb all the knowledge.

### [](#Product-Roadmap "Product Roadmap")Product Roadmap

If you are curious about the features and enhancements planned for upcoming releases, check out [Postman’s roadmap](https://trello.com/b/4N7PnHAz/postman-roadmap-for-developers).

Want early access to these features? Some of the enhancements are available in our latest Canary builds available for download on OSX ([x64](https://dl.pstmn.io/download/channel/canary/osx_64)) / Windows ([x86](https://dl.pstmn.io/download/channel/canary/windows_32) or [x64](https://dl.pstmn.io/download/channel/canary/windows_64)) / Linux ([x86](https://dl.pstmn.io/download/channel/canary/linux_32) or [x64](https://dl.pstmn.io/download/channel/canary/linux_64)).

### [](#Documentation-and-Tutorials "Documentation and Tutorials")Documentation and Tutorials

If you are looking for more information regarding features, installation, and usage of the app, head over to the [documentation section on our website](https://learning.postman.com/). You can also have a look at our blog at [https://blog.postman.com](https://blog.postman.com) for interesting tutorials, development stories, and platform updates.

![[screenshot](https://assets.postman.com/postman-docs/postman-app-default-v8.jpg](https://assets.postman.com/postman-docs/postman-app-default-v8.jpg)

## [](#Guidelines-for-reporting-issues "Guidelines for reporting issues")Guidelines for reporting issues

We have put together a short set of guidelines you can follow while adding an issue to our [GitHub issue tracker](https://github.com/postmanlabs/postman-app-support/issues). Following this should help speedy resolution of issues.

1.  This issue tracker is only for Postman App related issues, along with other services accessible from the app.  
    If you have Newman specific issues, a better place to report them would be the Newman issue tracker at [https://github.com/postmanlabs/newman/issues](https://github.com/postmanlabs/newman/issues)
2.  If you are facing a Postman Cloud-related issue (such as sync, cloud-api, documenter, etc) and you want to include personal information such as your username or collection names, then mail us at [help@postman.com](mailto:help@postman.com).
3.  If you want to report a security issue in any of Postman’s services or products, read our [security reporting guidelines and policy](https://www.postman.com/vulnerability-reporting) for more details.
4.  Answer to questions along the lines of “How do I… in Postman” should be in our online documentation at [https://learning.postman.com/](https://learning.postman.com/). If you are unable to find a how-to guide in our online documentation, feel free to ask your question on our [Postman Community Forum](https://community.postman.com/).
5.  Before reporting an issue use the search feature on the issues page to check if there are issues similar to yours. A lot of issues are duplicates, and it is hard to keep track of them or respond when the issues are solved. If you find your issue already reported, feel free to add a “thumbs up” reaction and we will keep a note of it.
6.  When reporting a new issue in the issue tracker, check whether it helps to answer the following questions:

    - Which Postman App and Operating System version you are using. You can check this out in _Settings -> About_ section.
    - Is the bug reproducible every time, or do you see it occasionally?
    - Did you first encounter it recently, or has it always been there?
    - If it is a UI issue, a screenshot or GIF will help tremendously. (Tip: For quick gifs, check out [http://www.cockos.com/licecap/](http://www.cockos.com/licecap/))
    - If the issue is related to a script in the sandbox, attach the full code snippet and ensure that this is formatted correctly using the code block [markdown syntax](https://docs.github.com/en/github/writing-on-github/creating-and-highlighting-code-blocks)
    - Do you have the [Postman Interceptor](https://learning.postman.com/docs/postman/sending-api-requests/capturing-http-requests/) switched on? (applicable for the Chrome app)
    - If the request/response flow is not working, be sure to check and include details from the DevTools window (More on this at [https://learning.postman.com/docs/postman/sending-api-requests/debugging-and-logs/](https://learning.postman.com/docs/postman/sending-api-requests/debugging-and-logs/)).

    # [](#We-are-hiring "We are hiring!")We are hiring!

Want to help us solve [these issues](https://github.com/postmanlabs/postman-app-support/issues)? [We are hiring](https://www.postman.com/jobs/) engineers! Postman has grown a lot since it started as a side-project. More than 10 million people use Postman within thousands of companies across the world for everything API related. We are working hard to meet the expectations of the Postman community. If you want to build something amazing with us, [reach out](https://www.postman.com/jobs/)!

## [](#About-Postman "About Postman")About Postman

Postman is a collaboration platform for API development. Postman’s features simplify each step of building an API and streamline collaboration so you can create better APIs—faster.

Read more on our website: [https://www.postman.com/](https://www.postman.com/)

---

If you have issues or code contribution pertaining to Postman legacy version, head over to the [postmanlabs/postman-chrome-extension-legacy](https://github.com/postmanlabs/postman-chrome-extension-legacy) repository.

Share

- [postman](/tags/postman/)

[2020-12-12](/2020/12/12/laravel/)

[Laravel](/categories/Laravel/)

# [Laravel](/2020/12/12/laravel/)

[![](https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg)](https://laravel.com)

[![Build Status](https://travis-ci.org/laravel/framework.svg)](https://travis-ci.org/laravel/framework) [![Total Downloads](https://img.shields.io/packagist/dt/laravel/framework)](https://packagist.org/packages/laravel/framework) [![Latest Stable Version](https://img.shields.io/packagist/v/laravel/framework)](https://packagist.org/packages/laravel/framework) [![License](https://img.shields.io/packagist/l/laravel/framework)](https://packagist.org/packages/laravel/framework)

## [](#About-Laravel "About Laravel")About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## [](#Learning-Laravel "Learning Laravel")Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

If you don’t feel like reading, [Laracasts](https://laracasts.com/) can help. Laracasts contains over 1500 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## [](#Laravel-Sponsors "Laravel Sponsors")Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the Laravel [Patreon page](https://patreon.com/taylorotwell).

### [](#Premium-Partners "Premium Partners")Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co/)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com/)**
- **[64 Robots](https://64robots.com/)**
- **[Cubet Techno Labs](https://cubettech.com/)**
- **[Cyber-Duck](https://cyber-duck.co.uk/)**
- **[Many](https://www.many.co.uk/)**
- **[Webdock, Fast VPS Hosting](https://www.webdock.io/en)**
- **[DevSquad](https://devsquad.com/)**
- **[Curotec](https://www.curotec.com/)**
- **[OP.GG](https://op.gg/)**

## [](#Contributing "Contributing")Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## [](#Code-of-Conduct "Code of Conduct")Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## [](#Security-Vulnerabilities "Security Vulnerabilities")Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## [](#License "License")License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

Share

- [laravel](/tags/laravel/)
- [php](/tags/php/)

[2020-11-12](/2020/11/12/yii2/)

[Yii2](/categories/Yii2/)

# [Yii2](/2020/11/12/yii2/)

[![Yii Framework](https://www.yiiframework.com/files/logo/yii.png)](https://www.yiiframework.com/)

Yii 2 is a modern framework designed to be a solid foundation for your PHP application.

It is fast, secure and efficient and works right out of the box pre-configured with reasonable defaults.  
The framework is easy to adjust to meet your needs, because Yii has been designed to be flexible.

[![Latest Stable Version](https://img.shields.io/packagist/v/yiisoft/yii2.svg)](https://packagist.org/packages/yiisoft/yii2)  
[![Total Downloads](https://img.shields.io/packagist/dt/yiisoft/yii2.svg)](https://packagist.org/packages/yiisoft/yii2)  
[![Build Status](https://github.com/yiisoft/yii2/workflows/build/badge.svg)](https://github.com/yiisoft/yii2/actions)  
[![Code Coverage](https://scrutinizer-ci.com/g/yiisoft/yii2/badges/coverage.png?s=31d80f1036099e9d6a3e4d7738f6b000b3c3d10e)](https://scrutinizer-ci.com/g/yiisoft/yii2/)  
[![Scrutinizer Quality Score](https://scrutinizer-ci.com/g/yiisoft/yii2/badges/quality-score.png?s=b1074a1ff6d0b214d54fa5ab7abbb90fc092471d)](https://scrutinizer-ci.com/g/yiisoft/yii2/)

## [](#Installation "Installation")Installation

- The minimum required PHP version of Yii is PHP 5.4.
- It works best with PHP 7.
- [Follow the Definitive Guide](https://www.yiiframework.com/doc-2.0/guide-start-installation.html)  
  in order to get step by step instructions.

## [](#Documentation "Documentation")Documentation

- A [Definitive Guide](https://www.yiiframework.com/doc/guide/2.0) and  
  a [Class Reference](https://www.yiiframework.com/doc/api/2.0) cover every detail  
  of the framework.
- There is a [PDF version](https://www.yiiframework.com/doc/download/yii-guide-2.0-en.pdf) of the Definitive Guide  
  and a [Definitive Guide Mirror](http://stuff.cebe.cc/yii2docs/) which is updated every 15 minutes.
- For Yii 1.1 users, there is [Upgrading from Yii 1.1](https://www.yiiframework.com/doc/guide/2.0/en/intro-upgrade-from-v1)  
  to get an idea of what has changed in 2.0.

## [](#Community "Community")Community

- Participate in [discussions at forums](https://www.yiiframework.com/forum/).
- [Community Slack](https://join.slack.com/t/yii/shared_invite/MjIxMjMxMTk5MTU1LTE1MDE3MDAwMzMtM2VkMTMyMjY1Ng) and [Chat in IRC](https://www.yiiframework.com/chat/).
- Follow us on [Facebook](https://www.facebook.com/groups/yiitalk/), [Twitter](https://twitter.com/yiiframework)  
  and [GitHub](https://github.com/yiisoft/yii2).
- Check [other communities](https://github.com/yiisoft/yii2/wiki/communities).

## [](#Contributing "Contributing")Contributing

The framework is [Open Source](LICENSE.md) powered by [an excellent community](https://github.com/yiisoft/yii2/graphs/contributors).

You may join us and:

- [Report an issue](docs/internals/report-an-issue.md)
- [Translate documentation or messages](docs/internals/translation-workflow.md)
- [Give us feedback or start a design discussion](https://www.yiiframework.com/forum/index.php/forum/42-general-discussions-for-yii-20/)
- [Contribute to the core code or fix bugs](docs/internals/git-workflow.md)
- [Become a sponsor](#sponsoring)

### [](#Reporting-Security-issues "Reporting Security issues")Reporting Security issues

Please refer to a [special page at the website](https://www.yiiframework.com/security/)  
describing proper workflow for security issue reports.

### [](#Directory-Structure "Directory Structure")Directory Structure

1  
2  
3  
4

build/ internally used build tools  
docs/ documentation  
framework/ core framework code  
tests/ tests of the core framework code

### [](#Spreading-the-Word "Spreading the Word")Spreading the Word

Acknowledging or citing Yii 2 is as important as direct contributions.

**In presentations**

If you are giving a presentation or talk featuring work that makes use of Yii 2 and would like to acknowledge it,  
we suggest using [our logo](https://www.yiiframework.com/logo/) on your title slide.

**In projects**

If you are using Yii 2 as part of an OpenSource project, a way to acknowledge it is to  
[use a special badge](https://img.shields.io/badge/Powered_by-Yii_Framework-green.svg?style=flat) in your README:

![Yii2](https://img.shields.io/badge/Powered_by-Yii_Framework-green.svg?style=flat)

If your code is hosted at GitHub, you can place the following in your README.md file to get the badge:

1

\[!\[Yii2\](https://img.shields.io/badge/Powered\_by-Yii\_Framework-green.svg?style=flat)\](https://www.yiiframework.com/)

### [](#Sponsoring "Sponsoring")Sponsoring

Support this project by becoming a sponsor or a backer.

[![OpenCollective sponsors](https://opencollective.com/yiisoft/sponsors/badge.svg)](https://opencollective.com/yiisoft) [![OpenCollective backers](https://opencollective.com/yiisoft/backers/badge.svg)](https://opencollective.com/yiisoft)

Share

- [php](/tags/php/)
- [yii2](/tags/yii2/)

[2020-10-12](/2020/10/12/react/)

[React](/categories/React/)

# [React](/2020/10/12/react/)

# [](#React-middot "React ·    ")[React](https://reactjs.org/) · [![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://github.com/facebook/react/blob/master/LICENSE) [![npm version](https://img.shields.io/npm/v/react.svg?style=flat)](https://www.npmjs.com/package/react) [![CircleCI Status](https://circleci.com/gh/facebook/react.svg?style=shield&circle-token=:circle-token)](https://circleci.com/gh/facebook/react) [![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://reactjs.org/docs/how-to-contribute.html#your-first-pull-request)

React is a JavaScript library for building user interfaces.

- **Declarative:** React makes it painless to create interactive UIs. Design simple views for each state in your application, and React will efficiently update and render just the right components when your data changes. Declarative views make your code more predictable, simpler to understand, and easier to debug.
- **Component-Based:** Build encapsulated components that manage their own state, then compose them to make complex UIs. Since component logic is written in JavaScript instead of templates, you can easily pass rich data through your app and keep state out of the DOM.
- **Learn Once, Write Anywhere:** We don’t make assumptions about the rest of your technology stack, so you can develop new features in React without rewriting existing code. React can also render on the server using Node and power mobile apps using [React Native](https://reactnative.dev/).

[Learn how to use React in your own project](https://reactjs.org/docs/getting-started.html).

## [](#Installation "Installation")Installation

React has been designed for gradual adoption from the start, and **you can use as little or as much React as you need**:

- Use [Online Playgrounds](https://reactjs.org/docs/getting-started.html#online-playgrounds) to get a taste of React.
- [Add React to a Website](https://reactjs.org/docs/add-react-to-a-website.html) as a `<script>` tag in one minute.
- [Create a New React App](https://reactjs.org/docs/create-a-new-react-app.html) if you’re looking for a powerful JavaScript toolchain.

You can use React as a `<script>` tag from a [CDN](https://reactjs.org/docs/cdn-links.html), or as a `react` package on [npm](https://www.npmjs.com/package/react).

## [](#Documentation "Documentation")Documentation

You can find the React documentation [on the website](https://reactjs.org/docs).

Check out the [Getting Started](https://reactjs.org/docs/getting-started.html) page for a quick overview.

The documentation is divided into several sections:

- [Tutorial](https://reactjs.org/tutorial/tutorial.html)
- [Main Concepts](https://reactjs.org/docs/hello-world.html)
- [Advanced Guides](https://reactjs.org/docs/jsx-in-depth.html)
- [API Reference](https://reactjs.org/docs/react-api.html)
- [Where to Get Support](https://reactjs.org/community/support.html)
- [Contributing Guide](https://reactjs.org/docs/how-to-contribute.html)

You can improve it by sending pull requests to [this repository](https://github.com/reactjs/reactjs.org).

## [](#Examples "Examples")Examples

We have several examples [on the website](https://reactjs.org/). Here is the first one to get you started:

1  
2  
3  
4  
5  
6  
7  
8

function HelloMessage({ name }) {  
 return <div>Hello {name}</div>;  
}

ReactDOM.render(  
 <HelloMessage name="Taylor" />,  
 document.getElementById('container')  
);

This example will render “Hello Taylor” into a container on the page.

You’ll notice that we used an HTML-like syntax; [we call it JSX](https://reactjs.org/docs/introducing-jsx.html). JSX is not required to use React, but it makes code more readable, and writing it feels like writing HTML. If you’re using React as a `<script>` tag, read [this section](https://reactjs.org/docs/add-react-to-a-website.html#optional-try-react-with-jsx) on integrating JSX; otherwise, the [recommended JavaScript toolchains](https://reactjs.org/docs/create-a-new-react-app.html) handle it automatically.

## [](#Contributing "Contributing")Contributing

The main purpose of this repository is to continue evolving React core, making it faster and easier to use. Development of React happens in the open on GitHub, and we are grateful to the community for contributing bugfixes and improvements. Read below to learn how you can take part in improving React.

### [](#Code-of-Conduct "Code of Conduct")[Code of Conduct](https://code.fb.com/codeofconduct)

Facebook has adopted a Code of Conduct that we expect project participants to adhere to. Please read [the full text](https://code.fb.com/codeofconduct) so that you can understand what actions will and will not be tolerated.

### [](#Contributing-Guide "Contributing Guide")[Contributing Guide](https://reactjs.org/contributing/how-to-contribute.html)

Read our [contributing guide](https://reactjs.org/contributing/how-to-contribute.html) to learn about our development process, how to propose bugfixes and improvements, and how to build and test your changes to React.

### [](#Good-First-Issues "Good First Issues")Good First Issues

To help you get your feet wet and get you familiar with our contribution process, we have a list of [good first issues](https://github.com/facebook/react/labels/good%20first%20issue) that contain bugs which have a relatively limited scope. This is a great place to get started.

### [](#License "License")License

React is [MIT licensed](./LICENSE).

Share

- [javascript](/tags/javascript/)
- [react](/tags/react/)

[2020-09-12](/2020/09/12/vue/)

[Vue](/categories/Vue/)

# [Vue](/2020/09/12/vue/)

[![Vue logo](https://vuejs.org/images/logo.png)](https://vuejs.org)

[![Build Status](https://img.shields.io/circleci/project/github/vuejs/vue/dev.svg?sanitize=true)](https://circleci.com/gh/vuejs/vue/tree/dev) [![Coverage Status](https://img.shields.io/codecov/c/github/vuejs/vue/dev.svg?sanitize=true)](https://codecov.io/github/vuejs/vue?branch=dev) [![Downloads](https://img.shields.io/npm/dm/vue.svg?sanitize=true)](https://npmcharts.com/compare/vue?minimal=true) [![Version](https://img.shields.io/npm/v/vue.svg?sanitize=true)](https://www.npmjs.com/package/vue) [![License](https://img.shields.io/npm/l/vue.svg?sanitize=true)](https://www.npmjs.com/package/vue) [![Chat](https://img.shields.io/badge/chat-on%20discord-7289da.svg?sanitize=true)](https://chat.vuejs.org/)  
[![Build Status](https://app.saucelabs.com/buildstatus/vuejs)](https://app.saucelabs.com/builds/50f8372d79f743a3b25fb6ca4851ca4c)

## Supporting Vue.js

Vue.js is an MIT-licensed open source project with its ongoing development made possible entirely by the support of these awesome [backers](https://github.com/vuejs/vue/blob/dev/BACKERS.md). If you’d like to join them, please consider:

- [Become a backer or sponsor on Patreon](https://www.patreon.com/evanyou).
- [Become a backer or sponsor on Open Collective](https://opencollective.com/vuejs).
- [One-time donation via PayPal or crypto-currencies.](https://vuejs.org/support-vuejs/#One-time-Donations)

#### [](#What’s-the-difference-between-Patreon-and-OpenCollective "What’s the difference between Patreon and OpenCollective?")What’s the difference between Patreon and OpenCollective?

Funds donated via Patreon go directly to support Evan You’s full-time work on Vue.js. Funds donated via OpenCollective are managed with transparent expenses and will be used for compensating work and expenses for core team members or sponsoring community events. Your name/logo will receive proper recognition and exposure by donating on either platform.

### Special Sponsors

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/autocode.svg?sanitize=true)](https://autocode.com/)

### Platinum Sponsors

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/vueschool.png)](https://vueschool.io/?utm_source=Vuejs.org&utm_medium=Banner&utm_campaign=Sponsored%20Banner&utm_content=V1)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/vehikl.png)](https://vehikl.com/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/retool.png)](https://retool.com/?utm_source=sponsor&utm_campaign=vue)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/passionate_people.png)](https://passionatepeople.io/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/storyblok.png)](https://www.storyblok.com)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/ionic.png)](https://ionicframework.com/vue?utm_source=partner&utm_medium=referral&utm_campaign=vuesponsorship&utm_content=vuedocs)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/nuxt.png)](https://nuxtjs.org/)

### Platinum Sponsors (China)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/dcloud.gif)](http://www.dcloud.io/?hmsr=vuejsorg&hmpl=&hmcu=&hmkw=&hmci=)

### Gold Sponsors

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/vuemastery.png)](https://www.vuemastery.com/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/laravel.png)](https://laravel.com)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/html_burger.png)](https://htmlburger.com)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/frontendlove.png)](https://www.frontenddeveloperlove.com/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/onsen_ui.png)](https://onsen.io/vue/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/neds.png)](https://neds.com.au/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/icons_8.png)](https://icons8.com/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/vuejobs.png)](https://vuejobs.com/?ref=vuejs)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/tidelift.png)](https://tidelift.com/subscription/npm/vue)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/firestick_tricks.png)](https://www.firesticktricks.com/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/intygrate.png)](https://intygrate.com/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/shopware_ag.png)](http://en.shopware.com/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/vpnranks.png)](https://www.vpnranks.com/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/bacancy_technology.png)](https://www.bacancytechnology.com/hire-vuejs-developer)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/bestvpn_co.png)](https://www.bestvpn.co/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/y8.png)](https://www.y8.com/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/devexpress.png)](https://js.devexpress.com/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/fastcoding_inc.svg?sanitize=true)](https://fastcoding.jp/javascript/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/usave.png)](https://usave.co.uk/utilities/broadband)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/foo.png)](https://www.foo.software)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/flatlogic_templates.svg?sanitize=true)](https://flatlogic.com/templates)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/moovweb.png)](http://moovweb.com/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/vpn_review.png)](https://vpn-review.com/netflix-vpn)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/tendermint.png)](https://cosmos.network/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/okay.png)](https://www.okayhq.com/)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/vpsserver_com.png)](https://www.vpsserver.com)

[![](https://raw.githubusercontent.com/vuejs/vuejs.org/master/themes/vue/source/images/aussiecasinohex.svg?sanitize=true)](https://aussiecasinohex.com/)

### Sponsors via [Open Collective](https://opencollective.com/vuejs)

#### Platinum

[![](https://opencollective.com/vuejs/tiers/platinum-sponsors/0/avatar.svg?sanitize=true)](https://opencollective.com/vuejs/tiers/platinum-sponsors/0/website)  
[![](https://opencollective.com/vuejs/tiers/platinum-sponsors/1/avatar.svg?sanitize=true)](https://opencollective.com/vuejs/tiers/platinum-sponsors/1/website)

#### Gold

[![](https://opencollective.com/vuejs/tiers/gold-sponsors/0/avatar.svg?sanitize=true)](https://opencollective.com/vuejs/tiers/gold-sponsors/0/website)  
[![](https://opencollective.com/vuejs/tiers/gold-sponsors/1/avatar.svg?sanitize=true)](https://opencollective.com/vuejs/tiers/gold-sponsors/1/website)  
[![](https://opencollective.com/vuejs/tiers/gold-sponsors/2/avatar.svg?sanitize=true)](https://opencollective.com/vuejs/tiers/gold-sponsors/2/website)  
[![](https://opencollective.com/vuejs/tiers/gold-sponsors/3/avatar.svg?sanitize=true)](https://opencollective.com/vuejs/tiers/gold-sponsors/3/website)  
[![](https://opencollective.com/vuejs/tiers/gold-sponsors/4/avatar.svg?sanitize=true)](https://opencollective.com/vuejs/tiers/gold-sponsors/4/website)

---

## [](#Introduction "Introduction")Introduction

Vue (pronounced `/vjuː/`, like view) is a **progressive framework** for building user interfaces. It is designed from the ground up to be incrementally adoptable, and can easily scale between a library and a framework depending on different use cases. It consists of an approachable core library that focuses on the view layer only, and an ecosystem of supporting libraries that helps you tackle complexity in large Single-Page Applications.

#### [](#Browser-Compatibility "Browser Compatibility")Browser Compatibility

Vue.js supports all browsers that are [ES5-compliant](https://kangax.github.io/compat-table/es5/) (IE8 and below are not supported).

## [](#Ecosystem "Ecosystem")Ecosystem

Project

Status

Description

[vue-router](https://github.com/vuejs/vue-router)

[![vue-router-status](https://img.shields.io/npm/v/vue-router.svg)](https://npmjs.com/package/vue-router)

Single-page application routing

[vuex](https://github.com/vuejs/vuex)

[![vuex-status](https://img.shields.io/npm/v/vuex.svg)](https://npmjs.com/package/vuex)

Large-scale state management

[vue-cli](https://github.com/vuejs/vue-cli)

[![vue-cli-status](https://img.shields.io/npm/v/@vue/cli.svg)](https://npmjs.com/package/@vue/cli)

Project scaffolding

[vue-loader](https://github.com/vuejs/vue-loader)

[![vue-loader-status](https://img.shields.io/npm/v/vue-loader.svg)](https://npmjs.com/package/vue-loader)

Single File Component (`*.vue` file) loader for webpack

[vue-server-renderer](https://github.com/vuejs/vue/tree/dev/packages/vue-server-renderer)

[![vue-server-renderer-status](https://img.shields.io/npm/v/vue-server-renderer.svg)](https://npmjs.com/package/vue-server-renderer)

Server-side rendering support

[vue-class-component](https://github.com/vuejs/vue-class-component)

[![vue-class-component-status](https://img.shields.io/npm/v/vue-class-component.svg)](https://npmjs.com/package/vue-class-component)

TypeScript decorator for a class-based API

[vue-rx](https://github.com/vuejs/vue-rx)

[![vue-rx-status](https://img.shields.io/npm/v/vue-rx.svg)](https://npmjs.com/package/vue-rx)

RxJS integration

[vue-devtools](https://github.com/vuejs/vue-devtools)

[![vue-devtools-status](https://img.shields.io/chrome-web-store/v/nhdogjmejiglipccpnnnanhbledajbpd.svg)](https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd)

Browser DevTools extension

## [](#Documentation "Documentation")Documentation

To check out [live examples](https://vuejs.org/v2/examples/) and docs, visit [vuejs.org](https://vuejs.org/).

## [](#Questions "Questions")Questions

For questions and support please use [the official forum](https://forum.vuejs.org/) or [community chat](https://chat.vuejs.org/). The issue list of this repo is **exclusively** for bug reports and feature requests.

## [](#Issues "Issues")Issues

Please make sure to read the [Issue Reporting Checklist](https://github.com/vuejs/vue/blob/dev/.github/CONTRIBUTING.md#issue-reporting-guidelines) before opening an issue. Issues not conforming to the guidelines may be closed immediately.

## [](#Changelog "Changelog")Changelog

Detailed changes for each release are documented in the [release notes](https://github.com/vuejs/vue/releases).

## [](#Stay-In-Touch "Stay In Touch")Stay In Touch

- [Twitter](https://twitter.com/vuejs)
- [Blog](https://medium.com/the-vue-point)
- [Job Board](https://vuejobs.com/?ref=vuejs)

## [](#Contribution "Contribution")Contribution

Please make sure to read the [Contributing Guide](https://github.com/vuejs/vue/blob/dev/.github/CONTRIBUTING.md) before making a pull request. If you have a Vue-related project/component/tool, add it with a pull request to [this curated list](https://github.com/vuejs/awesome-vue)!

Thank you to all the people who already contributed to Vue!

[![](https://opencollective.com/vuejs/contributors.svg?width=890)](https://github.com/vuejs/vue/graphs/contributors)

## [](#License "License")License

[MIT](https://opensource.org/licenses/MIT)

Copyright (c) 2013-present, Yuxi (Evan) You

Share

- [javascript](/tags/javascript/)
- [vue](/tags/vue/)

[2020-08-12](/2020/08/12/jquery/)

[JQuery](/categories/JQuery/)

# [JQuery](/2020/08/12/jquery/)

# [](#jQuery-—-New-Wave-JavaScript "jQuery — New Wave JavaScript")[jQuery](https://jquery.com/) — New Wave JavaScript

[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fjquery%2Fjquery.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Fjquery%2Fjquery?ref=badge_shield)

[![Gitter](https://badges.gitter.im/jquery/jquery.svg)](https://gitter.im/jquery/jquery?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge)

## [](#Contribution-Guides "Contribution Guides")Contribution Guides

In the spirit of open source software development, jQuery always encourages community code contribution. To help you get started and before you jump into writing code, be sure to read these important contribution guidelines thoroughly:

1.  [Getting Involved](https://contribute.jquery.org/)
2.  [Core Style Guide](https://contribute.jquery.org/style-guide/js/)
3.  [Writing Code for jQuery Foundation Projects](https://contribute.jquery.org/code/)

## [](#Environments-in-which-to-use-jQuery "Environments in which to use jQuery")Environments in which to use jQuery

- [Browser support](https://jquery.com/browser-support/)
- jQuery also supports Node, browser extensions, and other non-browser environments.

## [](#What-you-need-to-build-your-own-jQuery "What you need to build your own jQuery")What you need to build your own jQuery

To build jQuery, you need to have the latest Node.js/npm and git 1.7 or later. Earlier versions might work, but are not supported.

For Windows, you have to download and install [git](https://git-scm.com/downloads) and [Node.js](https://nodejs.org/en/download/).

macOS users should install [Homebrew](https://brew.sh/). Once Homebrew is installed, run `brew install git` to install git,  
and `brew install node` to install Node.js.

Linux/BSD users should use their appropriate package managers to install git and Node.js, or build from source  
if you swing that way. Easy-peasy.

## [](#How-to-build-your-own-jQuery "How to build your own jQuery")How to build your own jQuery

First, [clone the jQuery git repo](https://help.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository).

Then, enter the jquery directory and run the build script:

1

cd jquery && npm run build

The built version of jQuery will be put in the `dist/` subdirectory, along with the minified copy and associated map file.

If you want to create custom build or help with jQuery development, it would be better to install [grunt command line interface](https://github.com/gruntjs/grunt-cli) as a global package:

1

npm install -g grunt-cli

Make sure you have `grunt` installed by testing:

1

grunt -V

Now by running the `grunt` command, in the jquery directory, you can build a full version of jQuery, just like with an `npm run build` command:

1

grunt

There are many other tasks available for jQuery Core:

1

grunt -help

### [](#Modules "Modules")Modules

Special builds can be created that exclude subsets of jQuery functionality.  
This allows for smaller custom builds when the builder is certain that those parts of jQuery are not being used.  
For example, an app that only used JSONP for `$.ajax()` and did not need to calculate offsets or positions of elements could exclude the offset and ajax/xhr modules.

Any module may be excluded except for `core`, and `selector`. To exclude a module, pass its path relative to the `src` folder (without the `.js` extension).

Some example modules that can be excluded are:

- **ajax**: All AJAX functionality: `$.ajax()`, `$.get()`, `$.post()`, `$.ajaxSetup()`, `.load()`, transports, and ajax event shorthands such as `.ajaxStart()`.
- **ajax/xhr**: The XMLHTTPRequest AJAX transport only.
- **ajax/script**: The `<script>` AJAX transport only; used to retrieve scripts.
- **ajax/jsonp**: The JSONP AJAX transport only; depends on the ajax/script transport.
- **css**: The `.css()` method. Also removes **all** modules depending on css (including **effects**, **dimensions**, and **offset**).
- **css/showHide**: Non-animated `.show()`, `.hide()` and `.toggle()`; can be excluded if you use classes or explicit `.css()` calls to set the `display` property. Also removes the **effects** module.
- **deprecated**: Methods documented as deprecated but not yet removed.
- **dimensions**: The `.width()` and `.height()` methods, including `inner-` and `outer-` variations.
- **effects**: The `.animate()` method and its shorthands such as `.slideUp()` or `.hide("slow")`.
- **event**: The `.on()` and `.off()` methods and all event functionality.
- **event/trigger**: The `.trigger()` and `.triggerHandler()` methods.
- **offset**: The `.offset()`, `.position()`, `.offsetParent()`, `.scrollLeft()`, and `.scrollTop()` methods.
- **wrap**: The `.wrap()`, `.wrapAll()`, `.wrapInner()`, and `.unwrap()` methods.
- **core/ready**: Exclude the ready module if you place your scripts at the end of the body. Any ready callbacks bound with `jQuery()` will simply be called immediately. However, `jQuery(document).ready()` will not be a function and `.on("ready", ...)` or similar will not be triggered.
- **deferred**: Exclude jQuery.Deferred. This also removes jQuery.Callbacks. _Note_ that modules that depend on jQuery.Deferred(AJAX, effects, core/ready) will not be removed and will still expect jQuery.Deferred to be there. Include your own jQuery.Deferred implementation or exclude those modules as well (`grunt custom:-deferred,-ajax,-effects,-core/ready`).
- **exports/global**: Exclude the attachment of global jQuery variables ($ and jQuery) to the window.
- **exports/amd**: Exclude the AMD definition.

The build process shows a message for each dependent module it excludes or includes.

##### [](#AMD-name "AMD name")AMD name

As an option, you can set the module name for jQuery’s AMD definition. By default, it is set to “jquery”, which plays nicely with plugins and third-party libraries, but there may be cases where you’d like to change this. Simply set the `"amd"` option:

1

grunt custom --amd="custom-name"

Or, to define anonymously, set the name to an empty string.

1

grunt custom --amd=""

#### [](#Custom-Build-Examples "Custom Build Examples")Custom Build Examples

To create a custom build, first check out the version:

1

git pull; git checkout VERSION

Where VERSION is the version you want to customize. Then, make sure all Node dependencies are installed:

1

npm install

Create the custom build using the `grunt custom` option, listing the modules to be excluded.

Exclude all **ajax** functionality:

1

grunt custom:-ajax

Excluding **css** removes modules depending on CSS: **effects**, **offset**, **dimensions**.

1

grunt custom:-css

Exclude a bunch of modules:

1

grunt custom:-ajax/jsonp,-css,-deprecated,-dimensions,-effects,-offset,-wrap

There is also a special alias to generate a build with the same configuration as the official jQuery Slim build is generated:

1

grunt custom:slim

For questions or requests regarding custom builds, please start a thread on the [Developing jQuery Core](https://forum.jquery.com/developing-jquery-core) section of the forum. Due to the combinatorics and custom nature of these builds, they are not regularly tested in jQuery’s unit test process.

## [](#Running-the-Unit-Tests "Running the Unit Tests")Running the Unit Tests

Make sure you have the necessary dependencies:

1

npm install

Start `grunt watch` or `npm start` to auto-build jQuery as you work:

1

grunt watch

Run the unit tests with a local server that supports PHP. Ensure that you run the site from the root directory, not the “test” directory. No database is required. Pre-configured php local servers are available for Windows and Mac. Here are some options:

- Windows: [WAMP download](http://www.wampserver.com/en/)
- Mac: [MAMP download](https://www.mamp.info/en/downloads/)
- Linux: [Setting up LAMP](https://www.linux.com/learn/tutorials/288158-easy-lamp-server-installation)
- [Mongoose (most platforms)](https://code.google.com/p/mongoose/)

## [](#Building-to-a-different-directory "Building to a different directory")Building to a different directory

To copy the built jQuery files from `/dist` to another directory:

1

grunt && grunt dist:/path/to/special/location/

With this example, the output files would be:

1  
2

/path/to/special/location/jquery.js  
/path/to/special/location/jquery.min.js

To add a permanent copy destination, create a file in `dist/` called “.destination.json”. Inside the file, paste and customize the following:

1  
2  
3  
4

{  
 "/Absolute/path/to/other/destination": true  
}

Additionally, both methods can be combined.

## [](#Essential-Git "Essential Git")Essential Git

As the source code is handled by the Git version control system, it’s useful to know some features used.

### [](#Cleaning "Cleaning")Cleaning

If you want to purge your working directory back to the status of upstream, the following commands can be used (remember everything you’ve worked on is gone after these):

1  
2

git reset --hard upstream/main  
git clean -fdx

### [](#Rebasing "Rebasing")Rebasing

For feature/topic branches, you should always use the `--rebase` flag to `git pull`, or if you are usually handling many temporary “to be in a github pull request” branches, run the following to automate this:

1

git config branch.autosetuprebase local

(see `man git-config` for more information)

### [](#Handling-merge-conflicts "Handling merge conflicts")Handling merge conflicts

If you’re getting merge conflicts when merging, instead of editing the conflicted files manually, you can use the feature  
`git mergetool`. Even though the default tool `xxdiff` looks awful/old, it’s rather useful.

The following are some commands that can be used there:

- `Ctrl + Alt + M` \- automerge as much as possible
- `b` \- jump to next merge conflict
- `s` \- change the order of the conflicted lines
- `u` \- undo a merge
- `left mouse button` \- mark a block to be the winner
- `middle mouse button` \- mark a line to be the winner
- `Ctrl + S` \- save
- `Ctrl + Q` \- quit

## [](#QUnit-Reference "QUnit Reference")[QUnit](https://api.qunitjs.com/) Reference

### [](#Test-methods "Test methods")Test methods

1  
2  
3

expect( numAssertions );  
stop();  
start();

_Note_: QUnit’s eventual addition of an argument to stop/start is ignored in this test suite so that start and stop can be passed as callbacks without worrying about their parameters.

### [](#Test-assertions "Test assertions")Test assertions

1  
2  
3  
4  
5  
6  
7  
8

ok( value, \[message\] );  
equal( actual, expected, \[message\] );  
notEqual( actual, expected, \[message\] );  
deepEqual( actual, expected, \[message\] );  
notDeepEqual( actual, expected, \[message\] );  
strictEqual( actual, expected, \[message\] );  
notStrictEqual( actual, expected, \[message\] );  
throws( block, \[expected\], \[message\] );

## [](#Test-Suite-Convenience-Methods-Reference-See-test-data-testinit-js "Test Suite Convenience Methods Reference (See test/data/testinit.js)")Test Suite Convenience Methods Reference (See [test/data/testinit.js](https://github.com/jquery/jquery/blob/main/test/data/testinit.js))

### [](#Returns-an-array-of-elements-with-the-given-IDs "Returns an array of elements with the given IDs")Returns an array of elements with the given IDs

1

q( ... );

Example:

1  
2  
3

q("main", "foo", "bar");

=\> \[ div#main, span#foo, input#bar \]

### [](#Asserts-that-a-selection-matches-the-given-IDs "Asserts that a selection matches the given IDs")Asserts that a selection matches the given IDs

1

t( testName, selector, \[ "array", "of", "ids" \] );

Example:

1

t("Check for something", "//\[a\]", \["foo", "bar"\]);

### [](#Fires-a-native-DOM-event-without-going-through-jQuery "Fires a native DOM event without going through jQuery")Fires a native DOM event without going through jQuery

1

fireNative( node, eventType )

Example:

1

fireNative( jQuery("#elem")\[0\], "click" );

### [](#Add-random-number-to-url-to-stop-caching "Add random number to url to stop caching")Add random number to url to stop caching

1

url( "some/url" );

Example:

1  
2  
3  
4  
5  
6  
7  
8

url("index.html");

=\> "data/index.html?10538358428943"

url("mock.php?foo=bar");

=\> "data/mock.php?foo=bar&10538358345554"

### [](#Run-tests-in-an-iframe "Run tests in an iframe")Run tests in an iframe

Some tests may require a document other than the standard test fixture, and  
these can be run in a separate iframe. The actual test code and assertions  
remain in jQuery’s main test files; only the minimal test fixture markup  
and setup code should be placed in the iframe file.

1  
2  
3  
4  
5  
6

testIframe( testName, fileName,  
 function testCallback(  
 assert, jQuery, window, document,  
 \[ additional args \] ) {  
 ...  
 } );

This loads a page, constructing a url with fileName `"./data/" + fileName`.  
The iframed page determines when the callback occurs in the test by  
including the “/test/data/iframeTest.js” script and calling  
`startIframeTest( [ additional args ] )` when appropriate. Often this  
will be after either document ready or `window.onload` fires.

The `testCallback` receives the QUnit `assert` object created by `testIframe`  
for this test, followed by the global `jQuery`, `window`, and `document` from  
the iframe. If the iframe code passes any arguments to `startIframeTest`,  
they follow the `document` argument.

## [](#Questions "Questions?")Questions?

If you have any questions, please feel free to ask on the  
[Developing jQuery Core forum](https://forum.jquery.com/developing-jquery-core) or in #jquery on irc.freenode.net.

Share

- [javascript](/tags/javascript/)
- [jquery](/tags/jquery/)

1[2](/page/2/)[Next »](/page/2/)

### Tags

- [C](/tags/C/)
- [Docker](/tags/Docker/)
- [Go](/tags/Go/)
- [Kubernetes](/tags/Kubernetes/)
- [NoSQL](/tags/NoSQL/)
- [composer](/tags/composer/)
- [javascript](/tags/javascript/)
- [jquery](/tags/jquery/)
- [laravel](/tags/laravel/)
- [php](/tags/php/)
- [postman](/tags/postman/)
- [react](/tags/react/)
- [redis](/tags/redis/)
- [vue](/tags/vue/)
- [yii2](/tags/yii2/)

### Recent Posts

- [Kubernetes (K8s)](/2021/02/12/kubernetes/)
- [PHP](/2021/02/11/php/)
- [About](/2021/02/02/about/)
- [Redis](/2021/01/12/redis/)
- [Postman](/2021/01/11/postman/)

### Categories

- [Composer](/categories/Composer/)
- [Jenkins](/categories/Jenkins/)
- [JQuery](/categories/JQuery/)
- [Kubernetes](/categories/Kubernetes/)
- [Laravel](/categories/Laravel/)
- [PHP](/categories/PHP/)
- [Postman](/categories/Postman/)
- [React](/categories/React/)
- [Redis](/categories/Redis/)
- [Selenium](/categories/Selenium/)
- [Vue](/categories/Vue/)
- [Yii2](/categories/Yii2/)

### Archives

- [February 2021](/archives/2021/02/)
- [January 2021](/archives/2021/01/)
- [December 2020](/archives/2020/12/)
- [November 2020](/archives/2020/11/)
- [October 2020](/archives/2020/10/)
- [September 2020](/archives/2020/09/)
- [August 2020](/archives/2020/08/)
- [July 2020](/archives/2020/07/)

© 2021 By Autoload  
Driven - [Hexo](https://hexo.io/)|Theme - [Auto](https://github.com/autoload/hexo-theme-auto)

[Home](/) [Archives](/archives) [Categories](/categories) [Tags](/tags) [About](/about)## 目标

去除 iconfinder 上 icon 的水印

### 原理

利用水印像素点和原图像素点颜色合并的原理，如果拥有加过水印的图片和水印图片，就可以反向推出原图原像素点的颜色；前提是你得拥有他的水印图片
