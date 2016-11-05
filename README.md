bastion Deployments
==============================

This repository contains the YAML templates that make up a series of
bastion BOSH deployments, using the format prescribed by the
[Genesis][1] utility.

The configuration is broken up into three logical strata: _global_,
_site_, and _environment_.  _Global_ defines the universal aspects of any
deployment, including overall job structure, constituent BOSH releases,
and invariant (or default) properties.  Each _site_ represents a single
IaaS (an AWS VPC, a vSphere cluster, etc.), and further refines the global
configuration for that infrastructure.  Each _environment_ represents a
single BOSH deployment, with specific network numbering, credentials,
domain names, etc.

For more information, see the READMEs scattered throughout this repository,
and check out `genesis help`.  You can download the Genesis program from
[Github][1]

Quickstart
----------

To create a new site:

    genesis new site NAME

To create a new environment

    cd site-name/
    genesis new environment NAME

To build the full BOSH manifest for an environment:

    cd site-name/env-name
    make manifest

... and then deploy it:

    cd site-name/env-name
    make deploy




[1]: https://github.com/starkandwayne/genesis
