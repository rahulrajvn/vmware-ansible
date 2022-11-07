Following are the Anisble Playbooks to deploy an Kubernetes Cluster Over a Vmware environment. 

```
Vmware Vcenter Server
Ubuntu Base template 
```

Following Playbook to Clone the VM's from the base template.  
 https://github.com/rahulrajvn/vmware-ansible/blob/main/vm-cloning/Infra-Build.yml

> ansible-playbook Infra-Build.yml -e @secret-vars.yml


Following Playbook to Clean up the VM's, Shutdown and Delete.   
 https://github.com/rahulrajvn/vmware-ansible/blob/main/vm-cloning/Infra-Cleanup.yml

> ansible-playbook Infra-Cleanup.yml -e @secret-vars.yml


Create the Secret file with following details and run with   

> ansible-playbook with -e @secret-vars.yml

secret-vars.yml
```
vcenter_server: "XX.XX.XX.XX"
vcenter_user: "USERNAME"
vcenter_pass: "PASSWORD"
datacenter_name: "DC_NAME"
cluster_name: "CLUSTER_NAME"
template_vm:  "TEMPLATE VM NAME TO BE USED"
serv:
  - Sever1 << Give the required server name>>
  - Sever2 << Give the required server name>>
  - Sever3 << Give the required server name>>
```

