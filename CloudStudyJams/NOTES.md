**TABLE OF CONTENTS**

<!--  Table Of Contents: START  -->
 - [GOOGLE CLOUD TRAINING](#google-cloud-training)
    + [1. GCP Essentials](#1-gcp-essentials)
        * [1.1 Creating a Virtual Machine](#11-creating-a-virtual-machine)
        * [1.2 Getting Started with Cloud Shell & gcloud](#12-getting-started-with-cloud-shell--gcloud)
        * [1.3 Provision Services with Cloud Launcher](#13-provision-services-with-cloud-launcher)
        * [1.4 Create a Persistent Disk](#14-create-a-persistent-disk)
        * [1.5 Hello Node Kubernetes](#15-hello-node-kubernetes)
        * [1.6 Monitoring Cloud Infrastructure with Stackdriver](#16-monitoring-cloud-infrastructure-with-stackdriver)
        * [1.7 Setup Network and HTTP Load Balancers](#17-setup-network-and-http-load-balancers)
    + [2. Kubernetes in the Google Cloud](#2-kubernetes-in-the-google-cloud)
        * [2.1 Intro to Docker](#21-intro-to-docker)
    + [3. Scientific Data Processing](#3-scientific-data-processing)
        * [3.1 Rent-a-VM to Process Earthquake Data](#31-rent-a-vm-to-process-earthquake-data)
<!-- Table of Contents: END -->


# GOOGLE CLOUD TRAINING

Study Jam [Agenda](http://bit.ly/gdgnyc-cloud-studyjams-2018) using
[QwikLabs Quests](https://google.qwiklabs.com/catalog) as training paths.

**Prerequisites:**
Familiarity with standard Linux text editors such as vim, emacs, or nano will be helpful. If you already have your own GCP account, make sure you do NOT use it for this lab. 

**TIPS:**
Open Qwiklabs in an ANONYMOUS window to make sure you are not logged into any of your real Google accounts. For each lab, it also helps to review all the content/instructions quickly _before_ you click the green START button to walk through them in practice.

---

## [1. GCP Essentials](https://google.qwiklabs.com/quests/23)

Useful shell commands you'll do many times:

```
// Validate you are setup with right credentials/project

$ gcloud auth list
$ gcloud config list project
$ gcloud config set project <PROJECT_ID>

// Helpful commands
// Add '-h' or '--help' for verbose output

$ gcloud help
$ gcloud config   
```


### [1.1 Creating a Virtual Machine](https://google.qwiklabs.com/focuses/5779).
In this hands-on lab, you’ll learn how to create a Google Compute Engine virtual machine and understand zones, regions, and machine types.
_Estimates 30 mins. **Took 10 mins**_

> **WHAT YOU'LL DO**

 * Create a virtual machine with the Google Cloud Platform Console
 * Create a virtual machine with gcloud command line
 * Deploy a web server and connect it to a virtual machine

> STEPS

 * Log into GCP Console using provided credentials
 * Open Cloud Shell & start it
 * Check if credentials / project are set correctly
 * Understand: [Regions & Zones](https://cloud.google.com/compute/docs/zones)
 * Create: New Machine Instance (Computer Engine > VM Instances > Create)
 * Launch: SSH Session to VM 
 * Install: NGINX Web Server in SSH session (as sudo)
 * Launch: External IP link to verify nginx running
 * Now exit shell (kills nginx process) and repeat the steps, but this time using the Cloud Shell (commandline) rather than dashboard, to create a new VM instance and ssh into it.

### [1.2 Getting Started with Cloud Shell & gcloud](https://google.qwiklabs.com/focuses/5780)
In this hands-on lab, you will learn how to connect to computing resources hosted on Google Cloud Platform via the web. You will also learn how to use Cloud Shell and the Cloud SDK gcloud command. 
_Estimates 40 mins. **Took 15 mins**_

> **WHAT YOU'LL DO**

 * Connect to computing resources hosted on Google Cloud Platform.
 * Practice using gcloud commands.

> STEPS

 * Try out a number of Cloud Shell commands
```
$ gcloud config list
$ gcloud config list --all
$ gsutil mb gs://my-calvin-hobbes
```

> NOTES

 * [Cloud Shell Docs](https://cloud.google.com/shell/)
 * Labs themselves take very little time. But if you actually go through the documentation and explore other options, that will take longer. 

### [1.3 Provision Services with Cloud Launcher](https://google.qwiklabs.com/focuses/5783)
In this hands-on lab you'll learn how to use Cloud Launcher to quickly get started with common operating systems, web frameworks, and databases.
_Estimates 30 minutes. **Took 10 minutes**_

> **WHAT YOU'LL DO**

* Launch a common web stack with Cloud Launcher
* Verify your deployment

> STEPS

 1. Go to Google Cloud Console. Click _Cloud Launcher_ (rocket icon)
 2. Go to Search bar. Look for _Nginx Certified By Bitnami_
 3. Select result. Click _Launch on Compute Engine_ (this starts a VM instance with that software directly)
 4. Configure Nginx instance (name, region) in window displayed. 
 5. Click to deploy. (Should show progess status ..)
 6. Verify deployment by clicking _Visit the Site_ (via console)
 7. Verify deployment by clicking _SSH_ (for VM instance), then running ``` ps aux | grep nginx``` to verify the process is running.
 8. Done!

Bonus:
 1. Use Search bar in _Cloud Launcher_ window to explore what other software packages are available for seamless Cloud deployment.

> NOTES


```
CONTINUE WITH THE LESSONS AT HOME
```

### [1.4 Create a Persistent Disk](https://google.qwiklabs.com/focuses/6986)
In this hands-on lab, you’ll learn how to create a persistent disk and use it on a Google Compute Engine virtual machine. You’ll also learn about zones, regions, and different disk types.
_Estimates 30 minutes, takes y minutes_

> **WHAT YOU'LL DO**

> STEPS

> NOTES


### [1.5 Hello Node Kubernetes](https://google.qwiklabs.com/focuses/5781)
In this hands-on lab, you'll learn how to turn your code into a replicated application running on Kubernetes. You'll create a Node.js app, create a Docker container from it, deploy it to Kubernetes Engine, and scale it up.
_Estimates 60 minutes, takes y minutes_

> **WHAT YOU'LL DO**

> STEPS

> NOTES

### [1.6 Monitoring Cloud Infrastructure with Stackdriver](https://google.qwiklabs.com/focuses/5782)
In this hands-on lab we take a look through some of the information provided by the Stackdriver Monitoring tools, and teach some of the concepts you will need to know to take advantage of Stackdriver Monitoring effectively.
_Estimates 45 minutes, takes y minutes_

> **WHAT YOU'LL DO**

> STEPS

> NOTES

### [1.7 Setup Network and HTTP Load Balancers](https://google.qwiklabs.com/focuses/5784)
In this hands-on lab, you'll learn how setup both network load balancers and HTTP load balancers for your application running in Google Compute Engine virtual machines.
_Estimates 40 minutes, takes y minutes_

> **WHAT YOU'LL DO**

> STEPS

> NOTES

---

## [2. Kubernetes in the Google Cloud](https://google.qwiklabs.com/quests/29)

### [2.1 Intro to Docker](https://google.qwiklabs.com/focuses/7010)
In this lab you will familiarize yourself with the basic Docker container environment commands. You will create, run, and debug containers, and learn to pull and push images to and from Google Container Registry.
_Estimates 40 minutes, takes y minutes_

> **WHAT YOU'LL DO**

> STEPS

> NOTES

---

## [3. Scientific Data Processing](https://google.qwiklabs.com/quests/28)

### [3.1 Rent-a-VM to Process Earthquake Data](https://google.qwiklabs.com/focuses/5688)
In this lab you spin up a virtual machine, configure its security, access it remotely, and then carry out the steps of an ingest-transform-and-publish data pipeline manually. This lab is part of a series of labs on processing scientific data.
_Estimates 40 minutes. **Took 12 minutes**_

> **WHAT YOU'LL DO**
> 
In this lab, you:

 * Create a Compute Engine instance with the necessary access and security.
 * SSH into the instance.
 * Install the software package Git (for source code version control).
 * Ingest data into the Compute Engine instance.
 * Transform data on the Compute Engine instance.
 * Store the transformed data on Cloud Storage.
 * Publish Cloud Storage data to the web.*

> STEPS

 1. Create VM Instance (Compute Engine > VM Instances > Create)
 2. Change Identify API access (to 'Allow Full Access to Cloud APIs')
 3. Open SSH Terminal for created VM Instance (from VM status line)
 4. Verify Compute Engine instance with ```cat /proc/cpuinfo```
 5. Install required Software in session.
    * Update package repo list. ```sudo apt-get update```
    * Install git. ```sudo apt-get -y -qq install git```
    * Verify git install. ```git --version```
 6. Install demo app code & run it.
    * Clone repo. ```git clone https://github.com/GoogleCloudPlatform/training-data-analyst```
    * Find lab directory. ```cd training-data-analyst/CPB100/lab2b```
    * Check ingest program code ```less ingest.sh```
    * Run ingest program ``` bash ingest.sh```
    * Verify data was ingested ```head earthquakes.csv```
 7. Transform ingested data into map visualization.
    * Review Python Notebook in browser ```https://github.com/GoogleCloudPlatform/datalab-samples/blob/master/basemap/earthquakes.ipynb```
    * Install Python dependencies in VM instance ```bash install_missing.sh```
    * Run the transformation code ```python transform.py```
    * Verify a new `.png` file was created ```ls -l```
 8. Store transformed data in Cloud Storage/
    * Create bucket using GCP Console (Products > Storage > Create)
    * Pick globally-unique bucket name (and remember it)
    * In Compute Engine SSH window, ```gsutil cp earthquakes.* gs://< ``` 
    * Verify 3 files copied (Storage > Check your named bucket)
 9. Publish Cloud Storage Files to Web
    * Select the three files from Storage (in Google Console)
    * Click "Share publicly" to get listing
    * Click "Share publicly" checkbox for only the ".htm" file 
    * Verify visibility by visiting the URL generated for this

Done. 
_Question: How did the bucket name you chose related to the published Google Cloud Storage public link URL?_
 * I chose _gdgnyc-earthquakes_ as the bucket name
 * The public URL ended up being _https://storage.googleapis.com/gdgnyc-earthquakes/earthquakes/earthquakes.htm_

> NOTES
