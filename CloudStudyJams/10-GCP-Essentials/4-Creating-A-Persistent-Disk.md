# [Creating a Persistent Disk](https://qwiklabs.com/focuses/6985)

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

Google Compute Engine helps you create VMs, provision them using Cloud Launcher (with required packages) and deploy them for use with automated (and effortless) load-balancing and reliability assurances.

[Persistent Disks](https://cloud.google.com/compute/docs/disks/) are available for use with your VM instances. They exist _independent of your VM_ and can be attached/detached from different VM instances as required. Even if the VM is deleted (or deactivated), the persistent disk continues to retain the stored data, allowing you to "re-attach" it to new VM instances (e.g., for service initialization or data processing needs).

The "Persistent Disk" looks and behaves just like any other standard disk drive on desktops or servers; however, in reality it has its data distributed across several physical disks for redundancy (fault-tolerance) and performance reasons. The Google Compute Engine manages these physical disk allocations and distributed data operations transparently for the developers.

Persistent Disks are available in two types: standard Hard Disk Drives (HDD) and Solid State Drives (SSD). Learn more about [Persistent Disk Options](https://cloud.google.com/compute/docs/disks/) and [Resizing Disks](https://cloud.google.com/compute/docs/disks/add-persistent-disk) for flexibility.

### 3. ```WHAT YOU'LL LEARN```

How to:

 - Create a VM and attach a Persistent Disk to it
 - Format & Mount the Persistent Disk (for access)

### 4. ```WHAT YOU'LL DO```

> First: Create a VM

 1. Login and start Cloud Shell
 2. Use ```gcloud auth list``` to verify login credentials
 3. Use ```gcloud config list project``` to verify project ID
 4. Use ```gcloud compute instances create gcelab --zone us-central1-c``` to create a VM instance called _gcelab_
 5. You can SSH into VM and use ```df``` to check default disk size for VM (you should see _/dev/sda1_ with size of about 10GB)

You may see something like this:
```
google201483_student@gcelab:~$ df

Filesystem     1K-blocks   Used Available Use% Mounted on
udev             1885400      0   1885400   0% /dev
tmpfs             379304   7580    371724   2% /run
/dev/sda1       10188088 988272   8659248  11% /
tmpfs            1896504      0   1896504   0% /dev/shm
tmpfs               5120      0      5120   0% /run/lock
tmpfs            1896504      0   1896504   0% /sys/fs/cgroup
```


> Second: Create the Persistent Disk and attach it to VM

 1. Use ```gcloud compute disks create mydisk --size=200GB --zone us-central1-c``` to create a new _Persistent Disk_ called _mydisk_ with 200GB capacity. Note that this **must** be created in the same zone as the VM that it will be attached to.
 2. Now use ```gcloud compute instances attach-disk gcelab --disk mydisk --zone us-central1-c``` to attach _mydisk_ to the previously created _gcelab_ Vmachine.

> Third: Verify that Disk is attached to VM
 
 1. Use ```gcloud compute ssh gcelab --zone us-central1-c``` to open an SSH session into that VM (accept config defaults)
 2. Use ```ls -l /dev/disk/by-id/``` to list attached disks. You should see a listing with "device name" *scsi-0Google_PersistentDisk_persistent-disk-1* - this is the first (and only) Persistent Disk attached. Note that if you want a recognizable device name, you can provide one during setup using ```gcloud compute instances attach-disk gcelab --disk mydisk --device-name <YOUR_DEVICE_NAME> --zone us-central1-c``` 

> Fourth: [Format](https://cloud.google.com/compute/docs/disks/add-persistent-disk#formatting) and mount the disk

 1. Make a mount point using ```sudo mkdir /mnt/mydisk```
 2. Format disk using _mkfs_ as follows: ```sudo mkfs.ext4 -F -E lazy_itable_init=0,lazy_journal_init=0,discard /dev/disk/by-id/scsi-0Google_PersistentDisk_persistent-disk-1```. This deletes all existing data on disk and reformats it as an _ext4_ filesystem.
 3. Mount the formatted disk at the previously created mount point using ```sudo mount -o discard,defaults /dev/disk/by-id/scsi-0Google_PersistentDisk_persistent-disk-1 /mnt/mydisk``` - explore [mount](http://manpages.ubuntu.com/manpages/xenial/man8/mount.8.html) command to understand options e.g., _discard_ which allows frequent reclaiming of freed space.

Now _df_ shows something like this:

```
google201483_student@gcelab:~$ df

Filesystem     1K-blocks   Used Available Use% Mounted on
udev             1885400      0   1885400   0% /dev
tmpfs             379304   7580    371724   2% /run
/dev/sda1       10188088 988272   8659248  11% /
tmpfs            1896504      0   1896504   0% /dev/shm
tmpfs               5120      0      5120   0% /run/lock
tmpfs            1896504      0   1896504   0% /sys/fs/cgroup
/dev/sdb       205375464  61468 194811852   1% /mnt/mydisk
```


> Fifth: Configure the VM for auto-mount on restart

 1. By default the disk is not auto-mounted if VM restarts
 2. To fix this, edit _fstab_ as root using ```sudo nano /etc/fstab```
 3. Find line starting with _UUID=_ and add the following **below** that line: ```/dev/disk/by-id/scsi-0Google_PersistentDisk_persistent-disk-1 /mnt/mydisk ext4 defaults 1 1```
 4. Save and exit editor using sequence _Ctrl+o Enter Ctrl-x_

Done! This lab explored formatting & mounting of a standard hard disk drive (HDDD). To learn more about how to do this with solid state drives (SSD) check out [this link](https://cloud.google.com/compute/docs/disks/local-ssd#create_a_local_ssd).

### ```TROUBLESHOOTING```
