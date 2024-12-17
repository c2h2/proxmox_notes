# proxmox_notes

## proxmox host rename
rename a proxmox host, use root.
```
export old-hostname=asdf 
epxort new-hostname=asdfnew

vim /etc/hostname #change oldname to new name
vim /etc/hosts #change oldname to new name
hostnamectl set-hostname new-hostname
vim /etc/pve/jobs.cfg  #change oldname to new name
mv /etc/pve/lxc/${old-hostname}/lxc/* /etc/pve/${new-hostname}/lxc/
mv /etc/pve/lxc/${old-hostname}/qemu-server/* /etc/pve/${new-hostname}/qemu-server/

#if you are using a proxmox cluster
vim /etc/pve/corosync.conf #update new hostname

systemctl restart corosync
systemctl restart pve-cluster

reboot
```

## zfs deletion




