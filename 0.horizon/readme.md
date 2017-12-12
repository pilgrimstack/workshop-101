You'll manipulate the Horizon interface. This is the official OpenStack graphical interface.

> **Vocabulary**
>
> * *an instance* is a cloud server
> * *a flavor* is the technical definition of an instance type (ex: 8vCPU, 30G RAM, 50G disk)
> * *a volume* is an additionnal disk which can be linked to an instance
> * *a region* is a part of an OpenStack deployment in a particular datacenter
> * *an image* is an operating system ready for the cloud environment

# Log into Horizon

Go to [https://horizon.cloud.ovh.net/](https://horizon.cloud.ovh.net/) and use the login/password you got when you created the OpenStack user.

As OVH Public Cloud is a multi-region product, the top menu bar give you the possibility to change from one region to another (near the OVH logo), select *GRA3* for exemple.

# Generate and upload the SSH key

A Linux instance need to embde an SSH key to let the user log in. In your terminal, use this command to generate the SSH key.
```bash
ssh-keygen
```
You can use the default value for each question using **Enter**. Once it's done, you can display the public key using this command.
```bash
cat .ssh/id_rsa.pub
```
Copy this key, we'll upload it into OpenStack.

In Horizon, on the left menu bar, go to *Compute* > *Key Pairs*, then click on *Import Key Pair* on the right side.

Give the name "mykey" and past the content of the key before saving.

# Launch your first instance

 * Go to *Compute* > *Instances* menu on the left bar
 * Click on *Launch Instance*
 * Give the name "inst01"
 * In *Source*, select "Create New Volume: No" and the image "Debian 8"
 * In *Flavor*, select the flavor "s1-2"
 * In *Key Pair*, verify "mykey" has been selected
 * Launch the instance and wait until the instance status switch to "Active"

# Add a volume

 * Go to *Volumes* > *Volumes* menu on the left bar
 * Click on *Create Volume*
 * Give the name "vol01"
 * Change the size to 5GB
 * Create the volume
 * Expand the menu at the end of the volume line and select *Manage Attachments*
 * Select "inst01" in *Attach to Instance* entry
 * Validate with *Attach Volume*

# Connect to the instance

 * Go back to the *Instances* menu to get the inst01 IP
 * Connect to the instance using the terminal
   ```bash
   ssh debian@IPv4_Public
   ```
 * Verify the 5GB volume is here
   ```bash
   sudo fdisk -l /dev/sdb
   ```
 * logout with
   ```bash
   exit
   ```

# Go to the next step

```bash
cd ../1.cli
```
Let's go to the [cli environment](../1.cli) for more fun.
