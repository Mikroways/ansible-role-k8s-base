# mikroways.m7s-k8s-base

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
  - git
  - python-setuptools
  - python2-pip
  - nfs-utils
  - jq
  - python2-pyyaml
  - python2-openshift

m7s_k8s_base_python_modules: []
```

## Example Playbook

  - hosts: kube-master
    roles:
       - mikroways.m7s-k8s-base

# License

GPLv2

