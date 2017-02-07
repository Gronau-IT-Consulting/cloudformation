# cloudformation
Cloudformation for Kickstarting &amp; Bootstrapping AWS Stacks

### cloudformation_es5node.yaml 

is a basic cloudformation template to create one stand alone elasticsearch 5 EC2 instance, listening on the public IP, which is given in the output section. 

It is a basic thing, only for one region, three instance types, and only for Amazon Linux. It won’t work for other Linuxes. It's 9200 port is open to the world, it's not a cluster, and has no input, no nice frontend and no backup. The template also won’t work if the elasticsearch repo is temporarily unreachable and a host of other situations. But does pass the template validation, and it did produce an instance with a functioning elasticsearch node a couple of times.


