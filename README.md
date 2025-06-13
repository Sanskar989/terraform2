# Terraform HTTP Server Deployment

A beginner-friendly Terraform project that provisions:

- VPC
- Public Subnet
- Internet Gateway
- Route Table
- Security Group (HTTP only)
- EC2 instance running Apache to serve a custom HTML page.

---

## Architecture Diagram

![ChatGPT Image Jun 13, 2025, 09_35_32 AM](https://github.com/user-attachments/assets/0400e8ac-15a6-4ffb-a4f0-d3a24413bb8f)
![ChatGPT Image Jun 13, 2025, 09_34_20 AM](https://github.com/user-attachments/assets/f87c6f32-6872-4e1c-9fc3-c85c0b0390d2)



---

## Prerequisites

- Terraform v1.0+
- AWS CLI configured with valid credentials
- AWS account with necessary permissions

---

## Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/<username>/<repo>.git
   cd <repo>
   ```
   ```
2. **Configure variables** in `terraform.tfvars`:
   ```hcl
   aws_region        = "ap-south-1"
   ssh_allowed_cidr  = "your-ip/32"
   public_key_path   = "id_rsa.pub"
   instance_type     = "t2.micro"
   user_data_message = "Hello World from terraform deploy"
   ```
3. **Initialize and apply** Terraform:
   ```bash
   terraform init
   terraform plan
   terraform apply
   ```
4. **Retrieve outputs**:
   ```bash
   web_public_ip  = ...
   web_public_dns = ...
   ```
5. **Visit the server** in your browser:
   ```
   http://<web_public_ip>
   ```

---

## Variables

| Name                     | Description                            | Default             |
|--------------------------|----------------------------------------|---------------------|
| `aws_region`             | AWS region to deploy into              | `ap-south-1`        |
| `vpc_cidr`               | CIDR block for the VPC                 | `10.0.0.0/16`       |
| `public_subnet_cidr`     | CIDR block for the public subnet       | `10.0.1.0/24`       |
| `availability_zone_suffix` | AZ suffix (e.g. `a` for ap-south-1a) | `a`                 |
| `ssh_allowed_cidr`       | CIDR block allowed to SSH              | *required*          |
| `public_key_path`        | Path to SSH public key                 | `id_rsa.pub`        |
| `instance_type`          | EC2 instance type                      | `t2.micro`          |
| `user_data_message`      | Text to serve on homepage              | `"Hello World..."` |

---

## Screenshots

---

## License
![Screenshot 2025-06-13 012113](https://github.com/user-attachments/assets/763b47ee-672d-4e8e-afca-4c21385947df)
![Screenshot 2025-06-13 012148](https://github.com/user-attachments/assets/094dbb66-e1ae-4edb-843b-c99603135208)
![Screenshot 2025-06-13 012157](https://github.com/user-attachments/assets/d202b29f-f251-48e5-ae95-f3751a99ce82)
![Screenshot 2025-06-13 012228](https://github.com/user-attachments/assets/6d2f31d7-2aa5-4da7-b2e1-a5cf3bc7cda5)
![Screenshot 2025-06-13 012253](https://github.com/user-attachments/assets/0f63dc0e-812b-4d6e-b308-262cbefa7d20)
![Screenshot 2025-06-13 012302](https://github.com/user-attachments/assets/151f0003-77a7-4058-8722-f33d183de890)
![Screenshot 2025-06-13 012311](https://github.com/user-attachments/assets/8b03ccf3-66e3-43c3-a428-b16ccda99846)
![Screenshot 2025-06-13 012354](https://github.com/user-attachments/assets/f4a41e42-5046-423a-8937-afa970b6778d)
![Screenshot 2025-06-13 013128](https://github.com/user-attachments/assets/6a76cb03-da4a-4554-aa9a-2754d20a543c)

