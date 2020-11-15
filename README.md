# memcached-operator
Sample Kubernetes Operator based on operator-sdk for Golang

## Installation of Operator SDK

* Prerequisite 
* Download operator-sdk source code and compile locally

### Prerequisite

* docker
* kubectl
* settings for envirionment vars 
  ~~~
  GOROOT(=/usr/local/go)
  GOPATH(=~/Projects/goworkspace)
  PATH=$PATH:$GOROOT/bin:$GOPATH/bin
  ~~~~

### Download operator-sdk source code and compile locally

~~~
cd ~/Projects/goworkspace
git clone https://github.com/operator-framework/operator-sdk
git checkout master
cd operator-sdk
make install
~~~

***
operator-sdk would be located under $GOPATH/bin if the above compilation is successful.
***

## Quick Start

### Create a new project
~~~
cd ~/Projects/goworkspace
mkdir memcached-operator
operator-sdk init --domain=io.allen --repo=github.com/AllenShi/memcached-operator
~~~

***
operator-sdk init generates a go.mod file to be used with Go modules. The --repo=<path> flag is required when creating a project outside of $GOPATH/src, as scaffolded files require a valid module path. 
***
  
### Create a new API and Controller

~~~
operator-sdk create api --group=cache --version=v1alpha1 --kind=Memcached
~~~

***
This will scaffold the Memcached resource API at api/v1alpha1/memcached_types.go and the controller at controllers/memcached_controller.go.
***

## Reference
1. [Golang Based Operator Tutorial](https://sdk.operatorframework.io/docs/building-operators/golang/tutorial/)
