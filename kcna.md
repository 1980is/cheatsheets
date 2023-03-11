# Docker Stuff
docker build . -f blabla -t ubuntu:nginx1

# K8S Stuff

Get bash completion for kubectl: ``source <(kubectl completion bash)`` \
Get help: ``kubectl explain pod``and ``kubectl explain pod.spec`` and ``kubectl explain --recursive pod.spec``This is a tree shape hierachy of all the resources that are available.

## Stuff to install Minikube, Cubectl

https://minikube.sigs.k8s.io/docs/start/ \
https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/

## Deployment
kubectl create deploy myweb --image=nginx
kubectl get deploy myweb -o yaml

## Kubectl Commands

Show available resources: ``kubectl api-resources`` \
Show versions: ``kubectl api-versions`` \
Get more information about resource properties: ``kubectl explain <resource>`` \
Show fields in the resource spec: ``kubectl explain <resource>.spec`` \
Show all field available: ``kubectl explain --recursive <resource>``
