# Verify user privileges

```
[olgierdg@ip-172-31-46-123 ~]$ kinit
Password for olgierdg@BOOTCAMP:
[olgierdg@ip-172-31-46-123 ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-41-146.eu-central-1.compute.internal:10000/default;principal=hive/ip-172-31-41-146.eu-central-1.compute.internal@BOOTCAMP
scan complete in 3ms
Connecting to jdbc:hive2://ip-172-31-41-146.eu-central-1.compute.internal:10000/default;principal=hive/ip-172-31-41-146.eu-central-1.compute.internal@BOOTCAMP
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-41-146.eu-central-1> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20181017142424_c0bbd126-4f00-4162-ab78-f2e239de11d3): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017142424_c0bbd126-4f00-4162-ab78-f2e239de11d3); Time taken: 0.059 seconds
INFO  : Executing command(queryId=hive_20181017142424_c0bbd126-4f00-4162-ab78-f2e239de11d3): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017142424_c0bbd126-4f00-4162-ab78-f2e239de11d3); Time taken: 0.118 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (0.255 seconds)
0: jdbc:hive2://ip-172-31-41-146.eu-central-1> USE DEFAULT;
Error: Error while compiling statement: FAILED: SemanticException No valid privileges
 User olgierdg does not have privileges for SWITCHDATABASE
 The required privileges: Server=server1->Db=*->Table=+->Column=*->action=select;Server=server1->Db=*->Table=+->Column=*->action=insert; (state=42000,code=40000)
0: jdbc:hive2://ip-172-31-41-146.eu-central-1>
```

# Create a Sentry role with full authorization

```
0: jdbc:hive2://ip-172-31-41-146.eu-central-1> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20181017142727_e608e807-74b8-4540-8b36-e4e8f326890f): CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017142727_e608e807-74b8-4540-8b36-e4e8f326890f); Time taken: 0.065 seconds
INFO  : Executing command(queryId=hive_20181017142727_e608e807-74b8-4540-8b36-e4e8f326890f): CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017142727_e608e807-74b8-4540-8b36-e4e8f326890f); Time taken: 0.405 seconds
INFO  : OK
No rows affected (0.481 seconds)
0: jdbc:hive2://ip-172-31-41-146.eu-central-1> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20181017142828_a75b2c7b-322c-4756-a46b-faf7766779af): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017142828_a75b2c7b-322c-4756-a46b-faf7766779af); Time taken: 0.073 seconds
INFO  : Executing command(queryId=hive_20181017142828_a75b2c7b-322c-4756-a46b-faf7766779af): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017142828_a75b2c7b-322c-4756-a46b-faf7766779af); Time taken: 0.071 seconds
INFO  : OK
No rows affected (0.155 seconds)
0: jdbc:hive2://ip-172-31-41-146.eu-central-1> GRANT ROLE sentry_admin TO GROUP olgierdg;
INFO  : Compiling command(queryId=hive_20181017142828_631d7f20-3c6a-43a8-a49b-2bf640f0ffd7): GRANT ROLE sentry_admin TO GROUP olgierdg
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017142828_631d7f20-3c6a-43a8-a49b-2bf640f0ffd7); Time taken: 0.047 seconds
INFO  : Executing command(queryId=hive_20181017142828_631d7f20-3c6a-43a8-a49b-2bf640f0ffd7): GRANT ROLE sentry_admin TO GROUP olgierdg
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017142828_631d7f20-3c6a-43a8-a49b-2bf640f0ffd7); Time taken: 0.06 seconds
INFO  : OK
No rows affected (0.118 seconds)
0: jdbc:hive2://ip-172-31-41-146.eu-central-1> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20181017142828_a8d46a5a-5df9-48d4-af6b-ba3c645540b2): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017142828_a8d46a5a-5df9-48d4-af6b-ba3c645540b2); Time taken: 0.073 seconds
INFO  : Executing command(queryId=hive_20181017142828_a8d46a5a-5df9-48d4-af6b-ba3c645540b2): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017142828_a8d46a5a-5df9-48d4-af6b-ba3c645540b2); Time taken: 0.106 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.228 seconds)
0: jdbc:hive2://ip-172-31-41-146.eu-central-1>
```

# Create test roles

```
0: jdbc:hive2://ip-172-31-41-146.eu-central-1> CREATE ROLE reads;
INFO  : Compiling command(queryId=hive_20181017143131_1b09d7d2-8494-4c96-96bf-9d8adaafaa15): CREATE ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017143131_1b09d7d2-8494-4c96-96bf-9d8adaafaa15); Time taken: 0.046 seconds
INFO  : Executing command(queryId=hive_20181017143131_1b09d7d2-8494-4c96-96bf-9d8adaafaa15): CREATE ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017143131_1b09d7d2-8494-4c96-96bf-9d8adaafaa15); Time taken: 0.02 seconds
INFO  : OK
No rows affected (0.114 seconds)
0: jdbc:hive2://ip-172-31-41-146.eu-central-1> CREATE ROLE writes;
INFO  : Compiling command(queryId=hive_20181017143131_f298281c-c69e-4d77-b33c-8d4eb9eca5a4): CREATE ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017143131_f298281c-c69e-4d77-b33c-8d4eb9eca5a4); Time taken: 0.052 seconds
INFO  : Executing command(queryId=hive_20181017143131_f298281c-c69e-4d77-b33c-8d4eb9eca5a4): CREATE ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017143131_f298281c-c69e-4d77-b33c-8d4eb9eca5a4); Time taken: 0.018 seconds
INFO  : OK
No rows affected (0.08 seconds)
0: jdbc:hive2://ip-172-31-41-146.eu-central-1>
```

# Grant read privilege for all tables to reads

```
0: jdbc:hive2://ip-172-31-41-146.eu-central-1> GRANT SELECT ON DATABASE default TO ROLE reads;
INFO  : Compiling command(queryId=hive_20181017143333_a70dec5f-e8cb-4bfd-95f3-c690e31e2a37): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017143333_a70dec5f-e8cb-4bfd-95f3-c690e31e2a37); Time taken: 0.066 seconds
INFO  : Executing command(queryId=hive_20181017143333_a70dec5f-e8cb-4bfd-95f3-c690e31e2a37): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017143333_a70dec5f-e8cb-4bfd-95f3-c690e31e2a37); Time taken: 0.04 seconds
INFO  : OK
No rows affected (0.113 seconds)
0: jdbc:hive2://ip-172-31-41-146.eu-central-1> GRANT ROLE reads TO GROUP selector;
INFO  : Compiling command(queryId=hive_20181017143333_a27a275e-69b3-4901-a0cf-73e1f885dbb6): GRANT ROLE reads TO GROUP selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017143333_a27a275e-69b3-4901-a0cf-73e1f885dbb6); Time taken: 0.048 seconds
INFO  : Executing command(queryId=hive_20181017143333_a27a275e-69b3-4901-a0cf-73e1f885dbb6): GRANT ROLE reads TO GROUP selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017143333_a27a275e-69b3-4901-a0cf-73e1f885dbb6); Time taken: 0.02 seconds
INFO  : OK
No rows affected (0.075 seconds)
0: jdbc:hive2://ip-172-31-41-146.eu-central-1>
```

# Grant read privilege for default.sample07 only to 'writes':

```
0: jdbc:hive2://ip-172-31-41-146.eu-central-1> REVOKE ALL ON DATABASE default FROM ROLE writes;
INFO  : Compiling command(queryId=hive_20181017143333_1feb5fd3-2157-4d0b-8385-2b6f80390961): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017143333_1feb5fd3-2157-4d0b-8385-2b6f80390961); Time taken: 0.044 seconds
INFO  : Executing command(queryId=hive_20181017143333_1feb5fd3-2157-4d0b-8385-2b6f80390961): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017143333_1feb5fd3-2157-4d0b-8385-2b6f80390961); Time taken: 0.081 seconds
INFO  : OK
No rows affected (0.135 seconds)
0: jdbc:hive2://ip-172-31-41-146.eu-central-1> GRANT SELECT ON default.sample_07 TO ROLE writes;
INFO  : Compiling command(queryId=hive_20181017143434_506c643f-b7db-4126-b92d-fefd2962f0aa): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017143434_506c643f-b7db-4126-b92d-fefd2962f0aa); Time taken: 0.047 seconds
INFO  : Executing command(queryId=hive_20181017143434_506c643f-b7db-4126-b92d-fefd2962f0aa): GRANT SELECT ON default.sample_07 TO ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017143434_506c643f-b7db-4126-b92d-fefd2962f0aa); Time taken: 0.023 seconds
INFO  : OK
No rows affected (0.08 seconds)
0: jdbc:hive2://ip-172-31-41-146.eu-central-1> GRANT ROLE writes TO GROUP inserters;
INFO  : Compiling command(queryId=hive_20181017143434_2aee7ca0-0040-4e10-9553-5b2693c25bc2): GRANT ROLE writes TO GROUP inserters
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20181017143434_2aee7ca0-0040-4e10-9553-5b2693c25bc2); Time taken: 0.042 seconds
INFO  : Executing command(queryId=hive_20181017143434_2aee7ca0-0040-4e10-9553-5b2693c25bc2): GRANT ROLE writes TO GROUP inserters
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017143434_2aee7ca0-0040-4e10-9553-5b2693c25bc2); Time taken: 0.02 seconds
INFO  : OK
No rows affected (0.07 seconds)
0: jdbc:hive2://ip-172-31-41-146.eu-central-1>
```

# kinit as george, then login to beeline

```
[george@ip-172-31-46-123 ~]$ kinit
Password for george@BOOTCAMP:
[george@ip-172-31-46-123 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1100
Default principal: george@BOOTCAMP

Valid starting     Expires            Service principal
10/17/18 14:34:36  10/18/18 14:34:36  krbtgt/BOOTCAMP@BOOTCAMP
        renew until 10/24/18 14:34:36
[george@ip-172-31-46-123 ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-41-146.eu-central-1.compute.internal:10000/default;principal=hive/ip-172-31-41-146.eu-central-1.compute.internal@BOOTCAMP
scan complete in 2ms
Connecting to jdbc:hive2://ip-172-31-41-146.eu-central-1.compute.internal:10000/default;principal=hive/ip-172-31-41-146.eu-central-1.compute.internal@BOOTCAMP
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-41-146.eu-central-1> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20181017143535_528dae6f-f6a4-4d41-8056-08b07bde8180): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017143535_528dae6f-f6a4-4d41-8056-08b07bde8180); Time taken: 0.075 seconds
INFO  : Executing command(queryId=hive_20181017143535_528dae6f-f6a4-4d41-8056-08b07bde8180): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017143535_528dae6f-f6a4-4d41-8056-08b07bde8180); Time taken: 0.115 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.276 seconds)
0: jdbc:hive2://ip-172-31-41-146.eu-central-1>
```

```
[ferdinand@ip-172-31-46-123 ~]$ kinit
Password for ferdinand@BOOTCAMP:
[ferdinand@ip-172-31-46-123 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1200
Default principal: ferdinand@BOOTCAMP

Valid starting     Expires            Service principal
10/17/18 14:35:49  10/18/18 14:35:49  krbtgt/BOOTCAMP@BOOTCAMP
        renew until 10/24/18 14:35:49
[ferdinand@ip-172-31-46-123 ~]$ beeline
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Java HotSpot(TM) 64-Bit Server VM warning: ignoring option MaxPermSize=512M; support was removed in 8.0
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://ip-172-31-41-146.eu-central-1.compute.internal:10000/default;principal=hive/ip-172-31-41-146.eu-central-1.compute.internal@BOOTCAMP
scan complete in 3ms
Connecting to jdbc:hive2://ip-172-31-41-146.eu-central-1.compute.internal:10000/default;principal=hive/ip-172-31-41-146.eu-central-1.compute.internal@BOOTCAMP
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://ip-172-31-41-146.eu-central-1> SHOW TABLES;
INFO  : Compiling command(queryId=hive_20181017143636_470fadb3-6348-40b8-8dc4-3164cdb39e5b): SHOW TABLES
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20181017143636_470fadb3-6348-40b8-8dc4-3164cdb39e5b); Time taken: 0.071 seconds
INFO  : Executing command(queryId=hive_20181017143636_470fadb3-6348-40b8-8dc4-3164cdb39e5b): SHOW TABLES
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20181017143636_470fadb3-6348-40b8-8dc4-3164cdb39e5b); Time taken: 0.125 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.276 seconds)
0: jdbc:hive2://ip-172-31-41-146.eu-central-1>
```