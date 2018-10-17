# What is ubertask optimization?

Normally mappers and reducers will run by ResourceManager (RM), RM will create separate container for mapper and reducer. Uber configuration allows running mappers and reducers in the same process as the ApplicationMaster (AM).

# Where in CM is the Kerberos Security Realm value displayed?

Administration > Settings > Security > Kerberos Security Realm

# Which CDH service(s) host a property for enabling Kerberos authentication?

* HDFS  
* YARN  
* Zookeeper
* Oozie  
* Hive  
* Hue  

# How do you upgrade the CM agents?

You can do it via Cloudera Manager or command line. 

With Cloudera Manager you can go to:

`https://my_cloudera_manager_server_host:port/cmf/upgrade`
`https://my_cloudera_manager_server_host:port/cmf/upgrade-wizard/welcome`

and follow the wizard.

Using the command line you in short you:

1. Remove yum repo files
2. Create a new yum repo file with the correct version
3. Stop the agent
4. Upgrade Java
5. Upgrade agent packages via yum
6. Verify

# Give the tsquery statement used to chart Hue's CPU utilization?

`select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=hue`

# Name all the roles that make up the Hive service

* Gateway
* WebHCat Server
* Hive Metastore Server
* HiveServer2

# What steps must be completed before integrating Cloudera Manager with Kerberos?

* Set up a working KDC. Cloudera Manager supports MIT KDC and Active Directory.
* The KDC should be configured to have non-zero ticket lifetime and renewal lifetime.
* OpenLdap client libraries should be installed on the Cloudera Manager Server host if you want to use Active Directory. Also, Kerberos client libraries should be installed on ALL hosts.
* Cloudera Manager needs an account that has permissions to create other accounts in the KDC.
* By default, CentOS and Red Hat Enterprise Linux 5.5 (and higher) use AES-256 encryption for Kerberos tickets, so the Java Cryptography Extension (JCE) Unlimited Strength Jurisdiction Policy File must be installed on all cluster hosts as detailed below. Alternatively, the Kerberos instance can be modified to not use AES-256.
* If an administrator principal to act on behalf of Cloudera Manager cannot be created on the Kerberos KDC for whatever reason, Cloudera Manager will not be able to create or manage principals and keytabs for CDH services. That means these principals must be created manually on the Kerberos KDC and then imported (retrieved) by Cloudera Manager.