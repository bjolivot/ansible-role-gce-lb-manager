gce_lb_manager
==============

Manage Google Cloud Load Balancer and affect VM


Role Variables
--------------

Mandatory vars :
 - gce_lb_name: name of the loadbalancer
 - gce_region: where to deploy (ex: europe-west1)
 - gce_service_account_email: gce service account email 
 - gce_pem_file: pem filename associated with service account, need to be saved at playbook root dir
 - gce_project_id: project ID, found in google cloud console
 - gce_zone: VM zone (ex: "europe-west1-d")
 - gce_lb_member_inventory_group: inventory group containing member VMs
 - gce_lb_protocol: tcp or udp

Default var : 
 - gce_lb_state: present  # desired state of the LB (active,present,absent,deleted)


How to use 
----------

You need to :
 - define mandatory vars
 - put pem file at playbook's root directory
 - start on localhost with playbook.yml containing : 

        - name: Create LB
          become: true
          hosts: localhost
          roles: 
            - gce_lb_manager

License
-------

Licensed under the MIT License. See the [LICENSE](LICENSE) file for details.


Author Information
------------------

See my other "work on my computer" ansible things on https://www.github.com/bjolivot