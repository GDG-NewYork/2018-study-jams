# Getting Started With Cloud Shell and gCloud

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

[Google Cloud Shell](https://cloud.google.com/shell/docs/) is an interactive shell environment for the Google Cloud Platform. It is pre-provisioned with the Google Cloud SDK, the _gcloud_ command-line utility, 5GB of persistent disk storage, a code editor, and built-in authorization to the GCP Console projects and resources. Learn more about its features [here](https://cloud.google.com/shell/docs/features). 

Cloud Shell is itself a Debian-based VM that is provisioned on a per-user, per-session basis. It persists while your Cloud Shell instance is active, and is shut down after an hour of inactivity. The biggest benefit is the ability to manage all your GCP projects from a (cloud-hosted) interactive shell _without_ having to install any SDK, tools or dependencies in your development (desktop) machine.


### 3. ```WHAT YOU'LL LEARN```

How to initialize a Google Cloud Shell and connect to your projects & resources on the Google Cloud Platform.


### 4. ```WHAT YOU'LL DO```

> FIRST SETUP

 - Click the Cloud Shell (look for ```>-```) icon to start the VM
 - Verify you are logged in with ```gcloud auth list```
 - Verify your current project with ```gcloud config list project```
 - If not set, set with ```gcloud config set project <id>```

> NEXT EXPLORE

 - Check commands ```gcloud -h```
 - Get help on specific commands e.g., ```gcloud help config``` for "config"
 - View configuration ```gcloud config list```
 - View detailed configuration ```gcloud config list --all```
 - Change to home directory ```cd $HOME```
 - Inspect BASH shell config ```cd $HOME; vi .bashrc```

> NEXT USE A SERVICE: e.g., CLOUD STORAGE

 - Cloud storage managed using ```gsutil``` utility
 - Check commands ```gsutil --help```
 - Make bucket (create) ```gsutil mb gs://my-unique-bucket-name```
 - Create dummy data ```cd $HOME; echo "Hello World!" > test.dat```
 - Upload it to bucket ```gsutil cp test.dat gs://my-unique-bucket-name```x

### ```TROUBLESHOOTING```

This section is meant to capture any issues encountered during this lab, and to provide clarifications to process if useful.

> Got a session with Cloud Shell icon disabled

QwikLabs indicated this could have been a transient issue caused by poor network connectivity. Take a screenshot of the issue and wait 24 hours to see if issue persists. If so, take a second screenshot and send both to _support@qwiklabs.com_ with a description of the problem. _This is a fairly rare issue though_