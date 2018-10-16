For better test conditions I changed the max memory per YARN container to 2GB, and the total memory for YARN to 8GB.

Best time:

```
mapper containers: 4
reducer containers: 1
container memory: 1024
mapper JVM heap : 819
reducer JVM heap : 819

real    0m47.115s
user    0m6.342s
sys     0m0.491s

real    1m46.538s
user    0m7.810s
sys     0m0.507s
```

Worst time:

```
mapper containers: 1
reducer containers: 8
container memory: 1536
mapper JVM heap : 1228
reducer JVM heap : 1228

real    1m11.101s
user    0m6.489s
sys     0m0.470s

real    7m35.264s
user    0m9.162s
sys     0m0.661s
```

