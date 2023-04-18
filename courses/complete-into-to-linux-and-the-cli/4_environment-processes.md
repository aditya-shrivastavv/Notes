```bash
printenv
  # print environment variables
```

### Variables

```bash
# To set a variable
export =variable= =value=

# To print a variable
echo $=variable=

# To unset a variable
unset =variable=
```

> The variables must be in uppercase

These variables are only available in the current shell session. If you open a new shell session, the variables will be gone.
If you want to set a variable permanently, you can add it to the `/etc/environment` file.

```bash
# To set a variable permanently
sudo vim /etc/environment
```

For setting a variable for a particular user, you can add it to the `~/.bashrc` file in the same way being that user.
