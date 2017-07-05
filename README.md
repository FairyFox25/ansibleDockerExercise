This Ansible script will setup and configure a single Amazon EC2 instance with Docker, wordpress, ansible, and apache. 
It will then make a post on the blog with the current Chicago weather 

It can be run by moving into the ansible folder and running "ansible-playbook site.yml". 
It allows you to configure multiple things by adding in extra variables to the end of the run command using:
    --extra-vars "<variable to set>=<Value to use>" 

Configurable variables:       name:            default: 

   Wordpress url:             wp_siteurl_var   InstancePublicDNS/wordpress
   Ci directory of the vpc:   cidir_vpc        172.40.0.0  (Only needed if no vpc id is provided )
   Aws region:                aws_region       us-east-2
   Aws image:                 aws_image        ami-3883a55d  (Amazon Linux)
   Name of instance:          image_name       WordpressServer
   Type of aws instance:      aws_instance     t2.micro    (Free Tier)
   Premade vpc id:            aws_vpc_id       (None. creates one programatically)
   Subnet id:                 aws_subnet_id    (None. creates one programatically)

If no vpc id is provided, the script will create a new vpc for the Ec2 instance to run on. Likewise, if no subnet id is provided, it will create one on the vpc. 

The entire stack, including the script created vpc, can be torn down by running "ansible-playbook terminate.yml"

Right now I am using the AWS access keys as environment variables for my system instead of in an encrypted file on github. 
