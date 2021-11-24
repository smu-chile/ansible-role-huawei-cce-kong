Huawei Loadbalancer - Kong
=========

Ansible Role to setup a API Gateway Kong with a Huawei Load Balancer


Role Variables
--------------

```
      LB_ID: Load Balancer ID
      LB_VIP_SUBNET_ID: Loadbalancer Subnet Id 
      LB_PUBLIC_IP: Public IP of Loadbalancer
      KONG_HOSTNAME: DNS hostname of Loadbalancer to be created with external-dns. An A Record will be created. 
```

Example Playbook
----------------


```
- hosts: all
  become: no
  remote_user: "root"

  roles:
    - role: ansible-role-huawei-cce-kong
      LB_ID: "{{ lookup('env', 'LB_ID') }}"
      LB_VIP_SUBNET_ID: "{{ lookup('env', 'LB_SUBNET_ID') }}"
      KONG_HOSTNAME: "{{ lookup('env', 'KONG_HOSTNAME') }}"
      LB_PUBLIC_IP: "{{ lookup('env', 'LB_PUBLIC_IP') }}"
```

Requirement
----------------

* [extenral-dns](https://github.com/kubernetes-sigs/external-dns)

Author Information
------------------

- [César vergara](mailto:cvergarae@smu.cl)

