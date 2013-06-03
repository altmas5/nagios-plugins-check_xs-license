check_xs-license
----------------

Nagios plugin that will check if a Citrix XenServer license is near expiring.

This script can run either on the xenserver itself or on another host.
Be sure to install the [XenAPI python module] [1]  if you are running the check from another host.

definition examples
-------------------

- command definition
 
```
define command
{
command_name  check_xs-license
command_line	/path/to/libexec/check_xs-license -H $HOSTADDRESS$
}
```

- service definition

```
define service
{
host_name    	    my-xenserver0
service_description	xenserver0 license
check_command		check_xs-license -u root -p myPass
}
```

[1]: https://pypi.python.org/pypi/XenAPI
