## Scale up again

Instead of modifying the yaml file, we can scale up our deployment manually:

Run: `kubectl scale deployment cpd --replicas=5`

## Rolling back

Now, let's play with the roll back options.

Run: `kubectl rollout history deployment cpd`

Run: `kubectl rollout undo deployment cpd` (it goes to the previous revision)

Run: `kubectl rollout undo deployment cpd --to-revision=2`

## Resume y pause

Some times we should create hundreds of pods, then we may use _resume_ and _pause_ 

`kubectl rollout pause deployment cpd`

`kubectl describe deploy cpd | less` (Check _OldReplicaSets_ and _NewReplicaSets_)

## What can I do if I need to restart all pods?

Before v1.15 there was no elegant option to do this. But now, we have the following command:

Run: `kubectl rollout restart deployment cpd`

It would be very useful for restart your deployment so that the pods can pick up changes from Secrets and Configmaps, for example.

# Finally...

Let's try to update the image to a non-existing image:

Run: `kubectl set image deploy cpd nginx=non-exist:1.0.0`

There is no observable difference in Pod status between a missing image and incorrect registry permissions...