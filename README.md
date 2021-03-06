# Configurable Local DaemonSet

A RESTful local daemonset (similiar to Kubernetes, but local).

![Deployment](images/deployment.png)

All data is held in memory, all transfer is via JSON.

## Features

- persists state to a local configuration file
- uses daemon __processes__
- linux-based

Why __processes__ rather than __goroutines__ or __threads__?
For memory and durability reasons: process memory is safer than
shared threadspace memory, and process crashes will be local
whereas thread crashes will affect the entire process.
 
## Prerequisites

- __dep__ is required

This is the latest Go dependency manager (until `vgo` arrives).

#### Installation

OS/X:

    $ brew install dep
    $ brew upgrade dep

Install script:

    $ curl https://raw.githubusercontent.com/golang/dep/master/install.sh | sh

go get:

    $ go get -u github.com/golang/dep/cmd/dep

For further details on installing `dep`, please refer to the [documentation](https://github.com/golang/dep).

## Installation

- __Go__ is required (version 1.10 or later)

Fetch this project as follows:

	$ go get -u github.com/mramshaw/colds

This could also be done with __git__ of course:

	$ git clone https://github.com/mramshaw/colds.git

Any dependencies will be fetched in the __build__ process.

## To Do

- [ ] Investigate upgrading to gRPC or HTTP2
