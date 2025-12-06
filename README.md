# 🛡️ Custom VPN Setup using EasyRSA & OpenVPN on AWS (Ubuntu)

This repository contains a complete setup guide, configuration files, and automation scripts to deploy a secure, self-hosted VPN using OpenVPN and EasyRSA on an AWS Ubuntu EC2 instance.
The goal of this project is to create a low-cost, private VPN server for secure remote access, encrypted communication, and controlled network routing.

# 🚀 Features

🔐 Custom CA (Certificate Authority) using EasyRSA

🧩 OpenVPN server configuration optimized for security and performance

👤 Client certificate generation for multiple users

🏗️ AWS Ubuntu EC2 deployment steps included

🛠️ Commands for managing certificates (revoke, renew, list)

📦 Optional scripts to automate setup

🔍 Troubleshooting guide for common OpenVPN issues

# 🏗️ Tech Stack

OpenVPN

EasyRSA 3

Ubuntu 20.04 / 22.04

AWS EC2 (t2.micro / t3.micro)

UFW / IPTables

# 📁 What This Repo Includes

/server/ → OpenVPN server configuration files

/easyrsa/ → PKI and certificate management scripts

/client-configs/ → Client profiles (.ovpn)

install.sh → Optional automated installation script

README.md → Step-by-step instructions

# 📘 How It Works (Short Summary)

Launch an Ubuntu EC2 instance on AWS

Install OpenVPN and EasyRSA

Create your own Certificate Authority (CA)

Generate server & client certificates

Configure OpenVPN server (UDP/TCP, port 1194, routing)

Enable IP forwarding & firewall rules

Start the VPN service

Export .ovpn files for client devices

# 🎯 Use Cases

Private VPN for your team or personal use

Secure browsing over public Wi-Fi

Accessing internal AWS or on-prem resources

Creating a learning environment for VPN & PKI

Lightweight alternative to commercial VPN services

# 🎯 Use Cases

Private VPN for your team or personal use

Secure browsing over public Wi-Fi

Accessing internal AWS or on-prem resources

Creating a learning environment for VPN & PKI

Lightweight alternative to commercial VPN services
