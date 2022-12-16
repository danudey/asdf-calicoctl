(This repository, including this readme, is cribbed from https://github.com/asdf-community/asdf-kubectl, and may contain inaccuracies as a result. Fix this before making it publicly available.)

# asdf-calicoctl

[![Build Status](https://travis-ci.org/asdf-community/asdf-calicoctl.svg?branch=master)](https://travis-ci.org/asdf-community/asdf-calicoctl)

calicoctl plugin for [asdf](https://github.com/asdf-vm/asdf) version manager

## Install

```
asdf plugin-add calicoctl https://github.com/asdf-community/asdf-calicoctl.git
```

## Use

Check out the [asdf documentation](https://asdf-vm.com/#/core-manage-versions?id=install-version) for instructions on how to install and manage versions of calicoctl.

## Architecture Override
The `ASDF_calicoctl_OVERWRITE_ARCH` variable can be used to override the architecture that is used for determining which `calicoctl` build to download. The primary use case is when attempting to install an older version of `calicoctl` for use on an Apple M1 computer as `calicoctl` was not built for ARM at the time.

### Without `ASDF_calicoctl_OVERWRITE_ARCH`:

```
% asdf install calicoctl 1.18.17
Downloading calicoctl from https://storage.googleapis.com/kubernetes-release/release/v1.18.17/bin/darwin/arm64/calicoctl
```

### With `ASDF_calicoctl_OVERWRITE_ARCH`:

```
% ASDF_calicoctl_OVERWRITE_ARCH=amd64 asdf install calicoctl 1.18.17
Downloading calicoctl from https://storage.googleapis.com/kubernetes-release/release/v1.18.17/bin/darwin/amd64/calicoctl
```

