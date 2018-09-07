# How to Use this demo

## Dependencies

- JFrog CLI 1.19.1
- Go 1.11

## Set Go Home
```
export GOPATH=<PATH_TO_FOLDER_WHERE_THIS_REPO_WAS_CLONED>
export PATH=$PATH:$GOPATH/bin
```

## Install vgo
```
go get -u golang.org/x/vgo
```

## Add Artifactory instance to JFrog CLI
```
jfrog rt config
```

## Build and install project
```
cd $GOPATH/src/github.com/elioengcomp/hello
jfrog rt go --server-id=<ARTIFACTORY_ID> install <GO_VIRTUAL_REPO>
```

Example:

```
jfrog rt go --server-id=artifactory install go
```


## Publish Go modules
```
cd $GOPATH/src/github.com/elioengcomp/hello
jfrog rt gp <GO_LOCAL_REPO> <VERSION> --server-id=<ARTIFACTORY_ID> --deps=ALL --self=true
```

Example:

```
jfrog rt gp go-local v1.0.1 --server-id=artifactory --deps=ALL --self=true
```
