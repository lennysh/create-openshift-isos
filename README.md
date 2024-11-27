Ansible Role: Create OpenShift ISOs
=========

A role for creating OpenShift (OCP or OKD) bare metal ISO's for a Single Node or Cluster Deployment

Testing Progress
--------------

- [x] Single Node
  - [x] Ignition file gets created
  - [x] ISO builds with embedded ignition file
  - [x] Static IP information (if provided) get's injected into the ISO
  - [x] OCP set to DHCP
  - [x] OKD set to DHCP
  - [x] OCP set to STATIC IP
  - [x] OKD set to STATIC IP
- [ ] Multi Node
  - [ ] install-config.yaml has all the needed values
  - [x] Manifests get created
  - [ ] Add any tasks to manipulate the manifests before building ignition files (masters schedulable for example...)
  - [x] Ignition files get created  
  - [x] ISO's build with embedded ignition files
  - [x] Static IP information (if provided) get's injected into the ISO's


Role Variables
--------------



Example Playbook (see more in tests folder)
----------------

    - name: Create OpenShift ISOs
      hosts: localhost
      roles:
        - role: create_openshift_isos
          vars:
            create_openshift_isos_openshift_distribution: "ocp"
            create_openshift_isos_openshift_version: "stable"
            create_openshift_isos_cluster_name: ocp
            create_openshift_isos_base_domain: domain.local
            create_openshift_isos_machine_cidr: '172.16.15.0/24'
            create_openshift_isos_control_plane_nodes:
              - name: "{{ create_openshift_isos_cluster_name | lower }}-sn-01"
            create_openshift_isos_pull_secret: '{"auths":{"cloud.openshift.com":{"auth":"...'
            create_openshift_isos_ssh_keys:
              - ssh-rsa AAAAB3NzaC1yc2EAAAA...

License
-------

MIT

Author Information
------------------

This role was created in 2024 by [Lenny Shirley II](https://github.com/lennysh)
