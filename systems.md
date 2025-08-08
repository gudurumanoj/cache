## Systems

## uid and gid
userid and groupid are created automatically by the os in order to manage privileges and permissions. Any created user will automatically get uid and gid from 1000. 0 to 999 are reserved for system accounts, services and other special accounts. Root has the privilege of 0 and 0!!
- `/etc/group`: contains the user list
- `/etc/passwd`: basic information about user accounts, including username, user ID, group ID, home directory, and login shell, but not the actual passwords which are usually stored in a separate file like `/etc/shadow`
