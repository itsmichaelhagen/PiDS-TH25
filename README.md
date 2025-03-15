# Raspberry Pi Project: PiDS-TH25
### Powered with Suricata IDS (Intrusion Detection System) and Zeek ITA (Intrusion Traffic Analysis)

Turn a raspberry pi into a NIDS and threat hunting tool, capable of connecting to any network in range to analyze network traffic and potential vulnerabilities.

## Table of Contents
1. [Project Overview] (#project-overview)
2. [Hardware Used] (#hardware-used)
3. [Suricata Installation Guide] (#suricata-installation-guide)
4. [Zeek and ELK Stack] (#zeek-and-elk-stack)
5. [Screenshots] (#screenshots)
6. [Author] (#author)

--

## Project Overview
Using a Raspberry Pi (Raspberry Pi 4, Model B from CanaKit), configuring and adding enhancements to create a fully functional NIDS and threat hunter. 

Pre-requisites to begin the project include a Raspberry Pi, 256GB storage (external MicroSD), 8GB RAM, and WiFi adapter. The setup is headless and meant to be able to connect to via SSH from any device on the network. Connected to GUI for remote desktop using RealVNC. Reconfigure LAN settings if moving to another network. 

--

## Hardware Used
1) **CanaKit Raspberry Pi 4**
2) **256GB MicroSD Card**
3) **USB WiFi Adapter (Monitor Mode)**
4) **Ethernet Cable (Wired Traffic Analysis)**

--

## Suricata Installation Guide
### 1. Update OS and Install Dependencies
``` bash
sudo apt update && sudo apt upgrade -y
sudo apt install libpcre3 libpcre3-dbg libpcre3-dev build-essential \
  libpcap-dev libyaml-0-2 libyaml-dev pkg-config zlib1g zlib1g-dev \
  libmagic-dev libjansson-dev rustc cargo python3-yaml liblua5.1-dev
```
### 2. Download Suricata and Navigate to Directory
``` bash
wget https://www.openinfosecfoundation.org/download/suricata-7.0.3.tar.gz
tar -xvf suricata-7.0.3.tar.gz
cd suricata-7.0.3/
```
### 3. Compile Suricata
``` bash
./configure --prefix=/usr --sysconfdir=/etc --localstatedir=/var --enable-nfqueue --enable-lua
make -j$(nproc)
```
### 4. Install Suricata
``` bash
sudo make install
sudo make install-full
sudo ldconfig
```
### 5. Verify Suricata Installation
``` bash
suricata -v
```
--
## Zeek and ELK Stack

TBA

--

## Screenshots

TBA

--

## Author

TBA

--
