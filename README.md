# Ansible Playbook for Prometheus Exporters Setup
This Ansible playbook automates the installation and setup of Prometheus exporters for monitoring various services such as Node Exporter, Redis Exporter, MySQL Exporter, and NGINX Exporter. These exporters collect valuable metrics from your infrastructure, enabling efficient monitoring and visualization using Prometheus.

🚀 Features
Node Exporter: Gathers system-level metrics such as CPU, memory, disk, and network usage.
Redis Exporter: Exposes Redis instance metrics for Prometheus scraping.
MySQL Exporter: Collects MySQL database performance metrics.
NGINX Exporter: Provides NGINX server performance data.

🔧 Requirements
Ansible 2.9 or higher
A working Linux environment
Services: Redis, MySQL, and NGINX (for Redis, MySQL, and NGINX exporters)

📦 Supported Versions
Node Exporter: 1.8.2
Redis Exporter: v1.45.0
MySQL Exporter: v0.14.0
NGINX Exporter: v1.3.0
🛠 Installation
Clone this repository:

git clone https://github.com/meBerkay/prometheus-exporters-ansible-playbook/
cd prometheus-exporters-setup

Run the playbook:
ansible-playbook -i your_inventory_file setup_exporters.yml
This playbook will:

Install the necessary dependencies (wget, tar).
Download and install each exporter.
Set up systemd services for each exporter.
Ensure the corresponding services (Redis, MySQL, NGINX) are running before installing the exporters.
Open the required firewall ports for each exporter.

⚙️ Configuration
The following variables can be modified in the playbook:

node_exporter_version: Version of Node Exporter to install.

redis_exporter_version: Version of Redis Exporter.

mysql_exporter_version: Version of MySQL Exporter.

nginx_exporter_version: Version of NGINX Exporter.

These variables are set at the top of the playbook and can be adjusted as needed for your environment.

🔒 Firewall Setup
The playbook configures firewalld rules to allow communication with the following services:

Node Exporter: Default port 9100
Redis Exporter: Default port 9121
MySQL Exporter: Default port 9104
NGINX Exporter: Default port 9113

✅ Prerequisites
Redis, MySQL, and NGINX must be installed and running on your target machines for their respective exporters to be configured.
Make sure the firewall is configured to allow the necessary ports.

🤝 Contributing
Feel free to fork this repository, create issues, or submit pull requests for improvements or bug fixes. Contributions are welcome!

📝 License
This project is licensed under the MIT License - see the LICENSE file for details.
