# MetaCall Embedding Python Example

This example shows how to embed Python into C/C++ source code. The instructions are focused on Linux but it can be ported to other platforms easily.

## Dependencies

For building this example you need Python 3 to be installed in the system (including the dev dependencies). For debian based distros:

```bash
sudo apt-get install -y --no-install-recommends python3 python3-dev
```

## Build

Build the project, MetaCall dependency may require root permissions in order to be installed in the system.

```bash
git clone https://github.com/metacall/embedding-python-example.git
mkdir embedding-python-example/build && cd embedding-python-example/build
cmake ..
cmake --build . --target install
```

## Run

From project root directory, run the following commands:

```bash
export LOADER_LIBRARY_PATH="/usr/local/lib"
export LOADER_SCRIPT_PATH="`pwd`"
embedding-python-example
```

## Docker

Building and running with Docker:

```bash
docker build --build-arg DISABLE_CACHE=`date +%s` -t metacall/embedding-python-example .
docker run --rm -it metacall/embedding-python-example
```
