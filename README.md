Ansible Role: Create OpenShift ISOs
=========

A role for creating OpenShift (OCP or OKD) ISO's for a Single Node or Cluster Deployment

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Example Playbook (see more in tests folder)
----------------

    - name: Create OpenShift ISOs
      hosts: localhost
      roles:
        - role: create-openshift-isos
          vars:
            openshift_distribution: "ocp"
            openshift_version: "stable"
            cluster_name: ocp
            base_domain: domain.local
            machine_cidr: '172.16.15.0/24'
            control_plane_nodes:
              - name: "{{ cluster_name | lower }}-sn-01"
            pull_secret: '{"auths":{"cloud.openshift.com":{"auth":"...'
            ssh_keys:
              - ssh-rsa AAAAB3NzaC1yc2EAAAA...

License
-------

MIT

Author Information
------------------

This role was created in 2024 by [Lenny Shirley II](https://github.com/lennysh)
