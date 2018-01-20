# GOOGLE CLOUD TRAINING

Using [QwikLabs Quests](https://google.qwiklabs.com/catalog)

> Prerequisites

Familiarity with standard Linux text editors such as vim, emacs, or nano will be helpful. If you already have your own GCP account, make sure you do NOT use it for this lab. 

> TIP

Open Qwiklabs in an ANONYMOUS window to make sure you are not logged into any of your real Google accounts. 


## [1. GCP Essentials](https://google.qwiklabs.com/quests/23)

Useful shell commands you do many times:

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

_ESTIMATE: 30 mins, TOOK: 10 mins_

> WHAT YOU'LL DO

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

_ESTIMATE: 40 mins, TOOK: 30 mins_

> WHAT YOU'LL DO

 * Connect to computing resources hosted on Google Cloud Platform.
 * Practice using gcloud commands.

> STEPS

 * Try out a number of Cloud Shell commands
```
$ gcloud config list
$ gcloud config list --all
$ gsutil mb gs://my-calvin-hobbes
```








### [1.2 Getting Started with Cloud Shell & gcloud](https://google.qwiklabs.com/focuses/5780)

> WHAT YOU'LL DO

 * 

> Prerequisites

Familiarity with 

> TIP

Open . _Took 12 minutes for me_

> STEPS

 * Log 
