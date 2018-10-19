[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
 default_realm = OLGIERDG.SG
 dns_lookup_realm = false
 dns_lookup_kdc = false
 ticket_lifetime = 24h
 renew_lifetime = 7d
 forwardable = true

[realms]
 OLGIERDG.SG = {
  kdc = ip-172-31-16-185.eu-west-2.compute.internal
  admin_server = ip-172-31-16-185.eu-west-2.compute.internal
 }

[domain_realm]
 .eu-central-1.compute.internal = OLGIERDG.SG
 eu-central-1.compute.internal = OLGIERDG.SG
