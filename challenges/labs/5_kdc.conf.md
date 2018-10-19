[kdcdefaults]
 kdc_ports = 88
 kdc_tcp_ports = 88
 default_tkt_enctypes = aes256-cts
 default_tgs_enctypes = aes256-cts
 permitted_enctypes = aes256-cts

[realms]
 OLGIERDG.SG = {
  master_key_type = aes256-cts
  acl_file = /var/kerberos/krb5kdc/kadm5.acl
  dict_file = /usr/share/dict/words
  admin_keytab = /var/kerberos/krb5kdc/kadm5.keytab
  default_principal_flags = renewable
  max_life = 1d
  max_renewable_life = 7d

  # WARNING: aes256-ct:normal is disabled to simplify testing, since it
  # requires the enhanced security JCE policy file to be installed. You should
  # NOT run with this configuration in production or any real environment. You
  # have been warned.
  supported_enctypes = aes256-cts:normal des3-hmac-sha1:normal arcfour-hmac:normal des-hmac-sha1:normal des-cbc-md5:normal des-cbc-crc:normal
 }
