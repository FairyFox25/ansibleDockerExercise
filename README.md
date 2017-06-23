This Ansible script will setup and configure a single Amazon EC2 instance with Docker, wordpress, ansible, and apache. 
It can be run by moving into the ansible folder and running "ansible-playbook site.yml". 
To configure wordpress with your own url, add --extra-vars "wp_siteurl_var=mysite.com" 
If the url is not provided, then it will automatically run on the Public DNS of the ec2 instance /wordpress. 
Right now I am using the AWS access keys as environment variables for my system instead of in an encrypted file on github. 
