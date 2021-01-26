# Instance Userdata

Its basically the information that you can pass into instance when it boots up.

Think of it as a bash script contains all the commands that you need to run when booting up the `ec2` instance.
This can be your regular ubuntu `apt` commands. For example

```bash

#!bin/bash
sudo apt-get upgrade
sudo apt install <xyz-software>

```

You can basically paste this into `userdata` located in advance details when launching an instance.

you can also make a request to userdata by following command.

```console
curl http://169.254.169.254/latest/meta-data/
```