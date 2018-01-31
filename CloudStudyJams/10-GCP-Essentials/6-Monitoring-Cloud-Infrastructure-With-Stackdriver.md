# Monitoring Cloud Infrastructure with Stackdriver

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

[Google Stackdriver](https://cloud.google.com/stackdriver/) provides logging, monitoring and diagnostics capabilities that give you insights into the health, performance and availability of your Cloud-powered apps.
It can currently be used with both Google Cloud Platform (GCP) and Amazon Web Services (AWS).

Among Stackdriver's features are: 
 * [Stackdriver Debugger](https://cloud.google.com/debugger/) 
 * [Stackdriver Error Reporting](https://cloud.google.com/error-reporting/)
 * [Stackdriver Trace](https://cloud.google.com/trace/)
 * [Stackdriver Logging](https://cloud.google.com/logging/) 
 * [Stackdriver Monitoring](https://cloud.google.com/monitoring/)
 * [Partner Integrations](https://cloud.google.com/stackdriver/partners)
 * Dashboards (for visualization), Automated Discovery (of relevant cloud resources & services) & Alerts (for real-time notifications to key events)

### 3. ```WHAT YOU'LL LEARN```

This lesson focuses on [Stackdriver Monitoring](https://cloud.google.com/monitoring/). Stackdriver Monitoring provides dashboards and alerts so you can review performance metrics for cloud services, virtual machines, and common open source servers such as MongoDB, Apache, Nginx, Elasticsearch, and more. You configure Stackdriver Monitoring using the Stackdriver Monitoring Console.

You'll learn to:

 * Enable Stackdriver Monitoring
 * Practice Google Stackdriver Monitoring concepts
 * Navigate Stackdriver Monitoring


### 4. ```WHAT YOU'LL DO```

> First, create resources to monitor

 1. Compute Engine > VM Instances > Create
 2. Products & Services > SQL Instances > Create (MySQL 2nd gen)
 3. Create MySQL 2nd gen with no password

> Setup Stackdriver Monitoring

 1. Projects & Services > Monitoring > Login with Google
 2. Choose an account > (Pick the qwiklab login)
 3. Create your free Stackdriver Account > Create account
 4. Add Google Cloud Platform projects to monitor > Add qwiklabs project ID
 5. Skip AWS Setup
 6. Continue (skips: Install Stackdriver agents)
 7. Stackdriver reports: No reports
 8. Done > Launch monitoring / Continue with the trial

> Explore Monitoring Dashboard

Learn more via [Documentation](https://cloud.google.com/monitoring/docs/)
Then explore dashboard.

### ```TROUBLESHOOTING```

A good starting point for [troubleshooting StackDriver Monitoring API]
(https://cloud.google.com/monitoring/api/troubleshooting)