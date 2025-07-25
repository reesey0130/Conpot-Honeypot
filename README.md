# ICS Honeypot Lab - Conpot

![Status](https://img.shields.io/badge/Project-Live-brightgreen?style=for-the-badge)
![Tool](https://img.shields.io/badge/Tool-Conpot-orange?style=for-the-badge&logo=python)
![Category](https://img.shields.io/badge/Type-ICS%20Simulation-blue?style=for-the-badge)
![OS](https://img.shields.io/badge/Platform-Ubuntu%2022.04-purple?style=for-the-badge&logo=ubuntu)

---

## Project Overview

This project simulates an Industrial Control System (ICS) environment using the **Conpot** honeypot. It exposes common industrial protocols like:

- **Modbus/TCP** (Port 502)
- **S7comm** (Siemens – Port 102)
- **HTTP** (Port 80 / 8800)
- **SNMP**, **TFTP**, **FTP**, **IPMI**

The goal is to emulate a real ICS/SCADA device and observe how attackers interact with exposed OT systems.

---

## Setup Instructions

### OS & Environment
- Ubuntu 22.04 LTS (VM)
- Python 3.10+
- Virtual Environment

###  Installation Steps

```bash
# Update system and install required packages
sudo apt update && sudo apt upgrade -y
sudo apt install -y python3 python3-pip python3-venv git build-essential libssl-dev libffi-dev libxml2-dev libxslt1-dev zlib1g-dev libjpeg-dev

# Set up virtual environment
python3 -m venv conpot-env
source conpot-env/bin/activate

# Clone and install Conpot
git clone https://github.com/mushorg/conpot.git
cd conpot
pip install --upgrade pip
pip install -r requirements.txt
pip install .

# Run Conpot with default template
conpot -t templates/default -f
