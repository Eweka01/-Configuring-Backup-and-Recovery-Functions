# Configuring Backup and Recovery Functions

**Author**: Osamudiamen Eweka  
**Course**: CYB-605-Z2 Principles of Cybersecurity  
**Institution**: Utica University

## Overview

This lab provides hands-on experience in configuring essential backup and recovery functions to ensure business continuity and disaster recovery within an IT infrastructure. The lab covers System State backups using Windows Server Backup, Network File System (NFS) configuration for high availability, and load balancing with pfSense. These tasks emphasize the importance of proactive planning and execution to safeguard business processes against disruptions.

## Objectives

- Understand the processes involved in business continuity planning, disaster recovery planning, and high availability.
- Install and configure Windows Server Backup to perform System State backups.
- Restore a Domain Controller from a System State backup.
- Set up a Network File System (NFS) for shared data access across redundant web servers.
- Configure load balancing using pfSense to ensure high availability and scalability for web services.

## Lab Setup

### Lab Environment Details

The lab setup includes the following tools and software:

- **Windows Server Backup**: A built-in utility for backing up and restoring Windows servers.
- **Wbadmin**: A command-line tool for managing Windows backups and recoveries.
- **NFS (Network File System)**: A protocol that allows for shared file access over a network.
- **Vi Editor**: A text editor for Unix and Linux systems used to edit configuration files.
- **pfSense**: An open-source firewall and router software, used here for load balancing across web servers.

## Hands-On Demonstrations

### 1. Install Windows Server Backup
Participants installed the Windows Server Backup feature on a Windows 2019 Server using the Server Manager. This tool is essential for performing backups and enables the administrator to designate backup locations and manage backup operations.

### 2. Configure a System State Backup
Using the Windows Backup Admin (wbadmin) console, participants configured a daily System State backup for the DomainController01 server. This involved scheduling the backup to run at 2:00 AM and designating a dedicated disk for storing the backups, ensuring data availability in case of system failure.

### 3. Restore from a System State Backup
Participants practiced restoring the DomainController01 server from an existing System State backup. This exercise involved booting the server into safe mode, preparing for Directory Services Restore Mode (DSRM), and navigating the Windows Server Backup console to initiate the recovery process.

### 4. Configure an NFS Share
Participants set up an NFS share on a dedicated storage server and configured two web servers to access this shared directory. This setup ensured high availability and redundancy for web services by allowing both servers to serve the same content.

### 5. Configure Load Balancing
Using pfSense and HAProxy, participants configured load balancing across two redundant web servers. The setup distributed incoming HTTP traffic evenly between the servers, ensuring consistent service availability and performance.

## Challenge and Analysis

### 1. Add Failover Functionality
Participants implemented health checks on the load-balanced web servers to ensure that only operational servers receive traffic. This setup added fault tolerance to the web service infrastructure by allowing the load balancer to automatically reroute traffic if a server became unresponsive.

### 2. Validate Failover Functionality
By simulating a server failure, participants tested the effectiveness of the configured health checks. The lab verified that the load balancer redirected traffic to the remaining healthy server, ensuring uninterrupted service for end-users.

## Conclusion

This lab provided a comprehensive understanding of configuring backup and recovery functions critical for maintaining business continuity and disaster recovery. Participants gained practical skills in setting up System State backups, configuring NFS shares for high availability, and using pfSense for load balancing. These exercises highlight the importance of proactive planning to ensure business resilience and system availability in the face of disruptions.

## References

- Load Balancer Metrics. (n.d.). *Oracle Cloud Infrastructure Documentation*. https://docs.oracle.com/en-us/iaas/Content/Balance/Reference/loadbalancermetrics.htm
- Jones & Bartlett (2024). *Implementing Security Monitoring and Logging (Figures)*. Jones and Bartlett Learning Virtual Lab. URL: https://jbl-lti.hatsize.com/startlab

For a complete list of references, please refer to the full lab report.
