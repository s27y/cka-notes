Taint prod node

`kubectl taint node <node_name> node-type=prod:NoSchedule`

Deployment to be scheduled on prod node
```
apiVersion: apps/v1
kind: Deployment
metadata:
 name: prod
spec:
 replicas: 1
 selector:
   matchLabels:
     app: prod
 template:
   metadata:
     labels:
       app: prod
   spec:
     containers:
     - args:
       - sleep
       - "3600"
       image: busybox
       name: main
     tolerations:
     - key: node-type
       operator: Equal
       value: prod
       effect: NoSchedule
```