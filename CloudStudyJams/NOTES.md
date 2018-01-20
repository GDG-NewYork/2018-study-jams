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

> Prerequisites

Familiarity with standard Linux text editors such as vim, emacs, or nano will be helpful. If you already have your own GCP account, make sure you do NOT use it for this lab. 

> TIPS

Open Qwiklabs in an ANONYMOUS window to make sure you are not logged into any of your real Google accounts. 

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
_Estimates 40 mins. **Took 30 mins**_

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

> STEPS

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
_Estimates 45 minutes, takes y minutes_

> **WHAT YOU'LL DO**

> STEPS

> NOTES

### [1.7 Setup Network and HTTP Load Balancers](https://google.qwiklabs.com/focuses/5784)
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
_Estimates 40 minutes, takes y minutes_

> **WHAT YOU'LL DO**

> STEPS

> NOTES
