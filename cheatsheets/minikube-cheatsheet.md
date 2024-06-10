# Minikube Cheatsheet

## Installation

- Install Minikube: [Official Minikube Installation Guide](https://minikube.sigs.k8s.io/docs/start/)

## Getting Started

- Start Minikube: `minikube start`
- Stop Minikube: `minikube stop`
- Delete Minikube cluster: `minikube delete`

## Cluster Operations

- Get cluster info: `kubectl cluster-info`
- List all nodes: `kubectl get nodes`
- List all pods: `kubectl get pods`
- List all services: `kubectl get services`

## Deployments

- Create a deployment: `kubectl create deployment <deployment-name> --image=<image-name>`
- Scale a deployment: `kubectl scale deployment <deployment-name> --replicas=<replica-count>`
- Update a deployment: `kubectl set image deployment/<deployment-name> <container-name>=<new-image>`
- Delete a deployment: `kubectl delete deployment <deployment-name>`

## Services

- Create a service: `kubectl expose deployment <deployment-name> --type=NodePort --port=<port-number>`
- List all services: `kubectl get services`
- Delete a service: `kubectl delete service <service-name>`

## Pods

- Get pod details: `kubectl describe pod <pod-name>`
- Get logs from a pod: `kubectl logs <pod-name>`
- Execute a command in a pod: `kubectl exec -it <pod-name> -- <command>`

## Ingress

- Install Ingress controller: [Official Nginx Ingress Controller Installation Guide](https://kubernetes.github.io/ingress-nginx/deploy/)
- Create an Ingress resource: [Official Kubernetes Ingress Documentation](https://kubernetes.io/docs/concepts/services-networking/ingress/)

## Persistent Volumes

- Create a Persistent Volume: [Official Kubernetes Persistent Volumes Documentation](https://kubernetes.io/docs/concepts/storage/persistent-volumes/)
- Create a Persistent Volume Claim: [Official Kubernetes Persistent Volume Claims Documentation](https://kubernetes.io/docs/concepts/storage/persistent-volumes/#persistentvolumeclaims)

## Troubleshooting

- Check Minikube status: `minikube status`
- Check Kubernetes cluster status: `kubectl cluster-info dump`
- Check pod events: `kubectl get events`
- Check pod logs: `kubectl logs <pod-name>`
- Check pod describe: `kubectl describe pod <pod-name>`

## Minikube Commands

- Enable addons: `minikube addons enable <addon-name>`
- Disable addons: `minikube addons disable <addon-name>`
- Update Minikube: `minikube update`
- SSH into Minikube: `minikube ssh`
- Get Minikube IP: `minikube ip`
- Get Minikube version: `minikube version`
- Pause Minikube: `minikube pause`
- Resume Minikube: `minikube unpause`
- Delete Minikube cache: `minikube delete --all`
- Start Minikube with specific Kubernetes version: `minikube start --kubernetes-version=<version>`
- Start Minikube with specific driver: `minikube start --driver=<driver-name>`
- Start Minikube with custom configuration: `minikube start --config=<config-file>`
- Stop Minikube with specific profile: `minikube stop -p <profile-name>`
- Delete Minikube cluster with specific profile: `minikube delete -p <profile-name>`
