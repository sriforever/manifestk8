# Manifest.yaml
## Prerequisites: 
    - install minikube;change paths
    - install kubectl;change paths
    - run minikube start in CMD
## Apply YAML:
    - run kubectl apply -f manifest.yaml (make sure yaml is the current folder)
    - creates new namespace called 'sample'
    - creates deployment 'my-hellokube' with
        - 5 replicas (pods)
        - from docker hub - paulbouwer/hello-kubernetes:1.10
        - using port 8080
        - with label 'hellokube'
    - creates a service 'my-hellokube-svc' with loadbalancer point back pods with label 'hellokube'
    - minikube service my-hellokube-svc -n sample - this will launch the minikube URL with port in defult browser
    - kubectl get deployments --namespace=sample - this will return the deployemnt details with no of pods running
    - kubectl get pods --namespace=sample - this will return the pods running the image
    - kubectl get services --namespace=sample - this will give service details
    - finally run minikube delete --all - this willo remove all resources

## the same YAML with little change required for handling cloud specific CLIs
