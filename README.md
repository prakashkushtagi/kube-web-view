# Kubernetes Web View

EARLY HACK

Goals:

* handling of any API resource: both core Kubernetes and CRDs
* permalink-friendly URL paths for giving links to colleagues (e.g. to help troubleshoot)
* option to work with multiple clusters
* allow listing different resource types on the same page (e.g. deployments and CRDs with same label)
* replicate some of the common `kubectl` features, e.g. `-l` (label selector) and `-L` (label columns)
* simple HTML, only add JavaScript where it adds value
* pluggable links, e.g. to link to other tools based on resource properties like labels (monitoring, reports, ..)
* optional: editing resources as YAML manifests (`kubectl edit`)

Non-goals:

* application management
* reporting/visualization

## Quickstart

This will run Kubernetes Web View locally with your existing Kubeconfig:

```
docker run -it -p 8080:8080 -u $(id -u) -v $HOME/.kube:/.kube hjacobs/kube-web-view
```

Open http://localhost:8080/ in your browser to see the UI.

## Running tests

Requires Python 3.7 and poetry:

```
$ make test
```

## Building the Docker image

```
$ make
```

## Developing Locally

```
$ poetry run python3 -m kube_web
```