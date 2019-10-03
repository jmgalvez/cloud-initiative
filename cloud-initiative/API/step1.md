Let's verify that the cluster is up and running...

Usually, it takes some seconds....so please be patient...

## Kubectl

In your current directory (/root), go to `.kube` folder and identify a file called *config*

Now, inspect the content of the file with `cat config` 

And now...

Run: `grep 'client-certificate-data' $HOME/.kube/config |  awk '{print $2}' | base64 -d | openssl x509 -text`{{execute}}


Then, please rename the file with the following command: `mv config old_config`

Try to run a kubectl command. What's happening?

Run: `mv old_config config` to restore access.

