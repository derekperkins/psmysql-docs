# Frequently Asked Questions

## Q: Will *Percona Server for MySQL* with XtraDB invalidate our MySQL support?

A: We don’t know the details of your support contract. You should check with your *Oracle* representative.

## Q: Will we have to *GPL* our whole application if we use *Percona Server for MySQL* with XtraDB?

A: This is a common misconception about the *GPL*. We suggest reading the *Free Software Foundation* ‘s excellent reference material on the [GPL Version 2](http://www.gnu.org/licenses/old-licenses/gpl-2.0.html), which is the license that applies to MySQL and therefore to *Percona Server for MySQL* with XtraDB. That document contains links to many other documents which should answer your questions. Percona is unable to give legal advice about the *GPL*.

## Q: Do I need to install Percona client libraries?

A: No, you don’t need to change anything on the clients. *Percona Server for MySQL* is 100% compatible with all existing client libraries and connectors.

## Q: When using the *Percona XtraBackup* to setup a replication replica on Debian based systems I’m getting: “ERROR 1045 (28000): Access denied for user [‘debian-sys-maint’@’localhost](mailto:'debian-sys-maint'@'localhost)’ (using password: YES)”

A: In case you’re using init script on Debian based system to start 
`mysqld`, be sure that the password for `debian-sys-maint` user has 
been updated, and it’s the same as that user’s password from the server 
that the backup has been taken from. Password can be seen and updated 
in `/etc/mysql/debian.cnf`. For more information on how to set up a 
replication replica using *Percona XtraBackup* see [How to set up a 
replica in 6 simple steps](http://www.percona.com/doc/percona-xtrabackup/2.4/howtos/setting_up_replication.html).