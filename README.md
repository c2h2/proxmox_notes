# proxmox_notes

## proxmox host rename
rename a proxmox host, use root.
```
vim /etc/hostname #change oldname to new name
vim /etc/hosts #change oldname to new name
hostnamectl set-hostname new-hostname

#if you are using a proxmox cluster
vim /etc/pve/corosync.conf #update new hostname

systemctl restart corosync
systemctl restart pve-cluster

reboot
```

## zfs deletion




