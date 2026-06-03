# Esports Player Analytics System for Team Management Decisions

This repository contains the complete source code, system configurations, and automation scripts for the **Esports Player Analytics System**. The project is built to demonstrate a robust, scalable, and automated 3-tier cloud architecture tailored to optimize pro-player evaluation and roster management decisions.

## 🚀 System Architecture (3-Tier Multi-Node VM)
In compliance with the project guidelines, the infrastructure is distributed across **3 separate Virtual Machines (VMs)** to ensure operational isolation, modularity, and scalability:

1. **Frontend Server (VM 1)**
   * **Role:** Serves the client-facing user interface.
   * **Tech Stack:** [Fill in e.g., React.js / Vue.js / HTML5 Boilerplate]
   * **Function:** Provides interactive dashboards for team managers to view player metrics, performance charts, and analysis reports.

2. **Backend API Server (VM 2)**
   * **Role:** Handles the core business logic and system routing.
   * **Tech Stack:** [Fill in e.g., Node.js / Python Fast-API / Express]
   * **Function:** Processes player telemetry data, handles algorithmic decision-making metrics, and exposes RESTful API endpoints to the frontend.

3. **Database Server (VM 3)**
   * **Role:** Manages secure, data retention.
   * **Tech Stack:** [Fill in e.g., PostgreSQL / MySQL]
   * **Function:** Provides **Persistent Storage** to securely retain historical match statistics, player profiles, and team logs even after machine recycles.

---

## 🛠️ Infrastructure & Automation Tools
To maintain a **consistent** deployment environment and eliminate manual overhead, this project leverages modern Cloud-Enabling Technologies:
* **Vagrant & VirtualBox:** Orchestrates the multi-node VM lifecycle automatically using a unified `Vagrantfile`.
* **Ansible (Infrastructure as Code):** Handles agentless configuration management, ensuring the server dependencies, firewall ports, and system packages are identical upon execution.
