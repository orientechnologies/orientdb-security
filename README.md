# OrientDB Security
The new OrientDB Security plugin provides default implementations of the new security features in OrientDB (starting in 2.2).

OrientDB now supports an advanced external authentication model using a chain of authenticators.  Kerberos authentication is now a standard part of the OrientDB Security plugin.

In addition to new authentication methods, OrientDB Security provides an extensible password validator that can be configured via regular expression.

LDAP import of users and roles is also now a standard feature.

New auditing capabilities have been added, especially monitoring classes and distributed nodes.

Syslog support is also now integrated as part of auditing and can be configured easily.

Complete documentation on how to use and configure the new OrientDB Security plugin can be found here:

[OrientDB New Security Features](https://github.com/orientechnologies/orientdb-labs/blob/master/Security-OrientDB-New-Security-Features.md)

To use the new OrientDB Security plugin, build the project's jar file (a Maven pom.xml is provided) and copy it to the *plugins* directory of your OrientDB installation.


