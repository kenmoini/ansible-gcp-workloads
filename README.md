# Ansible GCP Workloads

This Ansible Collection deploys a set of workloads to Google Cloud.  The following workloads are supported:

- VPC Networks and Subnets
- Linux VMs
- Windows VMs
- GKE Clusters
- OpenShift Clusters

## Prerequisites

- Ansible Automation Platform 2, Controller

You can run this with ansible-playbook via the command line but that's on you:

```bash
python3 -m pip install --upgrade -r requirements.txt
ansible-galaxy collection install -r collections/requirements.yml

export GCP_SERVICE_ACCOUNT_FILE=~/.config/gcloud/creds.json
export GCP_AUTH_KIND="serviceaccount"

ansible-playbook -i inventory -e "@my-vars.yml" create.yml
ansible-playbook -i inventory -e "@my-vars.yml" delete.yml
```

## Getting Started

1. Create an **Inventory** that uses a Localhost Host for the execution of the EE
2. Create a **Credential** in Ansible Controller, Google Cloud type.
3. Make a **Project**, point to this repo or your fork of it
4. Create a set of **Templates** that point to the `create.yml` playbook as well as the `destroy.yml` playbooks.
