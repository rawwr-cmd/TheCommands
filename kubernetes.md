## kubectl --help
## kubectl-k, get-g, describe-d, create-c, apply-a, delete-del (time saving alias)
## which k  (code ~/.bashrc)
## kubectl apply -f . 
## kubectl apply -f posts.yaml (This will apply the Deployment defined in the my-deployment.yaml file to your Kubernetes cluster,
   - and create any necessary resources (such as Pods and Services) that are required to run it.)
## kubectl get pods (shows the name of each Pod, along with its current readiness and status. we can see that
   - there are pods that are running and ready to handle requests.)
## kubectl describe pod nameOfThePod (The kubectl describe pod command is used to get detailed information about a specific Pod in a Kubernetes cluster.
   - This command shows a detailed view of the Pod's current status, labels, and other metadata,
   - as well as any events or warnings that are related to the Pod.)
## kubectl exec -it nameOfThePod -- cmd (execute a command inside the pod, -- and space to run the command)
      - kubectl exec -it posts -- ls  (posts - name of the pod)
      - kubectl exec -it my-pod -c my-container -- ls (when we have more than one container running in the pod, we can specify using the -c flag.)  
## kubectl logs nameOfThePod
## kubectl delete pod nameOfThePod

## For DEPLOYEMENET
## kubectl create -f posts-depl.yaml (or kubectl apply -f posts-depl.yaml)
## kubectl get deployments (to see all the deployments, to get more detailed information about your deployment, ready is the number of pods)
## kubectl describe deployment
## kubectl describe deployment nameOfThedeployment
## kubectl delete deployment nameOfTheDeployement
## kubectl rollout (to rollout a new version and for help)
## kubecttl rollout restart deployment (new version updation)
## kubectl apply -f posts-depl.yaml (to roll out a new version, configure a new version)
## docker push id/posts (to push to the docker hub)

# services
## kubectl get services
## kubectl describe services 
## kubectl get services ingress-nginx-controller --namespace=ingress-nginx
## kubectl get pods --all-namespaces -l app.kubernetes.io/name=ingress-nginx

# ----------------------------------------------------------

# deployment (basic yaml file)
## deployement is inside the bucket of the objects called v1
apiVersion: apps/v1
kind: Deployment
metadata:
  #name of the deployement
  name: posts-depl
spec:
  ## number of pods we want to create
  replicas: 1
  selector:
    matchLabels:
      # label can be anything instead of app
      app: posts

  #very similar to pod config file
  template:
    metadata:
      labels:
        app: posts
    spec:
      containers:
        - name: posts
          image: chipmunkey/posts:0.0.1
          
# _____________________________________________________________________________________________________________________________

# Basic yaml file (of pod)
apiVersion: v1
## pod : the kind of object we want to create
kind: Pod
## metadata: config options for the object we are going to create
## giving the pod its name that is posts
metadata:
  name: posts
## The exact attributes we want to apply to the object we are about to create
spec:
  ## we can create many containers as we want
  containers:
    # make a container with the name of the posts
    - name: posts
      # the exact image we want to use
      image: chipmunkey/posts:0.0.1

Note:
A cluster IP address is a type of IP address that is used for communication between nodes in a cluster. In a cluster, multiple nodes work together to provide a service, and the cluster IP address is used to facilitate communication between these nodes. This allows the nodes in the cluster to share information and work together to provide the service.

A cluster IP address is different from a regular IP address in that it is only used within the cluster and is not accessible from outside the cluster. This makes it easier to manage the communication within the cluster and helps to improve the performance and reliability of the service provided by the cluster.

## loadbalancer
In Kubernetes, a load balancer is a type of service that distributes incoming traffic evenly among the pods in a deployment. This allows the pods to share the workload and improves the performance and reliability of the deployment.

## ingress
In Kubernetes, an ingress is a collection of rules that allow inbound connections to reach the cluster services. It is a way to give services externally-reachable URLs, load balance traffic, and offer name-based virtual hosting.

An ingress is defined as a Kubernetes resource, and it can be configured to give services externally-reachable URLs and load balance traffic. It can also be used to offer name-based virtual hosting, which allows you to use the same domain name for multiple service


apiVersion: networking.k8s.io/v1 - This line specifies the API version for the ingress resource. It tells Kubernetes which version of the API the ingress object is using.
kind: Ingress - This line specifies the kind of object that the configuration file defines. In this case, it is defining an ingress object.
metadata: - This section contains metadata about the ingress object, such as its name and any annotations that are applied to it.
name: example-ingress - This line specifies the name of the ingress object. This name will be used to identify the ingress in the cluster.
annotations: - This section contains any annotations that are applied to the ingress object. Annotations are key-value pairs that provide additional information or metadata about the object.
kubernetes.io/ingress.class: "nginx" - This line specifies the ingress class for the ingress object. In this case, it is set to "nginx", which tells Kubernetes to use the ingress-nginx controller to handle traffic for this ingress.
spec: - This section contains the specifications or rules for the ingress object. It defines how incoming traffic will be routed to the appropriate services.
rules: - This section contains an array of ingress rules. Each rule defines how incoming traffic will be routed to a specific service.
host: example.com - This line specifies the host that the ingress rule applies to. In this case, the rule will only apply to traffic for the example.com host.
http: - This section contains the HTTP-specific details for the ingress rule. It specifies how HTTP traffic will be routed to the service.
paths: - This section contains an array of path-based routing rules for the ingress. Each rule specifies a path and a backend service that incoming traffic will be routed to.
path: / - This line specifies the path that the ingress rule applies to. In this case, the rule will apply to all paths, because the / character matches all paths.
backend: - This section contains the details of the backend service that incoming traffic will be routed to.
serviceName: example-service - This line specifies the name of the service that incoming traffic will be routed to. In this case, traffic will be routed to the example-service service.
servicePort: 80 - This line specifies the port that the service is listening on. In this case, the example-service service is listening on port 80.
Overall, this configuration file defines an ingress object named example-ingress that uses the ingress-nginx controller to route incoming traffic for the example.com host to the example-service service on port 80. It is a simple example of how to use an ingress to expose a service to the outside world and control how traffic is distributed among the pods in the service.

The pathType field in an Ingress resource specifies the type of routing that should be used for requests matching the specified path. The pathType field can be set to either Exact, Prefix, or ImplementationSpecific, and it determines how the Ingress controller will match incoming requests to the specified path.

If pathType is set to Exact, the Ingress controller will only route requests that match the specified path exactly. For example, if the path is /my-service, requests to /my-service will be routed to the specified backend service, but requests to /my-service/foo will not be routed.
If pathType is set to Prefix, the Ingress controller will route all requests that have the specified path as a prefix. For example, if the path is /my-service, requests to /my-service, /my-service/foo, and /my-service/foo/bar will all be routed to the specified backend service.
If pathType is set to ImplementationSpecific, the Ingress controller will use its own internal routing algorithm to determine how requests should be routed. This can be useful if you want the Ingress controller to use advanced routing features, such as regex matching or path rewriting.

## skaffold 
### skaffold dev

## Google cloud
### gcloud topic --help
### gcloud cheat-sheet
### gcloud components install kubectl (after closing docker)
### gcloud container clusters get-credentials <cluster name> (either running docker or not doesn't matter, can work for both) 
