# K8s course

## Prerequisites
- Linux fundamentals + basic shell cmds 😎
- Web development (python + django) 😎
- Networking + Cloud 😞
- Containers 👍

## History & Motivation
- 2000s : Traditional era (on-premise, baremetal, immature tooling)
- 2010s : Virtualization era (Cloud, Configuration mngt tooling, managing a lot of resources)
- 2020s : Containerization era (Efficient schuduling, Health checks, Service discovery, Autoscaling, Persistent storage, Networking)
- Borg (Google) -> K8s

## K8s architecture
- Cluster : set of resource that form k8s system
- Node : a server (vm, physical host, ...) that form the k8s cluster
- Control plane : All the core components system runs
- Data plane : where our enduser apps runs

### Control plane Components
1. Cloud Controller Manager : the Interface between k8s and the cloud provider
2. Controller Manager : runs all the controller that regulate the state of the cluster (k8s control loop : actual state == desired state)
3. API server: all interactions to/inside k8s
4. etcd : the data store that k8s uses to save all the infos about the resources deployed to the cluster
5. Scheduler : Assign pods to nodes based on their infos/usage : CPUs, Memory, Storage, Networking, ...

### Data plane Components
1. Kubelet : spawn and manage worload inside the node & and communications infos to control plane API server
2. k-proxy : setup and maintain the netowrk between differents workloads/pods

### k8s Interfaces
1. CRI : Runtime
2. CNI : Networking
3. CSI : Storage

### CNCF (Cloud Native Comppute Foundation) landscape ?

# Setup
- Installing docker, docker-desktop and devbox
- Copy the devbox of the https://github.com/sidpalas/devops-directive-kubernetes-course course (i start from scratch, so i only needed the devbox.json and devbox.lock, don't forget the gcloud folder)
- Create the env using : devbox shell
- We are using go-task (a Go task runner program for automation, using Taskfile.yaml)
- Setup a KinD simple local cluster (support multiple nodes, as containers)
    1. install completion (to auto-complete task name)
    2. generate config
    3. create cluster
- Create a Civo Cluster # TODO
- Create a GKE cluster  # TODO | the best among cloud provider