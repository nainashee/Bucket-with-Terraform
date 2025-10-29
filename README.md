<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Create S3 Buckets with Terraform

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-devops-terraform1)

**Author:** Hussain Ashfaque  
**Email:** nain.ashee@gmail.com

---

![Image](http://learn.nextwork.org/confident_teal_noble_watermelon/uploads/aws-devops-terraform1_9i0j1k2l)

---

## Introducing Today's Project!

In this project, I will demonstrate how to use Terraform to deploy an S3 bucket. The goal is to understand the fundamentals of automating infrastructure deployment using Infrastructure as Code (IaC).

### Tools and concepts

In this project, I worked with several AWS and DevOps tools, including the AWS CLI, Terraform, AWS access keys, and Amazon S3 for storage management.

The key concepts I learned include Infrastructure as Code (IaC) using Terraform to configure, deploy, and manage AWS resources efficiently. I also gained experience in version-controlling infrastructure changes, handling updates and resource reconfigurations, and understanding the relationship between AWS IAM security and resource access management.

Overall, this project helped me strengthen my understanding of automation, scalability, and best practices in cloud infrastructure deployment.

### Project reflection

This project took me approximately few hours. The most challenging part was looking for my old access key. 

I chose to do this project today because I wanted to strengthen my hands-on experience with AWS and Terraform — not just follow tutorials but actually build something real. This project helped me connect the dots between Infrastructure as Code, automation, and cloud resource management in a practical way.

Something that would make learning with NextWork even better is adding more real-world use cases and challenges that mimic workplace scenarios, like troubleshooting misconfigurations or optimizing deployments. That kind of hands-on, “learn by breaking and fixing” approach would take the experience to the next level.

---

## Introducing Terraform

Terraform is an infrastructure as code tool that lets you build, change, and version infrastructure safely and efficiently. This includes low-level components like compute instances, storage, and networking; and high-level components like DNS entries and SaaS features.

Infrastructure as Code (IaC) is a method of managing and provisioning infrastructure through machine-readable configuration files instead of manually configuring resources in a graphical interface. It allows you to define, deploy, and manage servers, networks, and other cloud resources using code.

Terraform uses configuration files to define and manage infrastructure. The main.tf file is the central configuration file in a Terraform project — it’s where you describe what resources you want to create, such as S3 buckets, EC2 instances, or VPCs.

In short, main.tf defines what your infrastructure should look like and Terraform uses it to build and manage those resources automatically.

![Image](http://learn.nextwork.org/confident_teal_noble_watermelon/uploads/aws-devops-terraform1_9i0j1k2l)

---

## Configuration files

Terraform configurations are defined using blocks, such as provider, resource, variable, and output. Each block serves a specific purpose and helps organize the code in a clear and modular way.

This modular structure makes the code easier to read, maintain, and update. It also helps prevent accidental changes — if someone edits one section, it won’t affect the rest of the configuration.

### My main.tf configuration has three blocks

The first block defines the cloud provider, which in this case is AWS. It tells Terraform which platform we’re deploying resources to and in which region (us-east-1).

The second block defines the resource we’re creating — an S3 bucket. This block specifies the bucket’s name and tells Terraform to provision it in AWS.

The third block defines another resource that manages the bucket’s public access settings. It ensures that public access is blocked and that the bucket remains secure.

![Image](http://learn.nextwork.org/confident_teal_noble_watermelon/uploads/aws-devops-terraform1_ljvh9876)

---

## Customizing my S3 Bucket

For this project, I explored the official Terraform documentation to better understand how Terraform works with AWS. The documentation explains how to define resources such as S3 buckets, set parameters like region, bucket prefix, and tags, and use additional arguments such as force_destroy.

It also provides examples and best practices that help ensure infrastructure is created securely and efficiently.

I customized my S3 bucket by adding a custom tag under the environment key with the value “Pro”. This tag helps identify the bucket as part of the production environment.

Once the bucket is created, I can verify this customization by checking the tags section in the AWS Management Console.

![Image](http://learn.nextwork.org/confident_teal_noble_watermelon/uploads/aws-devops-terraform1_ffe757cd3)

---

## Terraform commands

I ran terraform init to initialize Terraform. This command sets up the working directory, downloads the required provider plugins (in this case, AWS), and initializes the backend where Terraform stores its state files. It also checks for any module or provider updates and prepares the project for the next steps, such as terraform plan and terraform apply.

Next, I ran terraform plan, which generates a preview of what Terraform will do before making any real changes. It shows what resources will be created, updated, or deleted based on what’s written in the code.

![Image](http://learn.nextwork.org/confident_teal_noble_watermelon/uploads/aws-devops-terraform1_3g4h5i6j)

---

## AWS CLI and Access Keys

When I tried to run terraform plan for my configuration, I received an error saying “no valid credential sources found.” This happened because I hadn’t configured the AWS CLI with my access keys, so Terraform couldn’t authenticate and connect to my AWS resources.

The AWS CLI (Command Line Interface) is a unified tool that allows you to interact with AWS services directly from the command line. It enables you to create, configure, and manage AWS resources using simple commands instead of navigating the AWS Management Console.

I installed the AWS CLI to resolve my error and to allow Terraform and other local tools to authenticate and communicate with my AWS account.

I set up AWS access keys so that my AWS CLI can securely authenticate and access AWS resources. These keys allow the CLI to communicate with my AWS account without needing to log in through the web console.

![Image](http://learn.nextwork.org/confident_teal_noble_watermelon/uploads/aws-devops-terraform1_7j8k9l0m)

---

## Lanching the S3 Bucket

The terraform apply command executes the Terraform plan and provisions the resources defined in the configuration files. It makes real changes to my AWS environment based on what was shown in the plan.

The sequence of runThe sequence of running terraform init, plan, and apply is crucial because each command builds upon the previous one to ensure infrastructure is deployed correctly and safely.

terraform init sets up the working directory by downloading necessary provider plugins and initializing the backend.

terraform plan then evaluates the current state and configuration to create an execution plan, allowing you to preview the changes Terraform will make.

Finally, terraform apply executes the actions proposed in the plan to provision or modify the infrastructure.

Running these commands in the correct order helps prevent errors, ensures consistency, and gives you the opportunity to review changes before they’re applied.ning terraform init, plan, and apply is crucial because...

![Image](http://learn.nextwork.org/confident_teal_noble_watermelon/uploads/aws-devops-terraform1_1q2w3e4r)

---

## Uploading an S3 Object

I created a new resource block to add an image file to the bucket.

We need to run terraform apply again because it will add the new resource for the image file we just uploaded.

To validate that I updated my configuration successfully, I downloaded the image file from the bucket using the AWS Console to verify the upload.

![Image](http://learn.nextwork.org/confident_teal_noble_watermelon/uploads/aws-devops-terraform1_9o0p1a2s)

---

---
