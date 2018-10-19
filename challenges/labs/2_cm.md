# List the command and output of ls /etc/yum.repos.d in challenges/labs/2_cm.md

```
[root@ip-172-31-18-209 ~]# ls /etc/yum.repos.d
CentOS-Base.repo       CentOS-fasttrack.repo  CentOS-Vault.repo      epel.repo          mysql-community.repo
CentOS-Debuginfo.repo  CentOS-Media.repo      cloudera-manager.repo  epel-testing.repo  mysql-community-source.repo
```

# List the full command line in 2_cm.md

```
[root@ip-172-31-18-209 ~]# /usr/share/cmf/schema/scm_prepare_database.sh -h ip-172-31-16-185.eu-west-2.compute.internal mysql scm scm scm_password
JAVA_HOME=/usr/java/jdk1.8.0_131
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.8.0_131/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!
```