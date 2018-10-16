```json
{
  "timestamp" : "2018-10-16T14:57:49.743Z",
  "clusters" : [ {
    "name" : "cluster",
    "displayName" : "olgierdg",
    "version" : "CDH5",
    "fullVersion" : "5.8.5",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-3f67300a3c3d7ca25b7f23aa86804736",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-07fa801414a73a624"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "16g16js1uxvv4fyj9bag4zr72"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "zookeeper-SERVER-BASE"
        }
      }, {
        "name" : "zookeeper-SERVER-4afbab7f60149c98835d7c6e69050d25",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-0240a85f2cb554c34"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "ab5xxmh1y1rgmta0e96103qhe"
          }, {
            "name" : "serverId",
            "value" : "3"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "zookeeper-SERVER-BASE"
        }
      }, {
        "name" : "zookeeper-SERVER-babfd98719a76db3a75fe5f3a09d6136",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "i-03dd27c1a8f6c0507"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b3bear5ae2hczg164saidt4tc"
          }, {
            "name" : "serverId",
            "value" : "2"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "zookeeper-SERVER-BASE"
        }
      } ],
      "displayName" : "ZooKeeper",
      "roleConfigGroups" : [ {
        "name" : "zookeeper-SERVER-BASE",
        "displayName" : "Server Default Group",
        "roleType" : "SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "zookeeper"
        },
        "config" : {
          "items" : [ ]
        }
      } ]
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-4afbab7f60149c98835d7c6e69050d25",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "i-0240a85f2cb554c34"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "661cu590jhhgc2pde4f9seo8e"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "oozie-OOZIE_SERVER-BASE"
        }
      } ],
      "displayName" : "Oozie",
      "roleConfigGroups" : [ {
        "name" : "oozie-OOZIE_SERVER-BASE",
        "displayName" : "Oozie Server Default Group",
        "roleType" : "OOZIE_SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "oozie"
        },
        "config" : {
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-38-172.eu-central-1.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie_password"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          } ]
        }
      } ]
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-38-172.eu-central-1.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "hue_password"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-HTTPFS-55bdac502ea0be18ece0658d7037c9bf"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-55bdac502ea0be18ece0658d7037c9bf",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "i-07620be5c9f137bbd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "apfod2e6teu1ppx4e3mifinzy"
          }, {
            "name" : "secret_key",
            "value" : "cDKdsYza9EhGf6IUEcb85p8aWtK0oC"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hue-HUE_SERVER-BASE"
        }
      } ],
      "displayName" : "Hue",
      "roleConfigGroups" : [ {
        "name" : "hue-HUE_LOAD_BALANCER-BASE",
        "displayName" : "Load Balancer Default Group",
        "roleType" : "HUE_LOAD_BALANCER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hue-HUE_SERVER-BASE",
        "displayName" : "Hue Server Default Group",
        "roleType" : "HUE_SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hue-KT_RENEWER-BASE",
        "displayName" : "Kerberos Ticket Renewer Default Group",
        "roleType" : "KT_RENEWER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ ]
        }
      } ]
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "QRDcJ1sisXtnTJkccYzB5A3vWCkkZM"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "OqZmWCGLOHihuhP1E9WsA5S9LjcGLW"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "7QUsLZlYdZKRp6EJaQsj6z1VCgOD8m"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-55bdac502ea0be18ece0658d7037c9bf",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "i-07620be5c9f137bbd"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-BALANCER-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-3f67300a3c3d7ca25b7f23aa86804736",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-07fa801414a73a624"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1rrp5qggq8mz9la68cj5qtq92"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-4afbab7f60149c98835d7c6e69050d25",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-0240a85f2cb554c34"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6br0m2or4eyzk78wawo2wcs5w"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-55bdac502ea0be18ece0658d7037c9bf",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-07620be5c9f137bbd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1l8eewu6qdjjk3o1du0yi3d5p"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-1"
        }
      }, {
        "name" : "hdfs-DATANODE-babfd98719a76db3a75fe5f3a09d6136",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "i-03dd27c1a8f6c0507"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "f0krums132el35yry6jzi3wti"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-3f67300a3c3d7ca25b7f23aa86804736",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-07fa801414a73a624"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "609kojqgb9j7g80ra4e2kvkzp"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-FAILOVERCONTROLLER-BASE"
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-babfd98719a76db3a75fe5f3a09d6136",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "i-03dd27c1a8f6c0507"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "59780fke1huclumzhbyi3svtd"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-FAILOVERCONTROLLER-BASE"
        }
      }, {
        "name" : "hdfs-HTTPFS-55bdac502ea0be18ece0658d7037c9bf",
        "type" : "HTTPFS",
        "hostRef" : {
          "hostId" : "i-07620be5c9f137bbd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "uwurd0qomwwih4erfpa4ncub"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-HTTPFS-BASE"
        }
      }, {
        "name" : "hdfs-JOURNALNODE-3f67300a3c3d7ca25b7f23aa86804736",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-07fa801414a73a624"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "akde7ptw10s48cctgxnk6cw5o"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-JOURNALNODE-BASE"
        }
      }, {
        "name" : "hdfs-JOURNALNODE-4afbab7f60149c98835d7c6e69050d25",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-0240a85f2cb554c34"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "68xanqqmm899v0wl9ljlhznyo"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-JOURNALNODE-BASE"
        }
      }, {
        "name" : "hdfs-JOURNALNODE-55bdac502ea0be18ece0658d7037c9bf",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "i-07620be5c9f137bbd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7s6tp3f3gvrghdjluto271fcf"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-JOURNALNODE-BASE"
        }
      }, {
        "name" : "hdfs-NAMENODE-3f67300a3c3d7ca25b7f23aa86804736",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-07fa801414a73a624"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "48"
          }, {
            "name" : "role_jceks_password",
            "value" : "9enln8y0y71ykht5xqgcrp125"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-NAMENODE-BASE"
        }
      }, {
        "name" : "hdfs-NAMENODE-babfd98719a76db3a75fe5f3a09d6136",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "i-03dd27c1a8f6c0507"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "63"
          }, {
            "name" : "role_jceks_password",
            "value" : "crz42tnt453lsayomqlsw39qv"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-NAMENODE-BASE"
        }
      } ],
      "displayName" : "HDFS",
      "roleConfigGroups" : [ {
        "name" : "hdfs-BALANCER-BASE",
        "displayName" : "Balancer Default Group",
        "roleType" : "BALANCER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-DATANODE-1",
        "displayName" : "DataNode Group 1",
        "roleType" : "DATANODE",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "3156951040"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-BASE",
        "displayName" : "DataNode Default Group",
        "roleType" : "DATANODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "3156951040"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-BASE",
        "displayName" : "Failover Controller Default Group",
        "roleType" : "FAILOVERCONTROLLER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-BASE",
        "displayName" : "HttpFS Default Group",
        "roleType" : "HTTPFS",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-BASE",
        "displayName" : "JournalNode Default Group",
        "roleType" : "JOURNALNODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/dfs/jn"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-BASE",
        "displayName" : "NameNode Default Group",
        "roleType" : "NAMENODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "1997537280"
          }, {
            "name" : "role_config_suppression_namenode_java_heapsize_minimum_validator",
            "value" : "true"
          } ]
        }
      }, {
        "name" : "hdfs-NFSGATEWAY-BASE",
        "displayName" : "NFS Gateway Default Group",
        "roleType" : "NFSGATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-SECONDARYNAMENODE-BASE",
        "displayName" : "SecondaryNameNode Default Group",
        "roleType" : "SECONDARYNAMENODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "1997537280"
          } ]
        }
      } ],
      "replicationSchedules" : [ {
        "id" : 4,
        "startTime" : "2018-10-16T08:58:00.000Z",
        "interval" : 0,
        "intervalUnit" : "MINUTE",
        "paused" : false,
        "nextRun" : null,
        "alertOnStart" : false,
        "alertOnSuccess" : false,
        "alertOnFail" : false,
        "alertOnAbort" : false,
        "hdfsArguments" : {
          "sourceService" : {
            "peerName" : "nawojka",
            "clusterName" : "cluster",
            "serviceName" : "hdfs"
          },
          "sourcePath" : "/nawojka",
          "destinationPath" : "/tmp/nawojka3",
          "mapreduceServiceName" : "yarn",
          "dryRun" : false,
          "abortOnError" : false,
          "removeMissingFiles" : false,
          "preserveReplicationCount" : true,
          "preserveBlockSize" : true,
          "preservePermissions" : true,
          "skipChecksumChecks" : false,
          "skipTrash" : false,
          "replicationStrategy" : "DYNAMIC",
          "preserveXAttrs" : false,
          "exclusionFilters" : [ ]
        },
        "active" : false
      } ],
      "snapshotPolicies" : [ ]
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "true"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "true"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "true"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "FzKDROsKjTC8YdeHGWI8DsRftxoVu2"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-babfd98719a76db3a75fe5f3a09d6136",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "i-03dd27c1a8f6c0507"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "7wat0z4tvu0kibkb9qg96wu8o"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-JOBHISTORY-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-3f67300a3c3d7ca25b7f23aa86804736",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-07fa801414a73a624"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "54rv31ywly179ek8h7c37xh2r"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-4afbab7f60149c98835d7c6e69050d25",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-0240a85f2cb554c34"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "dqa030519o3v49tnka5v87wrg"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-55bdac502ea0be18ece0658d7037c9bf",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-07620be5c9f137bbd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "df91mra9smowui9d8xj03epaj"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-1"
        }
      }, {
        "name" : "yarn-NODEMANAGER-babfd98719a76db3a75fe5f3a09d6136",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "i-03dd27c1a8f6c0507"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "8k5at15ej7wkfcgrmg8ycy5jc"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-BASE"
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-3f67300a3c3d7ca25b7f23aa86804736",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "i-07fa801414a73a624"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "55"
          }, {
            "name" : "role_jceks_password",
            "value" : "f3al4afevavuzbr5av29ulk3l"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-RESOURCEMANAGER-BASE"
        }
      } ],
      "displayName" : "YARN (MR2 Included)",
      "roleConfigGroups" : [ {
        "name" : "yarn-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "8"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "yarn-JOBHISTORY-BASE",
        "displayName" : "JobHistory Server Default Group",
        "roleType" : "JOBHISTORY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-1",
        "displayName" : "NodeManager Group 1",
        "roleType" : "NODEMANAGER",
        "base" : false,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "4"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "2048"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-BASE",
        "displayName" : "NodeManager Default Group",
        "roleType" : "NODEMANAGER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1800"
          }, {
            "name" : "rm_io_weight",
            "value" : "900"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "2048"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-BASE",
        "displayName" : "ResourceManager Default Group",
        "roleType" : "RESOURCEMANAGER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "2048"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        }
      } ]
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-38-172.eu-central-1.compute.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_password"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-07ac5b48fd63cdb0bc64e1ebdcd47b0e",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-00eac04f16cf528ee"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-3f67300a3c3d7ca25b7f23aa86804736",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-07fa801414a73a624"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-4afbab7f60149c98835d7c6e69050d25",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-0240a85f2cb554c34"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-55bdac502ea0be18ece0658d7037c9bf",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-07620be5c9f137bbd"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-GATEWAY-babfd98719a76db3a75fe5f3a09d6136",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "i-03dd27c1a8f6c0507"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-HIVEMETASTORE-4afbab7f60149c98835d7c6e69050d25",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "i-0240a85f2cb554c34"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1dlwnz1hd3tuzmkxb4dvyvaeu"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-HIVEMETASTORE-BASE"
        }
      }, {
        "name" : "hive-HIVESERVER2-55bdac502ea0be18ece0658d7037c9bf",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "i-07620be5c9f137bbd"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "csuzmzg7lrrunsxv323cskjsi"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-HIVESERVER2-BASE"
        }
      } ],
      "displayName" : "Hive",
      "roleConfigGroups" : [ {
        "name" : "hive-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-BASE",
        "displayName" : "Hive Metastore Server Default Group",
        "roleType" : "HIVEMETASTORE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "1997537280"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-BASE",
        "displayName" : "HiveServer2 Default Group",
        "roleType" : "HIVESERVER2",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "2286944256"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "2207724339"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "371"
          } ]
        }
      }, {
        "name" : "hive-WEBHCAT-BASE",
        "displayName" : "WebHCat Server Default Group",
        "roleType" : "WEBHCAT",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ ]
        }
      } ],
      "replicationSchedules" : [ ]
    } ],
    "parcels" : [ {
      "product" : "CDH",
      "version" : "5.8.5-1.cdh5.8.5.p0.5",
      "stage" : "DISTRIBUTED",
      "clusterRef" : {
        "clusterName" : "cluster"
      }
    }, {
      "product" : "CDH",
      "version" : "5.8.5-1.cdh5.8.5.p0.5",
      "stage" : "ACTIVATED",
      "clusterRef" : {
        "clusterName" : "cluster"
      }
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "i-07fa801414a73a624",
    "ipAddress" : "172.31.35.238",
    "hostname" : "ip-172-31-35-238.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-00eac04f16cf528ee",
    "ipAddress" : "172.31.38.172",
    "hostname" : "ip-172-31-38-172.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-03dd27c1a8f6c0507",
    "ipAddress" : "172.31.39.96",
    "hostname" : "ip-172-31-39-96.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-07620be5c9f137bbd",
    "ipAddress" : "172.31.41.146",
    "hostname" : "ip-172-31-41-146.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "i-0240a85f2cb554c34",
    "ipAddress" : "172.31.46.123",
    "hostname" : "ip-172-31-46-123.eu-central-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__0295bcbe-8f25-4d03-9c98-b41813eca418",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "062dd89a73997d0a48bf2090b968b74c7f80b82dd5977d7217df79ece3e01eff",
    "pwSalt" : -909545924939963307,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-ACTIVITYMONITOR-07ac5b48fd63cdb0bc64e1ebdcd47b0e",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "9a85f842bd36a2075cd6c95569db0c164fb4f94f055dff2cad2e024a1717ab57",
    "pwSalt" : -2208699128111788058,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-07ac5b48fd63cdb0bc64e1ebdcd47b0e",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "2fe3d81e11b8a7821d37cdb1727e53975fd6d137ab00f8ee198181819dad8053",
    "pwSalt" : 9220649056643072717,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-07ac5b48fd63cdb0bc64e1ebdcd47b0e",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "afa94072c3ce61b6b7945935e6dab0ef9cdc234f54559810902bdfb529619174",
    "pwSalt" : 2251814055878025541,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-07ac5b48fd63cdb0bc64e1ebdcd47b0e",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "6746ee0382aba6fa9139cc11feae132d48a0f46f39e7f755d63305ab87a1db18",
    "pwSalt" : -5961448613162353756,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-07ac5b48fd63cdb0bc64e1ebdcd47b0e",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "76aa349b9dab3d087a509b01e8077e739572d7ea361bef7cc967673a701c74cb",
    "pwSalt" : 854865915407007866,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "e939938aa0f7a7a537749cbfa98aca28253434c4de756576203172e21962c363",
    "pwSalt" : -2049500686692098805,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "e038a33d60e3c8eef798f835fcc08e0c90b721cbfcfb82b220ac86153cf52507",
    "pwSalt" : -2586656503488638211,
    "pwLogin" : true
  }, {
    "name" : "olgierdg",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "86407bd6a4fc6535ac42605e14eebe40edab1f9dffde18b71b98031f9cc06dd1",
    "pwSalt" : 1496968327785087902,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.8.3",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20161019-1014",
    "gitHash" : "518f0d6d44abc87bc392646e4369a20c8192b7cf",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ACTIVITYMONITOR-07ac5b48fd63cdb0bc64e1ebdcd47b0e",
      "type" : "ACTIVITYMONITOR",
      "hostRef" : {
        "hostId" : "i-00eac04f16cf528ee"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "ejd53hi9ogvjlfbkxfbbjj5th"
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-ACTIVITYMONITOR-BASE"
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-07ac5b48fd63cdb0bc64e1ebdcd47b0e",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "i-00eac04f16cf528ee"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "1fum42xlm0e3hyaqt06toiryn"
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-ALERTPUBLISHER-BASE"
      }
    }, {
      "name" : "mgmt-EVENTSERVER-07ac5b48fd63cdb0bc64e1ebdcd47b0e",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "i-00eac04f16cf528ee"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "3e56qzl3j1x3e2fd63nf9whzo"
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-EVENTSERVER-BASE"
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-07ac5b48fd63cdb0bc64e1ebdcd47b0e",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "i-00eac04f16cf528ee"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "85aobeg2h1gkyexxndxbkeyag"
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-HOSTMONITOR-BASE"
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-07ac5b48fd63cdb0bc64e1ebdcd47b0e",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "i-00eac04f16cf528ee"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "dkd5ii7sg3a178k362k69nb13"
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-REPORTSMANAGER-BASE"
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-07ac5b48fd63cdb0bc64e1ebdcd47b0e",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "i-00eac04f16cf528ee"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "b2k3i9b1hw4bb140268gy770x"
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-SERVICEMONITOR-BASE"
      }
    } ],
    "displayName" : "Cloudera Management Service",
    "roleConfigGroups" : [ {
      "name" : "mgmt-ACTIVITYMONITOR-BASE",
      "displayName" : "Activity Monitor Default Group",
      "roleType" : "ACTIVITYMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "firehose_database_host",
          "value" : "ip-172-31-38-172.eu-central-1.compute.internal"
        }, {
          "name" : "firehose_database_name",
          "value" : "amon"
        }, {
          "name" : "firehose_database_password",
          "value" : "amon_password"
        }, {
          "name" : "firehose_database_user",
          "value" : "amon"
        } ]
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-BASE",
      "displayName" : "Alert Publisher Default Group",
      "roleType" : "ALERTPUBLISHER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-BASE",
      "displayName" : "Event Server Default Group",
      "roleType" : "EVENTSERVER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-BASE",
      "displayName" : "Host Monitor Default Group",
      "roleType" : "HOSTMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      }
    }, {
      "name" : "mgmt-NAVIGATOR-BASE",
      "displayName" : "Navigator Audit Server Default Group",
      "roleType" : "NAVIGATOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-NAVIGATORMETASERVER-BASE",
      "displayName" : "Navigator Metadata Server Default Group",
      "roleType" : "NAVIGATORMETASERVER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-BASE",
      "displayName" : "Reports Manager Default Group",
      "roleType" : "REPORTSMANAGER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-38-172.eu-central-1.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman_password"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-BASE",
      "displayName" : "Service Monitor Default Group",
      "roleType" : "SERVICEMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "1610612736"
        } ]
      }
    } ]
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/27/2012 23:10"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/,http://localhost/cdh5.8.3"
    } ]
  },
  "allHostsConfig" : {
    "items" : [ {
      "name" : "rm_enabled",
      "value" : "true"
    } ]
  },
  "peers" : [ {
    "name" : "nawojka",
    "type" : "REPLICATION",
    "url" : "http://ec2-18-196-113-149.eu-central-1.compute.amazonaws.com:7180",
    "username" : "__cloudera_internal_user__2fddee72-479a-437e-8915-a5027ab74e36",
    "password" : "17da0ae9-aaf7-450c-a27e-ca8ca0d6a5510aadac76-f410-495f-a6cb-82a5749fe70e",
    "clouderaManagerCreatedUser" : true
  } ],
  "hostTemplates" : {
    "items" : [ ]
  }
}
```