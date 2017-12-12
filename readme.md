This is a "first steps" workshop using:
* [OVH Public Cloud](http://www.ovh.com/cloud): a IaaS solution based on OpenStack by OVH
* [cloud-init](https://cloudinit.readthedocs.io/en/latest/): a configurable boot script manager for cloud instance

# Purpose

You'll run a workshop which present you the basics of OVH Public Cloud.

There will be 3 steps:
 * Horizon: This is the official OpenStack GUI (Graphical User Interface), you'll use it to start an instance and add a disk
 * OpenStack-Client: This is the official CLI (Command Line Interface), you'll simply launch two instances
 * Cloud-Init: This is the first step to automation, it will help you to launch a post-install script

Every instructions will be provided to guide you step by steps. The required knowledges are simply the basics of SSH and Linux command line.

## Schema

TODO

# Requirements

To start the workshop, you'll need an OVH Account and a new cloud project.

## OVH account

You can skip this section if you already have one but be sure to be able to run a workshop on it (your company could have some restrictions about that if you plane to use your company's account).

If you run this workshop online and you don't have an account, just [sign up](https://www.ovh.com/fr/support/new_nic.xml) and log in to the web console.

If you run this workshop during a training session, the OVH account creation is not include in the schedule. Be sure to have it before the session and go directly in to the web console.

## Cloud project

Click on the "Cloud" tab then on "Order" button. Select "Cloud Project" and use your voucher code to apply.

## An OpenStack User

Go back to your cloud project and click on "OpenStack" in the left bar, then on "Add a User". We'll use the login and password to log into Horizon.

## Video

If you need help on that part, please watch those videos:

 * [Open an OVH account and create an OpenStack User](https://www.youtube.com/watch?v=BIMb0iR1YhY)

# Let's Go!

A server is available with a prepared environment.

```bash
ssh bounce@xxx.xxx.xxx.xxx
```

The IP and the password are provided during the workshop. You have to give a unique ID, it can be your desktop ID or your firstname.name (without accent and space). In case of connection lost, just redo the same.

Create a file named credentials and paste the content of the downloaded file on the previous step.

```bash
git clone https://github.com/pilgrimstack/workshop-101.git
```

Let's go to the [Horizon environment](./0.horizon).
