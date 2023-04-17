Linux is primarily a multi-user operating system. The users might not necessarily be a person or organization, but can also be a process or a service.

> To know who you are logged in as, you can use the `whoami` command.

```bash
cat /etc/passwd
  # show users
```

> `/etc/passwd` is a file that keeps track of all the users on the system

### Principle of Least Power

You want a user to have the least amount of power possible to do their job. It is good for security and also for productivity.

For example, if you are a developer, you don't need to be able to change the system configuration. You just need to be able to write code and run it.

As Ubuntu (default user) I cannot crete, delete or change anything in the root directory. (`cd /`)

## Super User

To really take control of the system you have to be a superuser.

And to do that you have to make use of the GREAT `sudo` command.

```bash
sudo =any command=
  # run command as superuser
```

> `sudo` stands for "superuser do"

```bash
sudo whoami
  # root
```

> You become the **root** for that single command only.

#### How to switch to root user?

```bash
sudo su
  # switch to root user

exit
  # switch back to ubuntu user

su =user=
  # switch to user
```

#### How to make a new user?

Ubuntu cannot make a new user, only root can.

```bash
sudo adduser =username=
  # create new user

sudo passwd =username=
  # set password for new user
```

When you create a new user, and try to access sudo with it, you will be prompted with a very funny prompt.

> =user= is not in the sudoers file. This incident will be reported. 🤣

## Groups

Groups are a way to organize users. You can add users to groups and then give permissions to the groups.

```bash
# To add user to a group
sudo usermod -aG =group= =user=

# To add user to sudo group
sudo usermod -aG sudo =user=
```

> a = --append, G = --groups

This way a new user can do sudo things.
