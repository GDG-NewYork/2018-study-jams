# Creating a Virtual Machine

_Recommended: 30 minutes_

### 1. ```QWIKLABS USAGE```

The _Connection Details_ side panel has three pieces of information:
 
 - Username
 - Password
 - GCP Project ID

These get populated when you click "Start Lab". They provide temporary credentials and a preset project IDs for doing labs. Recommended process:

 1. Open an anonymous browser to do exercises
 2. Log into Google Cloud Platform using these credentials
 3. Once logged in, make sure the "Project ID" reflects the ID provided
 4. Do not sign up for any free trials or recovery options during login


### 2. ```OVERVIEW```

[Google Compute Engine](https://cloud.google.com/compute/) is Google's _Infrastructure as a Service (IaaS)_ offering. 

  * Run Virtual Machines (VMs) on Google data centers worldwide, with support for both pre-defined and custom VM configurations. 
  * Persistent Disks can be attached to VM, allowing data to be retained (and re-attached) across VM terminations.

Main Compute Engine Features:

 - Predefined Machine Types (micro to high CPU config)
 - Custom Machine Types (config vCPU & memory)
 - Persistent Disks (up to 64TB, HDD or SD formats)
 - Global Load Balancing
 - Transparent Maintenance & Per-Second Billing
 - Choice of OS (Linux, Windows, Community images) or BYO.
 
Virtual Machines and Persistent Disks are Compute Engine "resources". 

 * Compute Engine resources live in [Regions or Zones](https://cloud.google.com/compute/docs/zones). 
 * A Region (e.g., "Eastern US") has one or more Zones (e.g., us-east-1b, us-east-1c, us-east-1d). 
 * A zonal resources can only reside in the allocated zone. There may be dependencies between resources associated with a Compute Engine project. For instance, a Persistent Disk resource can only be attached to a VM resource that is in the same **zone**. And a static IP can only be assigned to a resource that is in the same **region** as the static IP.

### 3. ```WHAT YOU'LL LEARN```

How to do the following:

 - Create VM instances with GCP Console
 - Create VM instances with gCloud CLI
 - Deploy a web server (NGINX) & connect it to your VM

### 4. ```WHAT YOU'LL DO```

> First the setup:

 - Login to GCP using QwikLabs provided credentials
 - Click "Cloud Shell" icon (has `>-` symbol) on GCP Console toolbar 
 - Type ```gcloud auth list``` in shell to verify account info
 - Type ```gcloud config list project``` in shell to verify project id
 - Type ```gcloud config set project <PROJECT_ID>``` to set it if needed
 
> Second, create a VM

 - Go to ```Menu > Compute Engine > VM instances```
 - Click ```Create``` to create a new VM instance
 - Use these parameters
     + name = _gcelab_
     + [zone](https://cloud.google.com/compute/docs/zones) = _us-central1-c_
     + [machine type](https://cloud.google.com/compute/docs/machine-types) = _1 vCPU_
     + boot disk = _default_ (OS Image: Debian)
     + firewall = check _Allow HTTP Traffic_ (required for web server later)
 - On completion, check _VM Instances_ to verify VM was created
     + Check it's external IP
     + Click it's SSH link to [open an SSH session to that VM](https://cloud.google.com/compute/docs/instances/connecting-to-instance)

> Third, install the NGINX server

 - Get root access in SSH session using ```sudo su - ```
 - As root, update OS in VM using ```apt-get update```
 - As root, install NGINX using ```apt-get install nginx -y```
 - Check that NGINX is running using ```ps auxw | grep nginx```
 - Verify server is running by clicking ```External IP``` for VM in GCP Console

> Now, let's repeat the exercise using the **gcloud** CLI instead

 - Open GCP Cloud Shell by clicking ">-" icon in GCP Console
 - Use ```gcloud compute instances create --help``` to see VM create options
 - Create VM instance from CLI using ```gcloud compute instances create gcelab2 --zone us-central1-c``` 
 - Check GCP Console "VM Instances" page to see if a new VM entry occurs
 - Verify creation by SSH-ing into VM ```gcloud compute ssh gcelab2 --zone us-central1-c``` (use empty passphrase)
 - Exit SSH session (and shell) using ```exit```


### ```TROUBLESHOOTING```

This section is meant to capture any issues encountered during this lab, and to provide clarifications to process if useful.

> Initially got a session with Cloud Shell icon disabled

QwikLabs indicated this could have been a transient issue caused by poor network connectivity. The issue no longer occurs and I was able to finish the labs correctly.

> Some folks have encountered an issue whereby the NGINX server is running (verified by 'ps auxw') but clicking the "External IP" link on the VM does not work (indicates no server running at that URL)

I was not able to replicate this behavior in my sessions. One thought is that we should verify that students clicked the "Enable HTTP" option when creating the VM instance. See the [Troubleshooting guide](https://cloud.google.com/compute/docs/tutorials/basic-webserver-apache) for help.
