You'll manipulate the OpenStack-Client. This is the official OpenStack command line interface.

# Get and use the credentials

Still on Horizon interface, select *API Access* on the left menu bar, then click on *Download OpenStack RC File* and select the "Idnetity API v2.0" entry. Once the file is downloaded, open it and copy the content.

In the terminal, create a new file and past the content.
```bash
vi openrc.sh
```
Now you can load the environment variables with this command
```bash
source openrc.sh
```
Provide the password of the user (you can regenerate it in your OVH web console if needed).

# Intall the CLI tool

In the terminal, as you are root, you can install the CLI.
```bash
apt-get -y install python-openstackclient
```
This tool can be use to manage all OpenStack ressources with the commande line, that means you can interacte with OpenStack plateform using scripts and command line tricks like pipes, loop or anything else.

But for now, let's start small.

# Delete the previous instance

"inst01" is still here. We'll delete it.

 * List existing instances
   ```bash
   openstack server list
   ```
 * Delete the "isnt01" instance
   ```bash
   openstack server delete inst01
   ```
 * You can list again the instances to verify the instance has been deleted

# Launch 2 instances in one command

To start an instance, you'll need at least an image name, a flavor name and a key name.

 * List the images
   ```bash
   openstack image list
   ```
 * List the flavors
   ```bash
   openstack flavor list
   ```
 * List the keys
   ```bash
   openstack keypair list
   ```
 * Now start the instances
   ```bash
   openstack server create --image 'Debian 8' --flavor 's1-2' --key-name mykey --max 2 inst02
   ```
 * To monitor the instance creation and his status
   ```bash
   openstack server show inst02
   ```

# Delete the instances

It's time to delete those 2 instances

 * List the images
   ```bash
   openstack image list
   ```
 * Delete the instances
   ```bash
   opesntack server delete inst02-XXXXX inst02-YYYYY
   ```

# Go to the next step

Let's go to the [cloud-init environment](../2.cloud-init) for more power.
