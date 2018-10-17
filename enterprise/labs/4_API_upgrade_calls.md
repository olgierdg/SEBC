# Report the latest available version of the API

```bash
bash-4.4$ curl -u olgierdg:cloudera 'http://ec2-3-120-225-216.eu-central-1.compute.amazonaws.com:7180/api/version'
v14
```

# Report the CM version

```bash
bash-4.4$ curl -u olgierdg:cloudera 'http://ec2-3-120-225-216.eu-central-1.compute.amazonaws.com:7180/api/v14/cm/version'
{
  "version" : "5.9.3",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170627-1506",
  "gitHash" : "23506bb4e114dd460bdac64c57a672e6be631907",
  "snapshot" : false
}
```

# List all CM users

```bash
bash-4.4$ curl -u olgierdg:cloudera 'http://ec2-3-120-225-216.eu-central-1.compute.amazonaws.com:7180/api/v14/users'
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  }, {
    "name" : "olgierdg",
    "roles" : [ "ROLE_ADMIN" ]
  } ]
}
```

# Report the database server in use by CM

```bash
bash-4.4$ curl -s -u olgierdg:cloudera 'http://ec2-3-120-225-216.eu-central-1.compute.amazonaws.com:7180/api/v14/cm/deployment' | grep -A 1 '"name" : "database_host"'
          "name" : "database_host",
          "value" : "ip-172-31-38-172.eu-central-1.compute.internal",
```

```bash
bash-4.4$ curl -s -u olgierdg:cloudera 'http://ec2-3-120-225-216.eu-central-1.compute.amazonaws.com:7180/api/v14/cm/deployment' | grep -A 1 '"name" : "database_type"'
          "name" : "database_type",
          "value" : "mysql",
```

```bash
bash-4.4$ curl -s -u olgierdg:cloudera 'http://ec2-3-120-225-216.eu-central-1.compute.amazonaws.com:7180/api/v14/cm/scmDbInfo'
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
```