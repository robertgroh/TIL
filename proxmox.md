# Upload ISO Image
Drop off any iso image under `/var/lib/vz/template/iso/`.

# Annotated Directory Tree
```
# tree /var/lib/vz
/var/lib/vz
├── dump
├── images
├── private
├── root
└── template
    ├── cache
    ├── iso // store ISO image here
    └── qemu
```

# Partitioning
Promox use a interesting default partitioning:

```
# lsblk
NAME                         MAJ:MIN RM   SIZE RO TYPE MOUNTPOINT
sdd                            8:48   0 232.9G  0 disk 
|-sdd1                         8:49   0     1M  0 part 
|-sdd2                         8:50   0   256M  0 part /boot/efi
`-sdd3                         8:51   0 232.6G  0 part 
  |-pve-root                 251:0    0    58G  0 lvm  /
  |-pve-swap                 251:1    0     8G  0 lvm  [SWAP]
  |-pve-data_tmeta           251:2    0    76M  0 lvm  
  | `-pve-data-tpool         251:4    0 150.7G  0 lvm  
  |   |-pve-data             251:5    0 150.7G  0 lvm  
  |   |-pve-vm--100--disk--1 251:6    0    32G  0 lvm  
  |   `-pve-vm--101--disk--1 251:7    0    32G  0 lvm  
  `-pve-data_tdata           251:3    0 150.7G  0 lvm  
    `-pve-data-tpool         251:4    0 150.7G  0 lvm  
      |-pve-data             251:5    0 150.7G  0 lvm  
      |-pve-vm--100--disk--1 251:6    0    32G  0 lvm  
      `-pve-vm--101--disk--1 251:7    0    32G  0 lvm  
```

```
# vgs
  VG   #PV #LV #SN Attr   VSize   VFree 
  pve    1   5   0 wz--n- 232.63g 15.85g
```

```
# lvs
  LV            VG   Attr       LSize   Pool Origin Data%  Meta%  Move Log Cpy%Sync Convert
  data          pve  twi-aotz-- 150.64g             0.00   0.45                            
  root          pve  -wi-ao----  58.00g                                                    
  swap          pve  -wi-ao----   8.00g                                                    
  vm-100-disk-1 pve  Vwi-a-tz--  32.00g data        0.00                                   
  vm-101-disk-1 pve  Vwi-a-tz--  32.00g data        0.00     
```
