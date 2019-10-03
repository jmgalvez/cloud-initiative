Let's create some pods

# Create a pod interactively

Just create and run a particular image. As you can see, we are not using any definition file.

`kubectl run --generator=run-pod/v1 nginx --image=nginx`

# Verify

Get the list of pods: `kubectl get pods`

Check the status column. Depends on your type speed, you might see different statuses: _ContainerCreating_ or _Running_ or a different one _Pending_

READY column indicates the number of containers.

```
NAME    READY   STATUS              RESTARTS   AGE
ngnix   0/1     ContainerCreating   0          3s
```

Use some flags:

- wide
- json

Please write the IP down.

# Create a pod manually

Now, let's do it in a different way.

`kubectl run --generator=run-pod/v1 nginx --image=nginx --dry-run -o yaml`

You will see the yaml definition for a pod in kubernetes.

Please create a file called `pod1.yaml` with the content of that output using a redirection pipe (>)

Now, we can use a text editor to modify the **PodSpec**  (**nano** or **vi** are available)


# Get a shell to a running container

Now, let's go into the pod, this is indeed quite similar to Docker, right?

`kubectl exec nginx -it bash`

and run the following command:

`nginx -v`

Please remember the ngnix version.

Type: `exit` to return to the node.

# Check app

Type `curl <IP>` (Pod IP) 

The app (nginx) is deployed and it is accesible, but, remember it is only visible inside the cluster. No external access.

# Modify the Pod specification

Open `pod1.yaml` into your text editor and replace/modify this line:

```
image: nginx
```

with this one:

```
image: nginx:1.7.9
```

Please remove line _creationTimestamp: null_

Please save the file with the changes and exit the text editor.

Now, try to create a new pod with this command:

`kubectl create -f pod1.yaml`

An error is expected here.

Now, try with this one:

`kubectl apply -f pod1.yaml`

Please get a shell into the new POD and check the nginx version. Compare both.

What's the difference?






