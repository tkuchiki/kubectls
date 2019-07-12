# kubectls

kubectls is a kubectl version manager.

## Installation

```console
$ git clone https://github.com/tkuchiki/kubectls ~/.kubectls
```

## Usage

```console
$ export PATH=~/.kubectls/bin:$PATH
$ kubectls --help
Usage: kubectls

kubectls is kubectl version manager

Commands:
  install   Install kubectl
  path      Show current kubectl's abs path
  update    Update kubectls
  use       Set version
  versions  Show installed versions

Options:
  --version Show version

```

### Install

```console
$ kubectls install --help
Usage: kubectl install (VERSION|stable) [--set]

Install kubectl

Options:
  --set     Set version

$ kubectls install stable
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 46.3M  100 46.3M    0     0  47.7M      0 --:--:-- --:--:-- --:--:-- 47.7M

v1.15.0 is installed

$ kubectls install v1.14.0
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 46.4M  100 46.4M    0     0  57.4M      0 --:--:-- --:--:-- --:--:-- 57.4M

v1.14.0 is installed
```

```console
# Install and set version
$ kubectls install v1.13.0 --use
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100 42.2M  100 42.2M    0     0  71.9M      0 --:--:-- --:--:-- --:--:-- 71.9M

v1.13.0 is installed
v1.13.0 selected

$ kubectl version --short
Client Version: v1.13.0
Server Version: v1.12.8-gke.10
```

### Use

```
$ kubectls use --help
Usage: kubectl use [VERSION]

Set version

$ kubectls use v1.14.0
v1.14.0 selected

$ ./bin/kubectls use
1) v1.13.0
2) v1.14.0
3) v1.15.0
Which version? 3
v1.15.0 selected
```

### path

```console
$ kubectls path --help
Usage: kubectl path

Show current kubectl's abs path

$ kubectls path
/path/to/homedir/.kubectls/versions/v1.15.0/kubectl
```

### versions

```console
$ kubectls versions --help
Usage: kubectl versions

Show installed versions

$ kubectls versions
v1.13.0
v1.14.0
v1.15.0
```

### Update

```console
$ kubectls update --help
Usage: kubectl update

Update kubectls

$ kubectls update
Updated
```