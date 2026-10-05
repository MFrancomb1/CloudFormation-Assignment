# CloudFormation IaC Assignment
This repository contains `corpweb.json`, an AWS CloudFormation template that creates two Amazon Linux 2023 web servers behind an Application Load Balancer.

## Verification

The template was validated using the AWS CLI:

`aws cloudformation validate-template --template-body file://corpweb.json --region us-east-1`

The stack was deployed as `WebserversDev` and reached `CREATE_COMPLETE`.

Both EC2 instances reported healthy in the load balancer target group. The `WebUrl` output was opened in a browser and refreshing the page confirmed that requests were distributed between the two web servers.

SSH access to an EC2 instance was also tested successfully. The instance was verified to be running Amazon Linux 2023, Apache was running, and `index.php` was present in `/var/www/html`.
