# Provisions Services with Cloud Launcher

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

[Google Cloud Launcher](https://cloud.google.com/launcher/docs/) lets you quickly launch common software packages and stacks on Google Compute Engine (VMs) in a few clicks. You can find a comprehensive listing of ready-to-deploy solutions on the [Google Cloud Launcher Page](https://console.cloud.google.com/launcher?_ga=2.38439722.862100619.1517188793-2064135373.1517188015). 

Examples of solutions you can install & launch with:

 * Virtual Machines (diverse OS)
 * Databases 
 * Datasets
 * Blogs & CMS
 * Google Cloud Products
 * Third Party APIs & Services
 * Developer Stacks (e.g., Node, Ruby, Python...)

and more. Google maintains up-to-date _images_ of these packages (but deployed instances are not updated automatically for you). 

In summary - while Compute Engine enables creation of VMs, the Google Cloud Launcher helps you provision it with all the right packages (development stacks, third-party dependencies, software & tools) required for successful deployment.


### 3. ```WHAT YOU'LL LEARN```

How to:

 * Launch a common web stack with Google Cloud Launcher
 * Verify the stack is functioning


### 4. ```WHAT YOU'LL DO```

 1. Open Google Cloud Console. Navigate to Products > Cloud Launcher.
 2. "Search for Solutions" - look for "nginx", select "Certified by Bitnami" result
 3. Click "Launch on Compute Engine" - will show pre-configured VM panel. Update as needed (e.g., change name, zone but leave other defaults)
 4. Click "Deploy" - will create VM instance & provision it (takes a few minutes to complete - watch the progress sidebar)
 5. Click "Visit the Site" - verify that VM with NGINX is running
 6. Click "SSH" - opens a secure shell to that VM
 7. Type "ps auxw | grep nginx" in shell - also verifies NGINX is running
 8. Type "exit" to leave SSH session. 
 9. Close Google Cloud Console browser session.

### ```TROUBLESHOOTING```

Check [this Troubleshooting page](https://cloud.google.com/launcher/docs/troubleshooting) for typical issues.

1. The "Deploy" process takes quite a while. Be patient and wait till you see the green "Visit the Site" button show up (and be enabled).

