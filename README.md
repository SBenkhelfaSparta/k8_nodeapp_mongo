# Running Apps using Kubernetes

## Setup
- Make sure Kubernetes is enabled on Docker's settings. This process could take a while to enable.
- `kubectl` will give commands available and check if install was correctly done, and default clusters can be seen in the Docker app
- `kubectl get service` or `svc` will show the running services with info
- `kubectl get` with `name_of_resource`, `node` or `pods` to view some information
- Can use `kubectl describe pod_id` to see what is inside a pod, which are similar to containers
- Can use Docker desktop to view more container details and see what is running

## The Task
- Create a deployment file called `nginx_deployment.yml`
- `kubectl create -f file_name.yml` will run the deployment file
- `kubectl get deployment` or `deploy` will list what has been deployed and what is running
- `kubectl get pods` will now display each replica
- To launch the deployment to public browsers, we need to create `nginx_service.yml` to connect with the deployment
- Run this service file with same `create` command, and nginx server is now available on localhost
- `kubectl edit deploy nginx-deployment` opens notepad to live edit (vi editor) the deployment file, which has been added to by k8
- `kubectl delete pod pod_id` will delete pods, k8 will redeploy pods with self healing - i.e. if there are 3 and one is deleted/goes down, k8 will load balance while recreating it
- `kubectl edit svc nginx-deployment` will open editing for the service 
- load balancer, cluster ip or node ports can be used for services
- `kubectl delete deploy nginx-deployment` and `kubectl delete svc nginx-deployment` are used to get rid of a service and its pods

## In a Nutshell
- `kubectl create -f mongo-deployment.yml`
- `kubectl create -f nginx_k8_deploy.yml`
- `kubectl delete deploy node`
