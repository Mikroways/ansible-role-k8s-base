# mikroways.m7s_k8s_base

Install some requirements on k8s management node (usually master nodes) so
ansible k8s module can easily.

As dependencies of k8s ansible module, are the following python modules:

* `python >= 2.7`
* `openshift >= 0.6`
* `PyYAML >= 3.11`

This role provide with those dependencies and other packages useful for cluster
management.

## Role Variables

This role define packages to be installed as requirements for our daily work
with k8s. You can change package list changing some of the following variables:

```yaml
m7s_k8s_base_install_packages:
  - name: git
    apt: git
    yum: git
    state: present
  - name: python-setuptools
    apt: python-setuptools
    yum: python-setuptools
    state: present
  - name: pip
    apt: python-pip
    yum: python2-pip
    state: present
  - name: nfs-utils
    yum: nfs-utils
    state: present
  - name: jq
    apt: jq
    yum: jq
    state: present
  - name: nfs-common
    apt: nfs-common
    state: present
  - name: nfs-kernel-server
    apt: nfs-kernel-server
    state: present
  - name: python-openshift
    yum: python-openshift
    state: present

package_state: present
update_cache: true

m7s_k8s_base_python_modules:
  - name: PyYAML
  - name: openshift
```

## Example Playbook

  - hosts: kube-master
    roles:
       - mikroways.m7s_k8s_base

## Changelog

### [2.0.0] - 2020-06-17
#### Added
- Debian family support
- Update cache for apt and yum
#### Updated
- Change package list definition
- Change pip module list definition - Now version is supported

### [1.0.0] - 2019-12-22
#### Added
- First stable version
- CentOS support
- pip modules support

# License

GPLv2
