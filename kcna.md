# Docker Stuff
docker build . -f blabla -t ubuntu:nginx1

# K8S Stuff

Get bash completion for kubectl: ``source <(kubectl completion bash)`` \
Get help: ``kubectl explain pod``and ``kubectl explain pod.spec`` and ``kubectl explain --recursive pod.spec``This is a tree shape hierachy of all the resources that are available.

## Stuff to install Minikube, Cubectl

https://minikube.sigs.k8s.io/docs/start/ \
https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/

## Deployment
``kubectl create deploy myweb --image=nginx`` \
``kubectl get deploy myweb -o yaml``

## Running Pods
Generally you shouldn't run naked Pods. \
Run a Pod with the name armann. ``kubectl run armann --image=nginx`` \
Generate a YAML file which will allow you to run the application in a declarative way. ``kubectl run armann --image=nginx --dry-run=client -o yaml > armann.yaml`` \
Run the application: ``kubectl create -f armann.yaml``

## Kubectl Commands

Show available resources: ``kubectl api-resources`` \
Show versions: ``kubectl api-versions`` \
Get more information about resource properties: ``kubectl explain <resource>`` \
Show fields in the resource spec: ``kubectl explain <resource>.spec`` \
Show all field available: ``kubectl explain --recursive <resource>``

## Application Resources

### Deployment
The standard resource for running scalable applications with the option to perform zero-downtime application updates. \
``kubectl create deployment nginxfarm --image=nginx --replicas=3 --dry-run=client -o yaml > nginxfarm.yaml``

### Stateful
An alternative to the Deployment Resources. Commonly used for stateful applications like databases.

### DaemonSet
This ensures that one application instance is started on each cluster node.

### Job
Used for singe-shot applications.

## Scalability

### Manually Adjusting Scalability

To manually scale the number of Pods in a Deployment or ReplicaSet use ``kubectl scale``\
You can also use ``kubectl edit`` to change the number of Pods in a ReplicaSet or Deployment. \
To scale the number of nodes in a cluster, add the new node using ``kubeadm join`` command. \

### Autoscaling


