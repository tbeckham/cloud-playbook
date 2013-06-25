# Eucalyptus Internal Deployment Playbook

This Ansible playbook is used by Eucalyptus Systems to do deployments of the
Eucalyptus Cloud for both development and test (using the [Eutester]()
framework).

# Manual Configuration

When using the playbook manually, one must create a `cloud_hosts` file and a
`cloud_config.yml` file. The `cloud_hosts` file is used for inventory of the
machines to be used when building the cloud. The hosts inventory is expected to
contain certain host _groups_ that are associated with different _roles_ in the
playbook.

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

If you are installing _enterprise_ packages, you can also use these optional
groups:

* **vmware_broker**
* **netapp_san**
* **equallogic_san**
* **emx_san**

## Cloud Configuration File

The configuration file _must_ be called `cloud_config.yml` and live in the root
of the playbook repository. You can view an example configuration file
[here](examples/cloud_config.yml).

Required arguments:

* **eucalyptus_commit_ref**: Commit ref for eucalyptus OSS packages

Optional arguments:

* **enterprise_commit_ref**: Commit ref for enterprise packages
* **ntp_server**: NTP server to sync with on all cloud hosts
* **pubkey**: Local public key file to add to `authorized_keys` on all cloud hosts

