dn: cn=John Doe,dc=example,dc=com
 cn: John Doe
 givenName: John
 sn: Doe
 telephoneNumber: +1 888 555 6789
 telephoneNumber: +1 888 555 1232
 mail: john@example.com
 manager: cn=Barbara Doe,dc=example,dc=com
 objectClass: inetOrgPerson
 objectClass: organizationalPerson
 objectClass: person
 objectClass: top
=========================
-   StartTLS – use the LDAPv3 [Transport Layer Security](https://en.wikipedia.org/wiki/Transport_Layer_Security "Transport Layer Security") (TLS) extension for a secure connection
-   Bind – [authenticate](https://en.wikipedia.org/wiki/Authentication "Authentication") and specify LDAP protocol version
-   Search – search for and/or retrieve directory entries
-   Compare – test if a named entry contains a given attribute value
-   Add a new entry
-   Delete an entry
-   Modify an entry
-   Modify Distinguished Name (DN) – move or rename an entry
-   Abandon – abort a previous request
-   Extended Operation – generic operation used to define other operations
-   Unbind – close the connection (not the inverse of Bind)