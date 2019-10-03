Let's verify that the cluster is up and running...

Usually, it takes some seconds....so please be patient...

# List the deployments

Go to the **master** terminal...

Run `kubectl get deployments`

# Create your first deployment 

As we did with Pods, we can create a deployment without a YAML file.

There are multiple ways to do that. Let's have a look. Please notice the _--dry-run_ option.

`kubectl run --image=nginx cpd -o yaml --dry-run`

`kubectl run --generator=deployment/v1beta1 cpd --image=nginx --dry-run -o yaml`{{execute}}

And finally, the preferred one (previous are DEPRECATED, but quite popular in many places)

`kubectl create deployment --image=nginx cpd -o yaml --dry-run`

With the first two you could even indicate the number of replicas, which is not the case with the last one.

# List the created objects

`kubectl get all`

There should not be any deployment or pod.


