## Create our deployments

# Terminal setup

By default, _node01_ cannot use kubectl commands.

Please click here.
`scp -r .kube/ node01:/root/`{{execute}}

Go to the node01 terminal and type this:

`watch kubectl get all -o wide`

Now, please click back again and go to master.

# Create your first deployment

`kubectl create deployment --image=nginx cpd`

Please keep an eye in the previous terminal to see what the outcome of your previous command.

Do you understand everything?

# Kill your pod

Use `kubectl delete pod` to delete the pod.

We will observe how the previous pod is killed but there is a new one. This is, as you have probably guessed, because of the replication controllers stuff, in our case, the _ReplicaSet_ controller.

Is the new pod using the same IP? Why?
Where the pod has been scheduled?
