# Permissions

Our goal is to read the root file, and from the title we get some *hint* that it has something to do with permissions.

1. After `ls -l` on `/` directory, it can be seen that `root` is a directory which is also a file in linux (this will come in handy later). We can also see the permissions of root directory `drwx------   1 root   root     23 Aug  4  2023 root` which means that owner name is `root` and group name is `root`. The permission also indicates that the only one that has access to `rwx` or read, write, and execute the file is the file owner. We are not `root` user then it is not possible to directly go inside `root` file to read whats inside.

2. Since we don't have access, then we might need to use the command `sudo` or "super user do". This basically gives us super power to
do things that we aren't supposed to be able to do (execute command that are restricted to user `root`). This super power (of access) is actually given by the system administrators, and to check what access are given to us we can use `sudo -l`. After running this command we can see that we are given access to execute `/bin/vi` which can be done by doing `sudo vi`. `vi` is a command that is a tool can be used to edit file from terminal similar to `nano` and `vim`.

3. Now back to our first observation, we know that `root` directory is a file which means it can be read, and when reading through it we can actually see what files are inside this directory. Its file owner (`root`) can read, write, and execute, and note that `vi` is file editor tool. Hence using `sudo vi root` we can actually check what are the files inside `root` directory and we can see `flag.txt` which inside resides the flag that are desired.
