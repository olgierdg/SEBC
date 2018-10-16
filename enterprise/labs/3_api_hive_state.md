# Status

```
bash-4.4$ curl -u olgierdg:cloudera 'http://ec2-3-120-225-216.eu-central-1.compute.amazonaws.com:7180/api/v12/clusters/olgierdg/services/hive'
```

```json
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-38-172.eu-central-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-172-31-38-172.eu-central-1.compute.internal:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "GOOD_HEALTH"
}
```

# Stop

```
bash-4.4$ curl -XPOST -u olgierdg:cloudera 'http://ec2-3-120-225-216.eu-central-1.compute.amazonaws.com:7180/api/v12/clusters/olgierdg/services/hive/commands/stop'
```
```json
{
  "id" : 485,
  "name" : "Stop",
  "startTime" : "2018-10-16T15:24:42.334Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

```
bash-4.4$ curl -u olgierdg:cloudera 'http://ec2-3-120-225-216.eu-central-1.compute.amazonaws.com:7180/api/v12/clusters/olgierdg/services/hive'
```

```json
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-38-172.eu-central-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-172-31-38-172.eu-central-1.compute.internal:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STOPPED",
  "healthSummary" : "DISABLED",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "DISABLED",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "DISABLED",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "STOPPED"
}
```

# Start

```
bash-4.4$ curl -XPOST -u olgierdg:cloudera 'http://ec2-3-120-225-216.eu-central-1.compute.amazonaws.com:7180/api/v12/clusters/olgierdg/services/hive/commands/start'
```

```json
{
  "id" : 489,
  "name" : "Start",
  "startTime" : "2018-10-16T15:25:36.889Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
```

```
bash-4.4$ curl -u olgierdg:cloudera 'http://ec2-3-120-225-216.eu-central-1.compute.amazonaws.com:7180/api/v12/clusters/olgierdg/services/hive'
```

```json
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-38-172.eu-central-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-172-31-38-172.eu-central-1.compute.internal:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "GOOD_HEALTH"
}
```