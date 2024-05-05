
### Snap in rocky linux

```
dnf check-update -y
dnf install -y dnf-utils epel-release snapd
```


https://www.youtube.com/watch?v=JynoYSE-Lko&list=PL58_tNpnaEHhAKwuBQ-SmSQNMf-NHq5VD&index=45

```
snap install microstack --beta
snap list microstack
microstack init --auto --control
microstack.openstack flavor list`
+----+-----------+-------+------+-----------+-------+-----------+
| ID | Name      |   RAM | Disk | Ephemeral | VCPUs | Is Public |
+----+-----------+-------+------+-----------+-------+-----------+
| 1  | m1.tiny   |   512 |    1 |         0 |     1 | True      |
| 2  | m1.small  |  2048 |   20 |         0 |     1 | True      |
| 3  | m1.medium |  4096 |   20 |         0 |     2 | True      |
| 4  | m1.large  |  8192 |   20 |         0 |     4 | True      |
| 5  | m1.xlarge | 16384 |   20 |         0 |     8 | True      |
+----+-----------+-------+------+-----------+-------+-----------+

microstack launch cirros -n virtu
```

Creating local "microstack" ssh key at /home/root/snap/microstack/common/.ssh/id_microstack
Launching server ...
Allocating floating ip ...
Server virtu launched! (status is BUILD)

Access it with 
`
ssh -i /home/root/snap/microstack/common/.ssh/id_microstack cirros@10.20.20.91
`
You can also visit the OpenStack dashboard at https://10.20.20.1:443


```
iptables -t nat -A PREROUTING -p tcp -d 192.168.1.42 --dport 443 -j DNAT --to-destination 10.20.20.1:443`
snap get microstack config.credentials.keystone-password
YXYeoDyNgc2mjJFyybVIwqUefGv6oaa9
```

https://192.168.1.42/auth/login/?next=/

User: admin
YXYeoDyNgc2mjJFyybVIwqUefGv6oaa9












