* **User Management**
    * `useradd <username>` - Add a user
        * `-c` - Comment
        * `-m` - Create the home directory
        * `-s` - Shell
        * `-u` - User ID
        * `-g` - Default Group
        * `-G` - Additional Groups
    * `userdel <username>` - Delete a user.
    * `passwd <username>` - Set the password for the user.
    * `usermod <username>` - Modify the user (same flags as `useradd`).

* **Group Management**
   * `groupadd <groupname>` - Add a group
   * `groupdel <groupname>` - Delete a group
   * `groupmod <groupname>` - Modify a group
        * `-g` - Group ID
        * `-n` - New Group Name