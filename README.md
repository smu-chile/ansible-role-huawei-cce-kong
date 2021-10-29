Huawei CCE Setup
=========

Role to setup a bastion to connect with a cce cluster



Role Variables
--------------

```
      LB_ID: id de Balanceador, se obtiene de terraform
      LB_VIP_SUBNET_ID: id de subnet de balanceador, se obtiene de terraform
      LB_PUBLIC_IP: IP publica de balanceador
      KONG_HOSTNAME: hostname donde se alojara Traefik, esto crea un registro A, apuntando a la Ip del balanceador:
```

Example Playbook
----------------


```
- hosts: all
  become: no
  remote_user: "root"

# Uncomment "aws-eks-setup" role only if you are upgrading the cluster
  roles:
    - role: ansible-role-huawei-cce-kong
      LB_ID: "{{ lookup('env', 'LB_ID') }}"
      LB_VIP_SUBNET_ID: "{{ lookup('env', 'LB_SUBNET_ID') }}"
      KONG_HOSTNAME: "{{ lookup('env', 'TRAEFIK_HOSTNAME') }}"
      LB_PUBLIC_IP: "{{ lookup('env', 'LB_PUBLIC_IP') }}"
```

License
-------

BSD

Author Information
------------------

- [César vergara](mailto:cvergarae@smu.cl)

