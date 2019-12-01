# KubeVirt Resources Role

Deploy KubeVirt resources onto a cluster.

### Role Variables
| variable       | default           |choices           | comments  |
|:-------------|:-------------|:----------|:----------|
|admin_user|   | _optional_ |User with cluster-admin permissions.|
|admin_password| |_optional_|Password for **admin_user**.|
|platform|openshift |<ul><li>openshift</li><li>kubernetes</li></ul>|Cluster type.|
|namespace|kubevirt | |Namespace to create resources.|
|apb_action|provision| <ul><li>provision</li><li>deprovision</li></ul>|Action to perform.|
|release_manifest_url|https://github.com/kubevirt/kubevirt/releases|||
|kubevirt_template_dir|./templates||Location of the deployment template file.|
|registry_namespace | kubevirt | |Container image organization.|
|registry_url | docker.io | |Container image registry.|
| storage_role | storage-none | <ul><li>storage-none</li><li>storage-demo</li><li>storage-glusterfs</li></ul> | Storage role to install with KubeVirt.|
| network_role | network-multus | <ul><li>network-none</li><li>network-multus</li></ul> | Network role to install with KubeVirt.|
| version |0.13.7|<ul><li>0.13.7</li><li>0.9.6</li><li>0.8.0</li><li>0.7.0</li><li>0.6.0</li><li>0.5.0</li><li>0.4.1</li><li>0.4.0</li><li>0.3.0</li><li>0.2.0</li><li>0.1.0</li></ul>|KubeVirt release version.|
|default_vm_templates|<ul><li>vm-template-fedora</li><li>vm-template-windows2012r2</li><li>vm-template-rhel7></ul>|| Default vm templates to deploy with KubeVirt.|
|offline_template_dir| /opt/apb/kubevirt-templates || Offline VM template location specifed in the APB Dockerfile.|

### Usage

```
ansible-playbook -i inventory  -e version=0.13.7 -e apb_action=provision playbooks/kubevirt.yml
```
