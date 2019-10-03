## Let's run some commands

Run: `curl https://localhost:6443/version -k`

Run: `curl https://localhost:6443 -k`

We should see some _forbidden_ stuff. Why?

Because we already know that kubectl works fine, let's try to use it as a proxy..

Run: `kubectl proxy &`

And now run the above commands.

Run: `curl http://localhost:8001 -k`

## Inspect the kubeconfig

Run: `kubectl config view`