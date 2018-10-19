# List the cloud provider you are using (AWS, GCE, Azure, other)

AWS

Hosts:

```
ec2-18-130-231-111.eu-west-2.compute.amazonaws.com
ec2-18-130-162-189.eu-west-2.compute.amazonaws.com
ec2-35-176-227-157.eu-west-2.compute.amazonaws.com
ec2-18-130-193-62.eu-west-2.compute.amazonaws.com
ec2-18-130-254-234.eu-west-2.compute.amazonaws.com
```

# List the Linux release you have chosen

```
ec2-18-130-231-111.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
CentOS release 6.9 (Final)

ec2-18-130-162-189.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
CentOS release 6.9 (Final)

ec2-35-176-227-157.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
CentOS release 6.9 (Final)

ec2-18-130-254-234.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
CentOS release 6.9 (Final)

ec2-18-130-193-62.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
CentOS release 6.9 (Final)
```

# Show that the disk space on each node is at least 30 GB

```
ec2-18-130-254-234.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  30G  0 disk
└─xvda1 202:1    0  30G  0 part /

ec2-35-176-227-157.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  30G  0 disk
└─xvda1 202:1    0  30G  0 part /

ec2-18-130-231-111.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  30G  0 disk
└─xvda1 202:1    0  30G  0 part /

ec2-18-130-162-189.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  30G  0 disk
└─xvda1 202:1    0  30G  0 part /

ec2-18-130-193-62.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  30G  0 disk
└─xvda1 202:1    0  30G  0 part /
```

```
ec2-35-176-227-157.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       30G 1013M   27G   4% /
tmpfs           7.8G     0  7.8G   0% /dev/shm

ec2-18-130-254-234.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       30G 1013M   27G   4% /
tmpfs           7.8G     0  7.8G   0% /dev/shm

ec2-18-130-193-62.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       30G 1013M   27G   4% /
tmpfs           7.8G     0  7.8G   0% /dev/shm

ec2-18-130-162-189.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       30G 1013M   27G   4% /
tmpfs           7.8G     0  7.8G   0% /dev/shm

ec2-18-130-231-111.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       30G 1013M   27G   4% /
tmpfs           7.8G     0  7.8G   0% /dev/shm
```

# List the command and output for yum repolist enabled

```
ec2-18-130-231-111.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: mirror.vorboss.net
 * epel: d2lzkl7pfhq30w.cloudfront.net
 * extras: mirrors.clouvider.net
 * updates: mirrors.coreix.net
repo id          repo name                                               status
base             CentOS-6 - Base                                         6,712+1
epel             Extra Packages for Enterprise Linux 6 - x86_64           12,515
extras           CentOS-6 - Extras                                         21+12
updates          CentOS-6 - Updates                                          205
repolist: 19,453

ec2-18-130-193-62.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: mirror.freethought-internet.co.uk
 * epel: d2lzkl7pfhq30w.cloudfront.net
 * extras: mirror.freethought-internet.co.uk
 * updates: mirrors.coreix.net
repo id          repo name                                               status
base             CentOS-6 - Base                                         6,712+1
epel             Extra Packages for Enterprise Linux 6 - x86_64           12,515
extras           CentOS-6 - Extras                                         21+12
updates          CentOS-6 - Updates                                          205
repolist: 19,453

ec2-18-130-162-189.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: mirror.vorboss.net
 * epel: d2lzkl7pfhq30w.cloudfront.net
 * extras: mirrors.clouvider.net
 * updates: mirrors.coreix.net
repo id          repo name                                               status
base             CentOS-6 - Base                                         6,712+1
epel             Extra Packages for Enterprise Linux 6 - x86_64           12,515
extras           CentOS-6 - Extras                                         21+12
updates          CentOS-6 - Updates                                          205
repolist: 19,453

ec2-35-176-227-157.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: mirror.freethought-internet.co.uk
 * epel: mirrors.coreix.net
 * extras: mirror.freethought-internet.co.uk
 * updates: mirrors.coreix.net
repo id          repo name                                               status
base             CentOS-6 - Base                                         6,712+1
epel             Extra Packages for Enterprise Linux 6 - x86_64           12,515
extras           CentOS-6 - Extras                                         21+12
updates          CentOS-6 - Updates                                          205
repolist: 19,453

ec2-18-130-254-234.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: mirror.vorboss.net
 * epel: d2lzkl7pfhq30w.cloudfront.net
 * extras: mirror.netweaver.uk
 * updates: mirrors.coreix.net
repo id          repo name                                               status
base             CentOS-6 - Base                                         6,712+1
epel             Extra Packages for Enterprise Linux 6 - x86_64           12,515
extras           CentOS-6 - Extras                                         21+12
updates          CentOS-6 - Updates                                          205
repolist: 19,453
```

# List the /etc/passwd entries for raffles and fullerton in your setup file

```
ec2-18-130-254-234.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
raffles:x:2000:2000::/home/raffles:/bin/bash

ec2-18-130-193-62.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
raffles:x:2000:2000::/home/raffles:/bin/bash

ec2-18-130-162-189.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
raffles:x:2000:2000::/home/raffles:/bin/bash

ec2-35-176-227-157.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
raffles:x:2000:2000::/home/raffles:/bin/bash

ec2-18-130-231-111.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
raffles:x:2000:2000::/home/raffles:/bin/bash
```

```
ec2-35-176-227-157.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
fullerton:x:3000:3000::/home/fullerton:/bin/bash

ec2-18-130-231-111.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
fullerton:x:3000:3000::/home/fullerton:/bin/bash

ec2-18-130-254-234.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
fullerton:x:3000:3000::/home/fullerton:/bin/bash

ec2-18-130-193-62.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
fullerton:x:3000:3000::/home/fullerton:/bin/bash

ec2-18-130-162-189.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
fullerton:x:3000:3000::/home/fullerton:/bin/bash
```

# List the /etc/group entries for hotels and shops in your setup file

```
ec2-18-130-162-189.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
hotels:x:3001:fullerton

ec2-18-130-193-62.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
hotels:x:3001:fullerton

ec2-18-130-231-111.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
hotels:x:3001:fullerton

ec2-35-176-227-157.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
hotels:x:3001:fullerton

ec2-18-130-254-234.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
hotels:x:3001:fullerton
```

```
ec2-18-130-254-234.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
shops:x:3002:raffles

ec2-35-176-227-157.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
shops:x:3002:raffles

ec2-18-130-162-189.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
shops:x:3002:raffles

ec2-18-130-193-62.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
shops:x:3002:raffles

ec2-18-130-231-111.eu-west-2.compute.amazonaws.com | CHANGED | rc=0 >>
shops:x:3002:raffles
```