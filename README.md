# SAPRouter service for FreeBSD system

This simple script should start SAPRouter using ```sudo service saprouter start``` command.

Just upload it to ```/etc/rc.d/``` or ```/usr/local/etc/rc.d``` directory and assign correct authorizations.

Be aware, that you can run SAPRouter on your FreeBSD system, but you need [Linux emulation support](http://www.freebsd.cz/doc/handbook/linuxemu.html).

## Configuration variables
Configuration is in ```/etc/make.conf``` file:

### saprouter_enable
 - *YES* enable autostart
 - *NO* disable autostart

### saprouter_cn
Common Name in form *p:CN=\<SAPRouter from SAP\>, OU=\<customer number\>, OU=SAProuter, O=SAP, C=DE*

### saprouter_verbosity
Verbosity of the command which goes into the log.
- **1** - Lowest verbosity
- **3** - Highest
- Default: **1**

### saprouter_port
Port on which the SAP Router will listen.
- Default: *3299*

### saprouter_saprouttab
Location of saprouttab file with the routing rules.
- Default: **/usr/saprouter/saprouttab**

### saprouter_hostname
Hostname of SAP Router machine.
- Default: **localhost**

### saprouter_user
User under which the SAP Router will be run and which has SSO to SAP using certificate.
- Default: **saprouter**

### saprouter_log
File where logs are written to
- Default: **/var/log/saprouter.log**

### saprouter_directory
Directory, where does the SAP Router reside, for *SECUDIR* variable.
- Default: **/usr/sap/saprouter**

### saprouter_snclib
Location of libsapcrypto library, for *SNC_LIB* variable.
- Default: */usr/sap/saprouter/libsapcrypto.so**
