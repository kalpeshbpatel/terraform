### Create an AWS VPC Module Using Terraform

#### Objective:

Develop a Terraform code live during the interview that sets up an AWS VPC with both public and private subnets, deploys an EC2 instance in the private subnet, and enables internet access for the instance via a NAT Gateway.

#### Step-by-Step Task:

1. **VPC Configuration:**

   - Define a VPC with a CIDR block, for example, `192.168.0.0/16`.
   - Create one public and one private subnet, each in different availability zones.

2. **Required AWS Resources:**

   - **Internet Gateway:** Attach to the VPC to allow public subnet internet access.
   - **NAT Gateway:** Deploy in the public subnet to enable internet access for instances in the private subnet.
   - **Route Tables:**
     - Public Route Table: Includes a route to the Internet Gateway.
     - Private Route Table: Includes a route to the NAT Gateway.

3. **Security Groups:**

   - Define a security group for the EC2 instance that allows:
     - Outbound traffic to all destinations.

4. **EC2 Instance in Private Subnet:**

   - Launch an EC2 instance in the private subnet using a public AMI (e.g., Amazon Linux 2).

5. **Outputs:**
   - Print VPC ID, public subnet IDs, private subnet IDs, and EC2 instance ID.

#### Implementation:

- During the interview, write the Terraform code live:
  - Start with the VPC and subnets (`vpc.tf`).
  - Add the Internet Gateway and NAT Gateway (`network.tf`).
  - Set up the route tables and associations (`routes.tf`).
  - Configure security groups (`security_groups.tf`).
  - Create and configure the EC2 instance (`ec2.tf`).
- Use Terraform commands to validate the configuration (`terraform init`, `terraform plan`).

#### Key Points to Discuss During the Interview:

- **Module Structure:** Emphasize the importance of modular code for reusability.
- **Security Best Practices:** Limit SSH access and discuss potential alternatives for secure access (e.g., VPN, Bastion host).
- **High Availability Considerations:** Discuss the benefits of placing resources in multiple availability zones.

#### Interview Guidance:

- Focus on showing understanding of Terraform basics, resource dependencies, and AWS networking concepts.
- Clearly articulate each step as you write the code.
- Ensure you explain the reasoning behind each resource and configuration.
- During the interview, refer to Terraform's official documentation https://registry.terraform.io/providers/hashicorp/aws/latest/docs
