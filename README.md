# kubefed-poc
Proof of Concept for Kubefed   
   
[![Docker build](https://img.shields.io/docker/cloud/build/adrianriobo/kubefed-poc?label=build&logo=docker)](https://hub.docker.com/r/adrianriobo/kubefed-poc/builds)    

# Components  
  
[docker](https://www.docker.com/)    
[kind](https://github.com/kubernetes-sigs/kind)    
[kubectl](https://kubernetes.io/docs/reference/kubectl/kubectl/)    
[helm](https://github.com/helm/helm)    
[kubefed](https://github.com/kubernetes-sigs/kubefed)    

# Usage
    
```
docker run -it --name kubefed-poc \
           -v /var/run/docker.sock:/var/run/docker.sock \
           --entrypoint=bash \
           adrianriobo/kubefed-poc:0.2.0-alpha.1
```
