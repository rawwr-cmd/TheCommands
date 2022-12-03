## kubectl --help
## kubectl-k, get-g, describe-d, create-c, apply-a, delete-del (time saving alias)
## which k  (code ~/.bashrc)
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
# docker push id/posts (to push to the docker hub)

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
