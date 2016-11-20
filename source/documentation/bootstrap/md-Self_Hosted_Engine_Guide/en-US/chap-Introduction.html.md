# Introduction

A self-hosted engine is a virtualized environment in which the engine, or Manager, runs on a virtual machine on the hosts managed by that engine. The virtual machine is created as part of the host configuration, and the engine is installed and configured in parallel to the host configuration process. The primary benefit of the self-hosted engine is that it requires less hardware to deploy an instance of Red Hat Virtualization as the engine runs as a virtual machine, not on physical hardware. Additionally, the engine is configured to be highly available. If the host running the Manager virtual machine goes into maintenance mode, or fails unexpectedly, the virtual machine will be migrated automatically to another host in the environment. A minimum of two self-hosted engine hosts are required to support the high availability feature.

For the Manager virtual machine installation, a RHV-M Virtual Appliance is provided. Manually installing the Manager virtual machine is not supported. To customize the Manager virtual machine, you can use a custom cloud-init script with the appliance. Creating custom cloud-init scripts is currently outside the scope of this documentation. A default cloud-init script can be generated during the deployment.

**Supported OS versions to Deploy Self-Hosted Engine**

| System Type | Supported Versions |
|-
| Red Hat Enterprise Linux host | 7.2 |
| Red Hat Virtualization Host   | 7.2 |
| HostedEngine-VM (Manager)     | 7   |

For hardware requirements, see [Hypervisor Requirements](https://access.redhat.com/documentation/en/red-hat-virtualization/4.0/single/installation-guide#sect-Hypervisor_Requirements) in the *Installation Guide*.

**Important:** It is important to synchronize the system clocks of the hosts, Manager, and other servers in the environment to avoid potential timing or authentication issues. To do this, configure the Network Time Protocol (NTP) on each system to synchronize with the same NTP server.

The following diagram illustrates the self-hosted engine deployment workflow:

![](images/RHEV-M_Virtual_Appliance_Installation.png)