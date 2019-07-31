
show lable as a column
`kubectl get po -L env`

add annotate to resource
`kubeclt annotate deploy <deploy-name> key=value`

filter object by filed [Field Selectors](https://kubernetes.io/docs/concepts/overview/working-with-objects/field-selectors/)
`kubectl get po --field-selector`
`kubectl got po --field-selector status.phase=Running`
`kubectl get svc --field-selector metadata.namespace=default`
`kubectl get svc --field-selector metadata.namespace=default,status.phase=Running`

Show lable on node
`kubectl get nodes chadcrowell3c.mylabserver.com --show-labels`


 Show kubeconfig settings

`kubectl config view `

View address of master and services

`kubectl get cluster-info`

View full cluster info

`kubectl get cluster-info --dump`

Show all the resources, verbs and assoicated API-group

`kubectl api-resources`

View the pods in the default namespace with a custome view

`kubectl get pods -o custom-columns=POD:metadata.name,NODE:spec.nodeName --sort-by spec.nodeName -n kube-system`

View the endpoints kube-scehuler YAML

`kubectl get endpoints kube-scheduler -n kube-system -o yaml`


Filed selector

`kubectl get pods --field-selector status.phase=Running`

List the services in the namespace via API call

`curl localhost:8001/api/v1/namespaces/my-ns/services`

View the token file from within a pod

`cat /var/run/secrets/kubernetes.io/serviceaccount/token`

View k8s version

`kubectl version --short`

Release the hold on versions of kubeadm and kubelet

`sudo apt-mark unhold kubeadm kubelet`

Install version 1.14.1 of kubeadm

`sudo apt install -y kubeadm=1.14.1-00`

Evict the pods on a node

`kubectl drain [node_name] --ignore-daemonsets`

Schedule pods to the node after maintenance is complete

`kubectl uncordon [node_name]`

Take a snapshot of the etcd datastore using etcdctl

`sudo ETCDCTL_API=3 etcdctl snapshot save snapshot.db --cacert /etc/kubernetes/pki/etcd/server.crt --cert /etc/kubernetes/pki/etcd/ca.crt --key /etc/kubernetes/pki/etcd/ca.key`


Create a service for existing deployment, by default and for convenience, the targetPort is set to the same value as the prot field

`kubectl expose deployment nginx --port 80 --type NodePort`

Delete a label `disk` on node

`kubectl label node chadcrowell3c.mylabserver.com disk-`

Overwrite a lable on node
`kubectl label node chadcrowell2c.mylabserver.com disk=hdd --overwrite`



Taint a node
`kubectl taint node <node_name> node-type=prod:NoSchedule`


Create configmap from commandlin
`kubectl  create configmap appconfig --from-literal=key1=value1 --from-literal=key2=value2`

Verify deployment rollout
` kubectl rollout status deployments kubeserve`

Create serviceaccounts
`kubectl create sa jenkins`

create rolebinding
`kubectl create rolebinding test --role=service-reader --serviceaccount=web:default -n web`

create clusterrole
`kubectl create clusterrole pv-reader --verb=get,list --resource=presistentvolumnes`

create clusterrolebingding
`kubectl  create clusterrolebinding pv-test --clusterrole=pv-reader --serviceaccount=web:default`

Create busybox interactive pod, remove after use
`kubectl run busybox --rm -it --image=busybox /bin/sh`


wget spider just look not downloading
`wget --spider --timeout=1 nginx`

Label pods
`kubectl label pods <pod-name> key=value`

### cfssl
Download the binaries for the cfssl tool:
```
wget -q --show-progress --https-only --timestamping \
  https://pkg.cfssl.org/R1.2/cfssl_linux-amd64 \
  https://pkg.cfssl.org/R1.2/cfssljson_linux-amd64
```
Make the binary files executable:
`chmod +x cfssl_linux-amd64 cfssljson_linux-amd64`

Move the files into your bin directory:
```
sudo mv cfssl_linux-amd64 /usr/local/bin/cfssl`

sudo mv cfssljson_linux-amd64 /usr/local/bin/cfssljson
```
Check to see if you have cfssl installed correctly:
`cfssl version`

Create secret
`kubectl create secret generic file-secret  --from-file=file`

filter by lable
`kubectl logs -l key=value`

Get the logs from all containers on the pod:

`kubectl logs counter --all-containers=true`


Get the logs from a previously terminated container within a pod:

`kubectl logs -p -c nginx nginx`

Stream the logs from a container in a pod:

`kubectl logs -f -c count-log-1 counter`

Tail the logs to only view a certain number of lines:

`kubectl logs --tail=20 nginx`

View the logs from a previous time duration:

`kubectl logs --since=1h nginx`

View the logs from a container within a pod within a deployment:

`kubectl logs deployment/nginx -c nginx`



