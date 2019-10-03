In Katacoda the environment takes some time to be ready..

Usually, it takes some seconds....so please be patient...

# Main client

When working with K8s, your **main client tool** should be **kubectl**. This is coming directly from the kubernetes guys and it is part of the kubernetes environment.

**kubectl** uses REST API calls to the kubernetes master.

Notes:
- In this environment there is an alias for kubectl which is **k**. You may run the alias command right now.
- Remember, TAB is your friend. If you have some problems, this might help you.
  - `source <(kubectl completion bash)`
- TAB will not work with the alias but with the kubectl command. 
  - `complete -F __start_kubectl k`