# AWS ECS Config
---

## Local Setup

1. sudo dnf config-manager --add-repo https://download.docker.com/linux/fedora/docker-ce.repo
2. sudo dnf install docker-ce docker-ce-cli containerd.io docker-compose-plugin
3. sudo systemctl enable docker
4. sudo systemctl start docker
5. sudo docker run hello-world
6. export AWS_PROFILE=advania-sso
7. aws ecr create-repository --repository-name ajp-wordpress --region eu-west-2
8. sudo docker tag wordpress 531667030042.dkr.ecr.eu-west-2.amazonaws.com/ajp-wordpress
9. sudo docker login -u AWS -p $(aws ecr get-login-password --region eu-west-2) 531667030042.dkr.ecr.eu-west-2.amazonaws.com
10. sudo docker push 531667030042.dkr.ecr.eu-west-2.amazonaws.com/ajp-wordpress

## Creating a cluster
1. 