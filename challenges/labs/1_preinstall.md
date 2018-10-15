# 1 Swappiness

```
[centos@ip-172-31-38-172 ~]$ cat /proc/sys/vm/swappiness
60
[centos@ip-172-31-38-172 ~]$ sudo sysctl -w vm.swappiness=1
vm.swappiness = 1
[centos@ip-172-31-38-172 ~]$ cat /proc/sys/vm/swappiness
1
[centos@ip-172-31-38-172 ~]$
```

# 2 Mount Attributes 

```
[root@ip-172-31-38-172 ~]# mount
/dev/xvda1 on / type ext4 (rw)
proc on /proc type proc (rw)
sysfs on /sys type sysfs (rw)
devpts on /dev/pts type devpts (rw,gid=5,mode=620)
tmpfs on /dev/shm type tmpfs (rw,rootcontext="system_u:object_r:tmpfs_t:s0")
none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw)
[root@ip-172-31-38-172 ~]#

```

```
[root@ip-172-31-38-172 ~]# cat /etc/fstab

#
# /etc/fstab
# Created by anaconda on Tue Jun  5 13:56:10 2018
#
# Accessible filesystems, by reference, are maintained under '/dev/disk'
# See man pages fstab(5), findfs(8), mount(8) and/or blkid(8) for more info
#
UUID=c64c61c1-9e9b-4f2e-912d-d81ce4c3b716 /                       ext4    defaults        1 1
tmpfs                   /dev/shm                tmpfs   defaults        0 0
devpts                  /dev/pts                devpts  gid=5,mode=620  0 0
sysfs                   /sys                    sysfs   defaults        0 0
proc                    /proc                   proc    defaults        0 0
[root@ip-172-31-38-172 ~]#

```

# 3 Reserve space

```
[root@ip-172-31-38-172 ~]# lsblk
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  30G  0 disk
└─xvda1 202:1    0  30G  0 part /
[root@ip-172-31-38-172 ~]#

```

```
[root@ip-172-31-38-172 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       30G 1006M   27G   4% /
tmpfs           7.8G     0  7.8G   0% /dev/shm
[root@ip-172-31-38-172 ~]#

```

# 4 Transparent Hugepage Support

```
[root@ip-172-31-38-172 ~]# cat /sys/kernel/mm/redhat_transparent_hugepage/defrag
[always] madvise never
[root@ip-172-31-38-172 ~]# cat /sys/kernel/mm/redhat_transparent_hugepage/enabled
[always] madvise never
[root@ip-172-31-38-172 ~]# echo never > /sys/kernel/mm/redhat_transparent_hugepage/defrag
[root@ip-172-31-38-172 ~]# echo never > /sys/kernel/mm/redhat_transparent_hugepage/enabled
[root@ip-172-31-38-172 ~]# cat /sys/kernel/mm/redhat_transparent_hugepage/defrag
always madvise [never]
[root@ip-172-31-38-172 ~]# cat /sys/kernel/mm/redhat_transparent_hugepage/enabled
always madvise [never]
[root@ip-172-31-38-172 ~]# chmod +x /etc/rc.d/rc.local
[root@ip-172-31-38-172 ~]# vi /etc/rc.d/rc.local
[root@ip-172-31-38-172 ~]# cat /etc/rc.d/rc.local
#!/bin/sh
#
# This script will be executed *after* all the other init scripts.
# You can put your own initialization stuff in here if you don't
# want to do the full Sys V style init stuff.

touch /var/lock/subsys/local

# set a random pass on first boot
if [ -f /root/firstrun ]; then
  dd if=/dev/urandom count=50|md5sum|passwd --stdin root
  passwd -l root
  rm /root/firstrun
fi

if [ ! -d /root/.ssh ]; then
  mkdir -m 0700 -p /root/.ssh
  restorecon /root/.ssh
fi

echo never > /sys/kernel/mm/transparent_hugepage/enabled
echo never > /sys/kernel/mm/transparent_hugepage/defrag
[root@ip-172-31-38-172 ~]#
```

# 5 Network Interfaces

```
[root@ip-172-31-38-172 ~]# ifconfig
eth0      Link encap:Ethernet  HWaddr 06:73:AE:33:16:82
          inet addr:172.31.38.172  Bcast:172.31.47.255  Mask:255.255.240.0
          inet6 addr: fe80::473:aeff:fe33:1682/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:9001  Metric:1
          RX packets:1040 errors:0 dropped:0 overruns:0 frame:0
          TX packets:687 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000
          RX bytes:99636 (97.3 KiB)  TX bytes:91035 (88.9 KiB)

lo        Link encap:Local Loopback
          inet addr:127.0.0.1  Mask:255.0.0.0
          inet6 addr: ::1/128 Scope:Host
          UP LOOPBACK RUNNING  MTU:65536  Metric:1
          RX packets:0 errors:0 dropped:0 overruns:0 frame:0
          TX packets:0 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          RX bytes:0 (0.0 b)  TX bytes:0 (0.0 b)

[root@ip-172-31-38-172 ~]#
```

# 6 Forward and Reverse Host Lookups 

Public DNS name:

```
[root@ip-172-31-38-172 ~]# nslookup cloudera.com
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   cloudera.com
Address: 52.52.16.117
Name:   cloudera.com
Address: 52.52.222.237

[root@ip-172-31-38-172 ~]# nslookup 52.52.16.117
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
117.16.52.52.in-addr.arpa       name = ec2-52-52-16-117.us-west-1.compute.amazonaws.com.

Authoritative answers can be found from:

[root@ip-172-31-38-172 ~]#

```

Private DNS name:

```
[root@ip-172-31-38-172 ~]# nslookup ip-172-31-38-172.eu-central-1.compute.internal
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ip-172-31-38-172.eu-central-1.compute.internal
Address: 172.31.38.172

[root@ip-172-31-38-172 ~]# nslookup 172.31.38.172
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
172.38.31.172.in-addr.arpa      name = ip-172-31-38-172.eu-central-1.compute.internal.

Authoritative answers can be found from:

[root@ip-172-31-38-172 ~]# 
```

# 7 nscd

```
[root@ip-172-31-38-172 ~]# nscd -g
nscd configuration:

              0  server debug level
         1m 41s  server runtime
              5  current number of threads
             32  maximum number of threads
              0  number of times clients had to wait
             no  paranoia mode enabled
           3600  restart internal
              5  reload count

passwd cache:

            yes  cache is enabled
            yes  cache is persistent
            yes  cache is shared
            211  suggested size
         216064  total data pool size
              0  used data pool size
            600  seconds time to live for positive entries
             20  seconds time to live for negative entries
              0  cache hits on positive entries
              0  cache hits on negative entries
              0  cache misses on positive entries
              0  cache misses on negative entries
              0% cache hit rate
              0  current number of cached values
              0  maximum number of cached values
              0  maximum chain length searched
              0  number of delays on rdlock
              0  number of delays on wrlock
              0  memory allocations failed
            yes  check /etc/passwd for changes

group cache:

            yes  cache is enabled
            yes  cache is persistent
            yes  cache is shared
            211  suggested size
         216064  total data pool size
              0  used data pool size
           3600  seconds time to live for positive entries
             60  seconds time to live for negative entries
              0  cache hits on positive entries
              0  cache hits on negative entries
              0  cache misses on positive entries
              0  cache misses on negative entries
              0% cache hit rate
              0  current number of cached values
              0  maximum number of cached values
              0  maximum chain length searched
              0  number of delays on rdlock
              0  number of delays on wrlock
              0  memory allocations failed
            yes  check /etc/group for changes

hosts cache:

            yes  cache is enabled
            yes  cache is persistent
            yes  cache is shared
            211  suggested size
         216064  total data pool size
              0  used data pool size
           3600  seconds time to live for positive entries
             20  seconds time to live for negative entries
              0  cache hits on positive entries
              0  cache hits on negative entries
              0  cache misses on positive entries
              0  cache misses on negative entries
              0% cache hit rate
              0  current number of cached values
              0  maximum number of cached values
              0  maximum chain length searched
              0  number of delays on rdlock
              0  number of delays on wrlock
              0  memory allocations failed
            yes  check /etc/hosts for changes

services cache:

            yes  cache is enabled
            yes  cache is persistent
            yes  cache is shared
            211  suggested size
         216064  total data pool size
              0  used data pool size
          28800  seconds time to live for positive entries
             20  seconds time to live for negative entries
              0  cache hits on positive entries
              0  cache hits on negative entries
              0  cache misses on positive entries
              0  cache misses on negative entries
              0% cache hit rate
              0  current number of cached values
              0  maximum number of cached values
              0  maximum chain length searched
              0  number of delays on rdlock
              0  number of delays on wrlock
              0  memory allocations failed
            yes  check /etc/services for changes

netgroup cache:

            yes  cache is enabled
            yes  cache is persistent
            yes  cache is shared
            211  suggested size
         216064  total data pool size
              0  used data pool size
          28800  seconds time to live for positive entries
             20  seconds time to live for negative entries
              0  cache hits on positive entries
              0  cache hits on negative entries
              0  cache misses on positive entries
              0  cache misses on negative entries
              0% cache hit rate
              0  current number of cached values
              0  maximum number of cached values
              0  maximum chain length searched
              0  number of delays on rdlock
              0  number of delays on wrlock
              0  memory allocations failed
            yes  check /etc/netgroup for changes

SELinux AVC Statistics:

              2  entry lookups
              1  entry hits
              1  entry misses
              0  entry discards
              1  CAV lookups
              0  CAV hits
              0  CAV probes
              1  CAV misses
[root@ip-172-31-38-172 ~]# time nslookup ip-172-31-38-172.eu-central-1.compute.internal
Server:         172.31.0.2
Address:        172.31.0.2#53

Non-authoritative answer:
Name:   ip-172-31-38-172.eu-central-1.compute.internal
Address: 172.31.38.172


real    0m0.006s
user    0m0.002s
sys     0m0.002s
[root@ip-172-31-38-172 ~]#
```

# 8 ntpd (actually chrony, because it's AWS)

```
[root@ip-172-31-38-172 ~]# chronyc sources -v
210 Number of sources = 1

  .-- Source mode  '^' = server, '=' = peer, '#' = local clock.
 / .- Source state '*' = current synced, '+' = combined , '-' = not combined,
| /   '?' = unreachable, 'x' = time may be in error, '~' = time too variable.
||                                                 .- xxxx [ yyyy ] +/- zzzz
||      Reachability register (octal) -.           |  xxxx = adjusted offset,
||      Log2(Polling interval) --.      |          |  yyyy = measured offset,
||                                \     |          |  zzzz = estimated error.
||                                 |    |           \
MS Name/IP address         Stratum Poll Reach LastRx Last sample
===============================================================================
^* 169.254.169.123               3   6   177     1   -230ns[ -147us] +/-  641us
[root@ip-172-31-38-172 ~]# chronyc tracking
Reference ID    : 169.254.169.123 (169.254.169.123)
Stratum         : 4
Ref time (UTC)  : Mon Oct 15 13:00:16 2018
System time     : 0.000000067 seconds fast of NTP time
Last offset     : -0.000146770 seconds
RMS offset      : 0.000813593 seconds
Frequency       : 25.170 ppm fast
Residual freq   : -1.542 ppm
Skew            : 1.567 ppm
Root delay      : 0.000547 seconds
Root dispersion : 0.000349 seconds
Update interval : 65.0 seconds
Leap status     : Normal
[root@ip-172-31-38-172 ~]#

```