<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Create S3 Buckets with Terraform

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-terraform1)

**Author:** Melvin J Bonner  
**Email:** melvinj.bonner@gmail.com

---

![Image](http://learn.nextwork.org/zealous_maroon_serene_raspberry/uploads/aws-devops-terraform1_9i0j1k2l)

---

## Introducing Today's Project!

In this project, I will demonstrate how to use Terraform to automate the deployment of an S3 bucket. The goal is to become more familiar with Terraform.  

### Tools and concepts

Services I used were Terraform and Amazon S3. Key concepts I learned include infrastructure as code, resource blocks, Terraform configuration, terraform apply, and terraform init. 

### Project reflection

This project took me approximately 2 hours. The most challenging part was getting Terraform installed on my computer. It was most rewarding when the image appeared in my S3 bucket.  

I did this project today to get some exposure to Terraform and get a better understanding of how it works. This project met my goals.  

---

## Introducing Terraform

Terraform is a tool that helps you build and manage your cloud infrastructure using code.

Terraform is one of the most popular tools used for infrastructure as code (IaC), which is a way to manage your IT infrastructure. Instead of manually setting up your resources one by one in the console, you're writing configuration files in code.

Terraform uses configuration files to  to define and manage infrastructure; main.tf is is a central file in a Terraform project. It's where you write down what you want your infrastructure to look like, using Terraform's language

![Image](http://learn.nextwork.org/zealous_maroon_serene_raspberry/uploads/aws-devops-terraform1_9i0j1k2l)

---

## Configuration files

The configuration is structured in blocks. The advantage of doing this is help to organize the code better. Each block handles a specific piece of your setup, like a resource or a configuration, which makes it easier to read, manage, and adjust things separately without affecting the rest of your infrastructure.

### My main.tf configuration has three blocks

The first block indicates that AWS is the provider.  The second block provisions an S3 bucket. The third block manages the public access policies for the S3 bucket.  

![Image](http://learn.nextwork.org/zealous_maroon_serene_raspberry/uploads/aws-devops-terraform1_ljvh9876)

---

## Customizing my S3 Bucket

For my project extension, I visited the official Terraform documentation to find setup instructions, descriptions of each available resource, best practice tips and examples, and parameters for customization. The documentation shows how to use Terraform to create and manage AWS S3 buckets. It covers how to configure these buckets, set their properties, and manage interactions with other AWS services.

I chose to customize my bucket by adding a Dev tag. With a Dev tag, S3 only allows the Dev to access those resources.  When I launch my bucket, I can verify my customization by checking both the AWS Console and Terraform outputs or state.

![Image](http://learn.nextwork.org/zealous_maroon_serene_raspberry/uploads/aws-devops-terraform1_ffe757cd3)

---

## Terraform commands

I ran terraform init to set up my project by initializing the backend, initialize the provider pluging, find the latest version of hashicorp, and create a lock file.

Next, I ran terraform plan to create an execution plan, showing what changes Terraform will make to the infrastructure on my configuration files.

![Image](http://learn.nextwork.org/zealous_maroon_serene_raspberry/uploads/aws-devops-terraform1_3g4h5i6j)

---

## AWS CLI and Access Keys

---

## Lanching the S3 Bucket

I ran terraform apply to apply the changes written in my Terraform configuration. Running terraform apply will affect my AWS account by adding the S3 bucket in my account.

The sequence of running terraform init, plan, and apply is crucial because I would have run into an error if not done in that order. Terraform init needed to be run first because it set my project up by downloading the necessary plugins and setting up the state line.  

![Image](http://learn.nextwork.org/zealous_maroon_serene_raspberry/uploads/aws-devops-terraform1_1q2w3e4r)

---

## Uploading an S3 Object

I created a new resource block to import an image to the S3 bucket.  

We need to run terraform apply again because anytime you change Terraform configuration you have to run terraform apply. This will make sure the changes are correctly applied to your infrastructure.

To validate that I've updated my configuration successfully, I downloaded the image and compared it to the uploaded image.  

![Image](http://learn.nextwork.org/zealous_maroon_serene_raspberry/uploads/aws-devops-terraform1_9o0p1a2s)

---
