Now...

# Describe an object

Run `kubectl describe pod nginx` and spend some time reading the output.

By the way, there are many fields... give them a try.

Now, please focus on the lates at the end, the **events**, you will see there what happened before.

Get the list of pods and check the Restart column.

# Editing kubernetes objects

Run this command:

`kubectl edit pod nginx`

a VI editor will be opened with the Pod definition in YAML format.

Please, roll back the image version to the previous one.

Save changes and exit your text editor.

What happened? Do you understand why?









