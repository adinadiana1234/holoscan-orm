
# Deploy NVIDIA Holoscan on Oracle Linux A10 Instance

This Oracle Cloud Infrastructure (OCI) Terraform stack deploys an A10 (VM.GPU.A10.1) instance running Oracle Linux and installs NVIDIA Holoscan in an existing Virtual Cloud Network (VCN). The deployment also installs the required dependencies and configures Docker and NVIDIA runtimes.

## Prerequisites

1. **OCI Account**: Ensure you have an active Oracle Cloud Infrastructure account.
2. **NVIDIA NGC API Key**: You need a valid NVIDIA NGC Catalog API key to complete the deployment.
3. **SSH Key Pair**: Generate an SSH key pair to access the deployed instance.

## Resource Configuration


### Required Configuration

The following variables are visible and need to be configured in the deployment UI:

- **Compartment OCID**: Choose the compartment where you want to deploy the GPU VM.
- **VCN ID**: Select the VCN (Virtual Cloud Network) where the resources will be deployed.
- **Subnet ID**: Select the subnet within the VCN for resource deployment.
- **VM Display Name**: Set a display name for the VM instance.
- **SSH Public Key**: Upload your public SSH key for accessing the compute instance.
- **Availability Domain**: Choose the availability domain for the instance.
- **NVIDIA API Key**: Enter your NVIDIA API key.

### Variables

The following variables are defined for the stack:

- `compartment_ocid`: OCID of the compartment where the resources will be deployed.
- `vcn_id`: OCID of the VCN.
- `subnet_id`: OCID of the subnet.
- `vm_display_name`: Display name for the VM.
- `ssh_public_key`: Your public SSH key.
- `ad`: Name of the availability domain.
- `nvidia_api_key`: NVIDIA Holoscan API key.

## CloudInit Script

The provided `cloudinit.sh` script automates the installation and configuration of essential tools, including Docker and the NVIDIA container toolkit. It also pulls the Holoscan container image and starts a Jupyter Notebook service. Firewall rules are configured to allow access to port 8888 for Jupyter.

## Use the below button to deploy this directly to OCI

[![Deploy to Oracle Cloud](https://oci-resourcemanager-plugin.plugins.oci.oraclecloud.com/latest/deploy-to-oracle-cloud.svg)](https://cloud.oracle.com/resourcemanager/stacks/create?zipUrl=https://github.com/adinadiana1234/holoscan-orm/archive/refs/heads/main.zip)