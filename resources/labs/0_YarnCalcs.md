Plugged in values:

```
Worker vcores	20
Worker spindles	12
Worker RAM	128
Workload factor	2
Worker nodes	10
```

Adjustments:

According to this answer by a Cloudera employee https://community.cloudera.com/t5/Cloudera-Manager-Installation/Memory/td-p/30571 Cloudera Manager memory calculation includes 20% for the Operating System. I adjusted the formula in the Excel sheet to reflect this as `=PRODUCT(0,2;B3)` instead of `=PRODUCT(0,1;B3)`.

Workload factor affects the number of mappers and reducers. Value 1 means that max 1 map and 1 reduce task will be run per node, value 2 means max 2 map and 2 reduce tasks, etc. In case of these plugged in values, setting it to more than 2 does not make a difference, since the total number of vcores for yarn is calculated to 15 and we have 10 nodes.