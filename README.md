# Eucalyptus Internal Deployment Playbook

This Ansible playbook is used by Eucalyptus Systems to do deployments of the
Eucalyptus Cloud for both development and test (using the [Eutester](https://github.com/eucalyptus/eutester)
framework and also [MicroQA](https://github.com/eucalyptus/micro-qa)).

# Manual Configuration

When using the playbook manually, one must create a `cloud_hosts` file and a
`cloud_config.yml` file. The `cloud_hosts` file is used for inventory of the
machines to be used when building the cloud. The hosts inventory is expected to
contain certain host _groups_ so that the component-specific packages can be
installed on machines hosting those components.

## Cloud Hosts File

The hosts file _must_ be called `cloud_hosts` and live in the root of the
playbook repository. You can view an example hosts file
[here](examples/cloud_hosts).

Required groups are:

* **cloud_controller**
* **cluster_controller**
* **storage_controller**
* **walrus**
* **node_controller**

## Cloud Configuration File

The configuration file _must_ be called `cloud_config.yml` and live in the root
of the playbook repository. You can view an example configuration file
[here](examples/cloud_config.yml).

All possible options are shown in the example configuration file.

