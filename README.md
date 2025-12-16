<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Create S3 Buckets with Terraform

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-terraform1)

**Author:** Kwame Ameyaw  
**Email:** kwameameyaw@aol.com

---

![Image](http://learn.nextwork.org/amused_green_smart_grape/uploads/aws-devops-terraform1_9i0j1k2l)

---

## Introducing Today's Project!

In this project, I will demonstrate how to use Terraform to launch an S3 bucket. The goal is to install + set up Terraform, troubleshoot any errors and successfully plan + apply Terraform configurations to launch an S3 bucket.

### Tools and concepts

Services I used were IAM, S3, and AWS CLI. Key concepts I learnt include infrastructure as code and authentication with access keys through AWS CLI.

### Project reflection

This project took me approximately 2 hours. The most challenging part was installing Terraform with Homebrew. It was most rewarding to create and teardown infrastructure in seconds using code instead of doing it manually in the console. 

I chose to do this project today because I wanted to familiarize myself with Terraform. 

---

## Introducing Terraform

Terraform is a popular IaC tool because it supports all major cloud providers, including AWS, Azure, and Google Cloud. 

Terraform is one of the most popular tools used for infrastructure as code (IaC), which is the practice of describing your cloud setup (like your servers, storage, networks) in plain text files instead of clicking through a web console.

Terraform uses configuration files to define and manage infrastructure. main.tf is a central file in a Terraform project. It's where you write down what you want your infrastructure to look like, using Terraform's language.

![Image](http://learn.nextwork.org/amused_green_smart_grape/uploads/aws-devops-terraform1_9i0j1k2l)

---

## Configuration files

The configuration is structured in blocks. By keeping each piece of your infrastructure in its own block, the file stays easy to read, and you can tweak one part without touching the rest of your setup.

### My main.tf configuration has three blocks

The first block (provider block) tells Terraform which cloud to work with, e.g., AWS, Google Cloud, or Azure. The second block (resource block) provisions what to create, such as a storage bucket or virtual machine, and how it should be configured. The third block manages variables, output, data and modules.

![Image](http://learn.nextwork.org/amused_green_smart_grape/uploads/aws-devops-terraform1_ljvh9876)

---

## Customizing my S3 Bucket

For my project extension, I visited the official Terraform documentation to read documentation about Terraform modules and providers. The documentation shows setup instructions, descriptions of each available resource, best practice tips and examples, and parameters for customization.

I chose to customise my bucket by applying a tag to make it easier to identify and organize my resources. 

![Image](http://learn.nextwork.org/amused_green_smart_grape/uploads/aws-devops-terraform1_ffe757cd3)

---

## Terraform commands

I ran 'terraform init' to download necessary plugins, set up the backend, prepare modules, and create a lock file.

Next, I ran 'terraform plan' to show what would be created, updated, or destroyed, so I could review and confirm the configuration before any real changes were made.

![Image](http://learn.nextwork.org/amused_green_smart_grape/uploads/aws-devops-terraform1_3g4h5i6j)

---

## AWS CLI and Access Keys

When I attempted to plan my Terraform configuration, I received an error message stating that no valid credentials were found because Terraform lacked the necessary access credentials to access my AWS account.

To resolve my error, first, I installed AWS CLI, which is a CLI tool that lets you manage your AWS services from your terminal.

I set up AWS access keys to authenticate with AWS through the CLI.

![Image](http://learn.nextwork.org/amused_green_smart_grape/uploads/aws-devops-terraform1_7j8k9l0m)

---

## Lanching the S3 Bucket

I ran 'terraform apply' to apply the configurations to my AWS account. Running 'terraform apply' will affect my AWS account by creating my S3 bucket.

The sequence of running' terraform init', ' plan', and' apply' is crucial because' init' needs to set up your project first by downloading necessary plugins and setting up the state file. There are no errors if you skip the Terraform plan. This is because Terraform apply will automatically run a plan and ask for confirmation before making any changes. But skipping the explicit Terraform plan means you might miss reviewing these changes in detail.

![Image](http://learn.nextwork.org/amused_green_smart_grape/uploads/aws-devops-terraform1_1q2w3e4r)

---

## Uploading an S3 Object

I created a new resource block to store a file in my S3 bucket.

We need to run Terraform apply again because of the changes we made in the code.

To validate that I've updated my configuration successfully, I accessed the S3 bucket from the AWS console to view the contents. 

![Image](http://learn.nextwork.org/amused_green_smart_grape/uploads/aws-devops-terraform1_9o0p1a2s)

---

---
