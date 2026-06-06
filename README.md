# Zabbix NOC Homelab 📊

Hi there! 👋 Welcome to my personal network monitoring lab.

I built this project because I wanted to go beyond networking theories and actually see what happens inside a real Network Operations Center (NOC).

## 🛠️ The Setup

I designed this lab to bridge a virtualized environment with my physical home network. Here is what's running under the hood:
* **The Brains:** Ubuntu Server running Zabbix 7.0 (hosted on VMware).
* **The Core:** A Cisco CSR1000v virtual router (IOS-XE) to simulate an enterprise core network.
* **The Edge:** A physical TP-Link TD-W8961N modem acting as the gateway.

## 🚀 What I Actually Did

* **SNMPv2 Configuration:** I enabled and secured SNMP on both the Cisco router and the TP-Link modem to pull live traffic data.
* **Automated Discovery (LLD):** Let Zabbix do the heavy lifting by automatically finding network interfaces, CPU usage, and memory stats using native templates.
* **Layer 7 Web Scenarios:** I didn't just want to know if the web server was reachable; I simulated user steps to check page load times, download speeds, and HTTP 200 OK responses.
* **Visual Topologies:** I drew a live Network Map. If a link goes down or a port is disconnected, the map visually alerts me just like a real NOC dashboard.
* **Bale Messenger Bot Alerts:** Integrated Zabbix Actions with a custom Webhook to send instant, real-time push notifications straight to my phone via the "Bale" messenger app whenever a critical trigger fires.
* **Taming the Database:** Set up Zabbix Housekeeping to regularly clean up raw `History` while keeping long-term `Trends`, ensuring the server doesn't crash from an overloaded DB.
* **Maintenance Windows:** Configured maintenance modes so I don't get flooded with false-positive alerts when I'm rebooting or updating the lab nodes.

## 📂 Inside this Repo
* `/dashboards`: Some screenshots showing the live traffic graphs, my NOC dashboard, and the network topology map.
* `/configs`: The exact CLI commands I used to configure SNMP and networking on the Cisco IOS-XE.
* `/templates`: A few custom Zabbix exports I used during my testing.

---
*I’m always tweaking and improving this lab as I learn more about system administration and network engineering. Feel free to explore the configs!*
