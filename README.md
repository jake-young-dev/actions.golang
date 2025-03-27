# actions.golang
[![tests](https://github.com/jake-young-dev/actions.golang/actions/workflows/test.yaml/badge.svg?branch=master)](https://github.com/jake-young-dev/actions.golang/actions/workflows/test.yaml)

An extremely simple github action to install golang and golang commands (using "go install") on linux hosts. This provides the ability to install and setup golang without node/typescript which is required when using [actions/setup-go](https://github.com/actions/setup-go). 


## Usage
I recommend using a tagged release to avoid unexpected changes that may come to the master branch, there may be breaking changes until v1.0.0
```yaml
    name: "install go"
    uses: jake-young-dev/actions.golang@master
    with:
        commands: |
            github.com/jake-young-dev/kelp@v0.0.9
```

#### Go verions
Go version is determined using the go.mod file in the root of working directory. Go files are pulled directly from the go download [site](https://go.dev/dl/) and all go commands are installed using 'go install'
#### Inputs
Some inputs are available to customize the installation
|Input|Required|Default|Description|
|---|---|---|---|
|arch|no|amd64|system architecture for golang
|purge|no|no|remove any golang files found on system before install
|commands|no|no default|links to any commands to be installed using 'go install'
#### Testing
A simple testing job is triggered on a push to the master branch, the job will create a mock go.mod file to ensure that one is present in testing container

<br />

## Issues
This repo is a as brain-dead as I could make it and is intended to be as fast and low-level as possible. Please open an issue for any problems or suggestions.
