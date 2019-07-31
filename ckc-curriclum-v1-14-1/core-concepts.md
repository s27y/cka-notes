# Core Concepts

## Understand the Kubernetes API primitives

Get cluster component status
`kubectl get componentstatus`

##Understand the kubernetes cluster architecture

### Master node(The Control Plane)
[Master Components](https://kubernetes.io/docs/concepts/overview/components/)

#### API Server
The communication hub for all cluster components, It exposes the kuberntes API.
All other components go through API server to modify the cluster state
[kube-apiserver](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-apiserver/#kube-apiserver)


#### Scheduler
Assigns your  app to a worker node. Auto-detects which pod to assign to which node based on resource requirements, hardware constraints, etc.
[kube-scheduler](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-scheduler/#kube-scheduler)

#### Controller Manager
Maintains the cluster, Handles node failures, replicating components, maintaining the correct amount of pods, etc
[kube-controller-manager](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-controller-manager/)


#### etcd
Data store that stores the cluster configuration
[etcd](https://kubernetes.io/docs/concepts/overview/components/#etcd)

### Worker node
[Node Components](https://kubernetes.io/docs/concepts/overview/components/#etcd)

#### kubelet
Runs and manages the containers on the node and talks to the API server
[kubelet](https://kubernetes.io/docs/reference/command-line-tools-reference/kubelet/)

#### kube-proxy
Load balances traffic between application components
[kube-proxy](https://kubernetes.io/docs/reference/command-line-tools-reference/kube-proxy/)

#### container runtime
The program that runs your containers(Docker, rkt, containerd)
[container runtime](https://kubernetes.io/docs/concepts/overview/components/#container-runtime)

## Understand Services and other network primitives