
# Getting started with open62541 library


#### Arranging prerequisites
```sh
$ sudo apt-get install git build-essential gcc pkg-config cmake python python-six
```
#### Cloning open62541
```sh
$ git clone https://github.com/open62541/open62541.git
$ cd open62541
$ git submodule init
$ git submodule update
```
![IMG01](./01 Cloningopen 62541.png)

#### Building open62541
```sh
$ mkdir build
$ cd build
$ cmake -DUA_ENABLE_AMALGAMATION=ON -DUA_ENABLE_METHODCALLS=ON -DUA_NAMESPACE_ZERO=FULL ..
$ sudo make install
```

#### Building and running OPCUA examples using single-file release open62541.h
```sh
$ cd examples
$ gcc -std=c99 -I../build/ ../build/open62541.c tutorial_server_variable.c -o server
$ ./server
```
#### Open a Prosys OPC UA client to view/edit server nodes
**Address**: opc.tcp://<*IP address of server* / *localhost*>:4840

