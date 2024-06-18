# Kubernetes 1.30.2 Cluster Setup on Ubuntu 22.04 LTS

This guide provides step-by-step instructions to set up a Kubernetes 1.30.2 cluster on Ubuntu 22.04 LTS.

## Prerequisites

- Ubuntu 22.04 LTS installed on all nodes.
- Access to the internet.
- User with `sudo` privileges.

## Step-by-Step Installation

### Step 1: Disable Swap on All Nodes

```bash
swapoff -a
sed -i '/ swap / s/^\(.*\)$/#\1/g' /etc/fstab
