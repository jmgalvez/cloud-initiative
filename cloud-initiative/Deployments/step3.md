## Scaling up

First, just delete the current deployment.

Run `kubectl delete deploy cpd`

Let's create more replicas. Please create a _cpd.yaml_ file using the --dry-run option.

`kubectl create deployment --image=nginx cpd -o yaml --dry-run > cpd.yaml'

Now, open this file in the text editor and modify the number of replicas, set to 4.

Please use the _apply_ kubectl command to create this deployment. Please keep an eye on the other terminal to see what happens.

Run: `kubectl rollout status deployment cpd` and see the output.

Now, run: `kubectl rollout history deployment cpd`. The _Change-cause_ is empty, which is normal. History number can be checked with the next command.

# Let's have a look to the deployment

Run: `kubectl describe deploy cpd` 

Run: `kubectl get events`

# Update the image

Run: `kubectl set image deploy cpd nginx=nginx:1.15` and please review the other terminal. We will see an additional replicaset and the rolling update.

Please note that the old RS is still there with 0 Pods. This is expected and, sometimes, creates some doubts for beginners on k8s. 

What version of ngnix are my pods running? We might run: `kubectl rollout history deployment cpd --revision=2` or `kubectl describe pod` command.

# Modify the image again

We can modify some things in our deployments, i.e., just modify the ngnix version (our app).

Run: `kubectl set image deployment cpd nginx=nginx:1.14.2`

# make some annotations

Run: `kubectl annotate deployment cpd kubernetes.io/change-cause="Update to 1.14.2"` 

Now: `kubectl rollout history deployment cpd`

Generally, we may use the _--record_ option to record the changes:

Run: `kubectl set image deployment cpd nginx=nginx:1.7 --record`
