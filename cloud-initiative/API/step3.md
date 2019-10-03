## Inspect kube-apiserver auth

Run: `cat /etc/kubernetes/manifests/kube-apiserver.yaml`

and search (grep?) by _--authorization-mode_

## Certificates

Please notice that everything in Kubernetes is secured by certificates.

Just have a look to this path _/etc/kubernetes/pki_

## Let's check our permissions

When creating k8s objects you might face some permissions issues.

Kubernetes provides a quick way to check this:

Run: `kubectl auth can-i create deployments`

