# Installation, Configuration & Validation


## Install Kubernetes masters and nodes

### Install Container runtimes
[Container runtimes](https://kubernetes.io/docs/setup/production-environment/container-runtimes/)

### [Install kubeadm, kubelet and kubectl](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/#installing-kubeadm-kubelet-and-kubectl)

### Create single control-plane cluster with kubeadmin

#### [Initializing your control-plane node _on master only_](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/install-kubeadm/#installing-kubeadm-kubelet-and-kubectl)

#### [Installing a pod network add-on _on master only_](https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/create-cluster-kubeadm/#pod-network)

#### Join the worker nodes to the cluster

Run join command on worker node. This command is printed out at the buttom of the output of `kubeadm init` 

#### Verify

Verify the worker nodes have joined the cluster successfully


# Configure a Highly-Available Kubernetes cluster

https://kubernetes.io/docs/setup/production-environment/tools/kubeadm/high-availability/


# Run end-to-end tests on your cluster
