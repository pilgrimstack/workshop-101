You'll manipulate cloud-init scripts. This is a standard tool to manipulate settings at boot time.

> **Vocabulary**
>
> * *cloud-init* is a tool started at boot time and configure many thongs on the server
> * *cloud-config* is a syntaxe use to write cloud-init scripts
> * *user-data* is the way OpenStack take the cloud-init information

# Read the cloud-init files

You have 2 yaml files in the directory.
```bash
cd 2.cloud-init
cat etherpad.yaml
```
```bash
cat wordpress.yaml
```

Take time to learn how to build a cloud-init file.

# Launch one of the following instance

```bash
openstack server create --image 'Debian 9' --flavor 's1-2' --key-name mykey --user-data wordpress.yaml wordpress
```
```bash
openstack server create --image 'Debian 9' --flavor 's1-2' --key-name mykey --user-data etherpad.yaml etherpad
```

Wait few minutes and get the IP of the instance (now you know how to do it) to try to join it in a web browser.

