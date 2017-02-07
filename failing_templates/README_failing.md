### These templates don't work. They fail in the validation.

I just put them here to show what doesn't work.
The template cloudformation_ip_dependency.yaml fails with:

> Template validation error: Circular dependency between resources: [minielkESEC2Instance]

The template cloudformation_instancetype_dependency.yaml fails with:

> Template validation error: Template format error: Unresolved resource dependencies [ESMemory, Instance::InstanceType] in the Resources block of the template

This makes some sense. You try to access the IP and the instance type (or the memory) while creating the instance - so it doesn't have this information yet. But then again, once you run commands on a server, there clearly _is_ a server with IP and RAM and instance type. I decided to hide things in a script, and it worked: cloudformation_es5node.yaml

The validation seems to be too strict.

