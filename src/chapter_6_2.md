# Instance Metadata

Instance metadata is data about your instance that can be used to configure or manage the running instance. Its divided into categories and gives you the information about your instance such as `hostname`,`ami-id` and `etc`.

You can run this command within your `ec2` in commandline to get the meta data

```console
curl http://169.254.169.254/latest/meta-data/
```

