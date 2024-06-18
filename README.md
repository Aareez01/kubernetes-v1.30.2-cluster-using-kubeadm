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

### Step 2: Enable IPv4 Packet Forwarding

# sysctl params required by setup, params persist across reboots
```bash
cat <<EOF | sudo tee /etc/sysctl.d/k8s.conf
net.ipv4.ip_forward = 1
EOF

# Apply sysctl params without reboot
sudo sysctl --system
