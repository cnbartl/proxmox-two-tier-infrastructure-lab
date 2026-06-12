# proxmox-two-tier-infrastructure--lab
A step-by-step guide to building a self-hosted, multi-tier cloud environment using Proxmox and Windows Server 2022.

## Overview

This project demonstrates how to configure a localized cloud-like environment using a physical machine running Proxmox VE. It was created as a final project for a Cloud Computing course at Whatcom Community College.

The environment uses two virtual machines:

* **Linux Server** — Web/Application Tier
* **Windows Server 2022** — Data Tier

The purpose of this lab was to build a small multi-tier infrastructure environment where a web application that is accessible only from the local network and can securely query a database hosted on a separate Windows Server VM. The application tier handles user access and web requests, while the data tier remains isolated from direct LAN access.

This guide documents the setup process, configuration steps, errors encountered, and the solutions used to resolve them. The final goal was to create a LAN-accessible website that could query a SQL Server database and return results through a simple web interface.

## Security-Oriented Design

This setup follows a security-focused architecture by separating the application and database roles into different network tiers. External LAN communication is allowed only to the application tier, while the data tier is not directly accessible from the LAN. The application tier is permitted to communicate with the data tier over the private network, reducing exposure and following the principle of least privilege.

This design demonstrates basic infrastructure concepts such as virtualization, network segmentation, controlled access, server administration, firewall configuration, and application-to-database connectivity.
