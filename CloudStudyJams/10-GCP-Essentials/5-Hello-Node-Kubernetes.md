# Hello Node Kubernetes


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

> ======== Kubernetes
 
[Kubernetes](https://kubernetes.io/) is an open-source system for automating the _deployment_, _scaling_ and _management_ of containerized applications across _clusters_ of hosts. It can run on many different environments (from desktops to servers, multi-node clusters and clouds)

At its core, Kubernetes works by grouping containers (that make up an application) into logical units that simplify discovery and management. Features include:
 
 - Automatic binpacking: optimizing container placement for resource needs
 - Self-healing: auto-restart failing containers, monitor container health
 - Service discovery & load balancing: dedicated {IP per container, DNS per set of containers} for easy load-balancing
 - Automated rollout/rollback: Progressive upgrades without health monitoring
 - Storage orchestration: attach & auto-mount diverse storage systems of choice

and more.

> ======== Kubernetes Engine

[Kubernetes Engine](https://cloud.google.com/kubernetes-engine/) is a cloud-hosted managed version of Kubernetes running on the Google Compute Engine. By using Kubernetes Engine, you can focus more on _how to use_ Kubernetes, instead of worrying about _how to setup_ the environment.

Kubernetes Engine is a Google-managed version of Kubernetes (k8s), running in Google Compute Engine, and orchestrating **Docker** based containers. Here "fully-managed" means Google keeps k8s software up-to-date, and ensures k8s clusters are operational and highly-available by default. It also _auto-scales_ (up or down) your app to optimize resource usage, _auto-upgrades_ your cluster to latest k8s versions, and _auto-repairs_ k8s nodes when they fail a health check. Plus support for enhanced features like identity & access management, integrated logging and monitoring etc.

Kubernetes Engine has an associated [Google Container Registry](https://cloud.google.com/container-registry/) that simplifies your ability to store and access your private Docker images (customized for your app/workload)


> ======== Kubernetes Terminology
 
 1. _Containers_ (aka "virtualization engines") are isolated user-space instances that can be co-resident on the same host machine. Think of it as the lowest level of _micro-service_ that holds the running application, its libraries and dependencies. Containers allow for optimal usage of machine resources (VM-level) while preserving secure separation of applications (process-level) for efficient provisioning.

 2. _Pods_ are the basic scheduling unit in k8s. A pod is a set of containers (1 or more) that are guaranteed to be co-located on the same host machine, and can thus share resources. Think of it as a higher-level abstraction for a containerized component (i.e., a set of micro-services that act together)

 3. _Nodes_ (aka "Worker") are the single machines (VMs) where containers are deployed. A node can host multiple containers. Some subset of co-hosted containers may belong to a single pod. Nodes themselves can be organized into _clusters_ that are managed (or "orchestrated") by the _Kubernetes Master_

 4. _Kubernetes Master_ (aka "Controller") manages workloads and coordinates communications across the system. Kubernetes is a master-slave architecture where this central controller (master) provisions apps on distributed workers (nodes), monitors their health, and takes appropriate scheduling and deployment actions.

Learn more [about Kubernetes](https://kubernetes.io/docs/concepts/overview/what-is-kubernetes/) and [Containers](https://cloud.google.com/containers/)

How the different parts work together:

 1. Use ```gcloud``` to provision a Google Compute Engine instance
 2. Use ```kubectl``` to provision a Kubernetes Engine within GCE
 3. Kubernetes Engine uses _Google Container Registry_ to find Docker images
 4. Use ```docker build; gcloud docker push``` to make your private Docker images accessible to your Kubernetes clusters.


### 3. ```WHAT YOU'LL LEARN```

How to:

 1. Create a Node.JS server (think micro-service)
 2. Create a Docker container image 
 3. Create a container cluster
 4. Create a Kubernetes pod (subset of containers, same VM)
 5. Scale up services



### 4. ```WHAT YOU'LL DO```

> Setup

 1. Activate Google Cloud Shell 
 2. Use ```gcloud auth list``` to verify credentials
 3. Use ```gcloud config list project``` to verify project ID

> Setup Node Server

 1. Open Google Cloud Shell. Then ```vi server.js```
 2. Add script (see below), save it - then ```node server.js```
 3. Use Cloud Shell [Web Preview](https://cloud.google.com/cloud-shell/docs/features#web_preview) to preview server running on 8080. 
 4. Once you've verified it works, kill server with ```Ctrl-C```.

```
var http = require('http');
var handleRequest = function(request, response) {
  response.writeHead(200);
  response.end("Hello World!");
}
var www = http.createServer(handleRequest);
www.listen(8080);
```


> Create Docker Image

1. Open a Dockerfile. ```vi Dockerfile```
2. Add the Docker config information (see below) and save
3. Build docker image using ```docker build -t gcr.io/PROJECT_ID/hello-node:v1 .``` (where PROJECT_ID is replaced by yours)
4. Once complete, test the image locally ```docker run -d -p 8080:8080 gcr.io/PROJECT_ID/hello-node:v1```
5. You can use web preview to test, or use curl from shell ```curl http://localhost:8080```

```
FROM node:6.9.2
EXPOSE 8080
COPY server.js .
CMD node server.js
```

> Stop your container

 1. Find your docker process ```docker ps ```  
 2. Find ID in result, then ```docker stop <container id>```
 3. Then push docker image to registry ```gcloud docker -- push gcr.io/PROJECT_ID/hello-node:v1```
 4. Check _Console > Tools > Container Registry_ to verify image is listed
  
> Create your cluster

A cluster consists of a Kubernetes _master_ (hosted by Google) and a set of associated _worker_ nodes (represented by Google Compute Engine VMs).

 1. Google Cloud Console > Kubernetes Enginer > Kubernetes Cluster
 2. From console ```gcloud config list project``` to verify project ID
 3. Then ```gcloud container clusters create hello-world --num-nodes 2  --machine-type n1-standard-1 --zone us-central1-f``` to create a cluster with 2 nodes of machine type _n1-standard-1_. Note: _this should be created in the same zone that hosts the container registry entry above_

The cluster is now ready to have an application/workload deployed.

> Create your pod

A pod consists of one or more containers that are tied together as one scheduling unit. Use ```kubectl``` (Kubernetes Master controller utility) to create a pod with a single container from above

```
kubectl run hello-node --image=gcr.io/PROJECT_ID/hello-node:v1 --port=8080 
```

You should see this output: ```deployment "hello-node" created```


> Explore kubectl commands

 1. Check pods ```kubectl get pods```
 2. Check clusters ```kubectl cluster-info```
 3. Check config ```kubectl config view```
 4. List events ```kubectl get events```
 5. Print logs for a container in a pod ```kubectl logs <pod-name>```

See more [kubectl commands](https://kubernetes.io/docs/reference/kubectl/overview/).

> Allow external access

By default pod is provisioned for access by internal IP (inside cluster only). To make it publicly accessible, it needs to be _exposed_ as a k8s service using the "LoadBalancer" flag.

```
kubectl expose deployment hello-node --type="LoadBalancer"

(Output)
service "hello-node" exposed
```

Note that this exposes the deployment (not the specific pod) and will transparently load balance external requests across all members of that deployment. Currently this is just one pod; in practice, there may be replicas of the pod in the deployment as well.

To find the public IP use ```kubectl get services ```

Note that the deployment has (internal) CLUSTER-IP and (public) EXTERNAL-IP values. You should be able to access the deployed service on the latter (at port 8080)

> Scale up your service

Now grow the deployment (number of pods) if you need to scale to larger loads (or for simple fault tolerance)

```
kubectl scale deployment hello-node --replicas=4

(Output)
deployment "hello-node" scaled
```

Verify this scaling using ```kubectl get pods``` or as below:

```
kubectl get deployment

(Output)
NAME         DESIRED   CURRENT   UP-TO-DATE   AVAILABLE   AGE
hello-node   4         4         4            3           16m
```


> Upgrade your service

With K8S you can rollout an updated version of your service without impacting current users.

 1. Edit the service. ```vi server.js```
 2. Add this line: ```response.end("Hello Kubernetes World!");``` (update)
 3. Save update.
 4. Build & publish new docker image 
 
```
docker build -t gcr.io/PROJECT_ID/hello-node:v2 . 
gcloud docker -- push gcr.io/PROJECT_ID/hello-node:v2
```

Now we have the new container images in our registry. All we need to to is update the deployment to let it know it needs to use new images. ```kubectl edit deployment hello-node```

Look for "spec.template.spec.containers.image" in the hierarchy within the _YAML_ file this opens. Update it from ```gcr.io/PROJECT_ID/hello-node:v1``` to ````gcr.io/PROJECT_ID/hello-node:v2```

Save it and verify deployments. ```kubectl get deployments```.
The upgrade of the deployment (pods) should be transparent and seamless to the users.

Last but not least - check out [Kubernetes dashboard](http://kubernetes.io/docs/user-guide/ui/)


### ```TROUBLESHOOTING```

1. If you don't see the _Preview_ option on Cloud Shell, then close the sidebar menu first (click the hamburger icon at top left). This will resize Cloud Shell window to full browser width, and other options will become visible in its menu.
