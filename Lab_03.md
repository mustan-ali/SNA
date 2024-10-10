* Linux permissions annotations:
    * `r` - Read
    * `w` - Write
    * `x` - Execute
    * `-` - No permission
    * `1` - Execute only
    * `2` - Write only
    * `4` - Read only
    * `u` - User
    * `g` - Group
    * `o` - Others
    * `a` - All

* `chmod 777 myfile.txt` - Give all permissions to all users.
* `chmod o+w myfile.txt` - Give write permission to others.
* `chmod g-xw myfile.txt` - Remove execute and write permissions from group.

* `umask` - Show the default file creation permissions.
    * `666` - Default file creation permissions.
    * `777` - Default directory creation permissions.
  
* `umask 022` - Set the default file creation permissions to 755 (777 - 022)

* `ip addr` - Show IP addresses of all network interfaces.