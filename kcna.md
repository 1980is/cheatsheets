# Docker Stuff
docker build . -f blabla -t ubuntu:nginx1

# K8S Stuff

source <(kubectl completion bash)

## Deployment
kubectl create deploy myweb --image=nginx
kubectl get deploy myweb -o yaml

## Kubectl Commands

kubectl api-resources

