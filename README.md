# aws-wordpress-deployment

Automate the setup of WordPress on AWS with this Bash script designed for Amazon Linux instances.

## Overview

This project provides a Bash script for deploying a WordPress website on Amazon Web Services (AWS) quickly. It streamlines the creation of necessary resources like EC2 instances, VPC, subnet, and database setup, simplifying the process for users.

## Prerequisites

- An AWS account with appropriate permissions.
- AWS CLI configured on your local machine.
- Basic knowledge of AWS services and WordPress.
- IAM Permissions: Ensure that your AWS account has the necessary IAM (Identity and Access Management) permissions to create and manage resources such as EC2 instances, RDS databases, and VPC configurations. At a minimum, you'll need permissions to create IAM roles, manage security groups, and configure network settings.
- Virtual Private Cloud (VPC): Set up a VPC in your AWS account if you haven't already done so. 
- Subnets: Define one or more subnets within your VPC.

Step 1: Create Stack
  - Log in to the AWS console (IAM) and navigate to the CloudFormation.
  - Please ensure you have selected North Virginia as the region in the top right.
  - Create Stack name

![1w](https://github.com/TarangJ/aws-wordpress-deployment/assets/65700353/e12fffc9-1ef8-4fa4-a962-657b56b999b8)

Step 2: AWS IAM Role
 
 - Check the Acknowledge Cloudformation might create IAM Resources.
 - Click create stack

![2w](https://github.com/TarangJ/aws-wordpress-deployment/assets/65700353/23dd2872-a78f-4594-840b-c346d3bd751b)


Step 3: Create Stack Stage
 
 - Wait for create comlete stage.

Step 4: Launch an Instance
  
  - Go to services and click EC2.
  - Now, create and EC2 instance

![3](https://github.com/TarangJ/aws-wordpress-deployment/assets/65700353/9483ef27-6239-49a8-bd19-c7f80e40d074)

3. Choose your VPC and subnet,The VPC will provide the networking infrastructure for your WordPress deployment and allow you to control access to your resources.
    Subnets are required for deploying EC2 instances and other resources in different availability zones for high availability and fault tolerance.
![4](https://github.com/TarangJ/aws-wordpress-deployment/assets/65700353/376b7620-8a47-4ae9-8650-0f6ff5d6793c)

4. Download or copy wordpress_setup.sh from this repo.
   Add Bash script designed for setting up a WordPress installation on an Amazon Linux server
   - Setting up Database Variables: Defines variables for the WordPress database name, username, and passwords.
   - Installing System Software: Uses dnf to install necessary software packages like Apache (httpd), PHP, MariaDB (MySQL), and some PHP extensions.
   - Starting Web and DB Servers: Enables and starts the Apache and MariaDB services.
   - Setting MariaDB Root Password: Uses mysqladmin to set the root password for MariaDB.
   - Downloading and Installing WordPress: Downloads the latest version of WordPress, extracts it, and moves the files to the web server's document root (/var/www/html).
   - Configuring WordPress: Copies the sample WordPress configuration file, modifies it to include the database name, username, and password.
   - Setting Permissions and Creating Database: Adjusts file permissions for the web server user (ec2-user and group apache) and creates the WordPress database, user, and    grants necessary privileges.
   - Adding Cowsay to Message of the Day (MOTD): Adds a humorous message using cowsay to the system's Message of the Day (/etc/update-motd.d/40-cow) to be displayed upon login.

![6](https://github.com/TarangJ/aws-wordpress-deployment/assets/65700353/378d6366-a8bc-4281-a02f-0ab4150c2aea)

5. Click Launch instance.

   -Wait for 2/2 checks
    
![5](https://github.com/TarangJ/aws-wordpress-deployment/assets/65700353/fd1d2d46-e3ea-41be-994f-d3faf7dfe037)

6. Now, right click launched instance and click connect,then choose EC2 instance coonect,it wiil redirect to AMI

![7](https://github.com/TarangJ/aws-wordpress-deployment/assets/65700353/cb2b6449-3852-4696-a93c-74d6e6ee114b)

7. Copy IPv4 address pase on clipboard
    
![9](https://github.com/TarangJ/aws-wordpress-deployment/assets/65700353/d79f576a-8300-43f8-9a1c-9f51f7090611)

![8](https://github.com/TarangJ/aws-wordpress-deployment/assets/65700353/6bd24935-4d4c-457f-bcfd-b92289399f03)

8. Paste copied IPv4 address on new tab,you get automated installed wordpress!

![10](https://github.com/TarangJ/aws-wordpress-deployment/assets/65700353/d8c8988f-5ea2-4391-aa5f-dab8364429d8)




