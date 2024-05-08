
---

# Ansible Elastic Load Balancer Automation

This Ansible playbook automates the configuration of Elastic Load Balancers (ELBs) on AWS.

## Prerequisites

Before running this playbook, ensure that you have the following prerequisites:

- Ansible installed on your local machine or control node.
- AWS credentials configured either through environment variables, AWS CLI, or IAM roles.

## Usage

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/ansible-elb-automation.git
```

### 2. Create Inventory Folder (depends on the OS, Linux example below)

If your playbook targets remote hosts, create a folder named `inventory` in the project root to store the inventory file.

```bash
mkdir inventory
```

### 3. Create Inventory File

Within the `inventory` folder, create a file named `hosts` and specify the target hosts or groups.

```ini
[elb]
your-elb-hostname
```

Replace `your-elb-hostname` with the DNS name or IP address of your Elastic Load Balancer.

### 4. Run the Playbook

Execute the Ansible playbook to configure the ELB:

```bash
ansible-playbook -i inventory/hosts playbooks/elb_configuration.yml
```

### 5. Verify Configuration

After running the playbook, verify that the Elastic Load Balancer is configured correctly by accessing it through its DNS name or IP address.

## Playbook Details

The `elb_configuration.yml` playbook performs the following tasks:

1. **Create Target Group:** Creates a target group for routing requests to registered instances.
2. **Create Load Balancer:** Creates an Elastic Load Balancer with specified listeners and subnets.
3. **Register Instances:** Registers EC2 instances with the target group for load balancing.
4. **Configure Health Check:** Configures health checks for monitoring the health of registered instances.

