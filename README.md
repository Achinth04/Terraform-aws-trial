
# Terraform-AWS-Trial 
This project was done only to  experiment and get a initial feel for Terraform and AWS service interaction. 

This project demonstrates how to provision and deploy a Flask-based echo chatbot service using **Terraform** and **AWS** infrastructure components, including:

- A custom **VPC** with public subnets
- **EC2** instance with Flask API running on port 80
- **Application Load Balancer (ALB)** for routing traffic
- **Security Groups**, IAM Roles, and Internet Gateway setup

---

## 🌟 Why This Matters

DevOps and SRE roles demand hands-on understanding of infrastructure-as-code (IaC), scalability, and deployment pipelines. This project showcases:

- How to use **Terraform to declaratively build cloud infrastructure**
- How to **expose a Python Flask app via a public Load Balancer**
- The foundational skills used in **CI/CD and infrastructure automation**
- Practical exposure to **networking**, **IAM**, and **high availability**

---

## 🧰 Stack

- **Terraform**
- **AWS EC2**
- **Flask (Python)**
- **AWS Application Load Balancer**
- **IAM, VPC, Subnets, Security Groups**

---

## 🔧 Setup Instructions

### 1. 🔑 Prerequisites

- [Terraform](https://www.terraform.io/downloads) installed
- AWS CLI configured (`aws configure`)
- A valid EC2 Key Pair (update the `key_name` in `main.tf`)
- Git & terminal/CLI access

---

### 2. 🛠 Clone and Deploy Infrastructure


```bash
git clone https://github.com/Achinth04/Terraform-aws-trial.git
cd Terraform-aws-trial
terraform init
terraform apply
```
Hit yes when prompted to approve resource creation.

### 3. Test the Deployed Chatbot
Use the Load Balancer DNS output from Terraform and run a curl command with headers and json req

### 4. Destroy when done
```bash
terraform destroy
```

## Challenges Faced
Here are some real-world issues I faced while building this, and what I learned from them:

# -SSH & Key Management
-Problem: .ppk and .pem key confusion when accessing EC2 from Windows.

-Fix: Used PuTTYgen to convert keys and used chmod 400 for proper permissions.

# -Networking Misconfiguration
Problem: Load Balancer failed due to subnet/zone errors.

Fix: Created public subnets in two separate Availability Zones for ALB.
#  -Port Inaccessibility
Problem: NGINX/Flask wasn’t publicly visible.
Fix: Allowed inbound traffic on port 80 via Security Groups.wrote rule set to enable.

#  Curl Debugging
Problem: Bad request errors due to incorrect header formatting.

Fix: Escaped double quotes and ensured proper Content-Type












Tools



ChatGPT can make
