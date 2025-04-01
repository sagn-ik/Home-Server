# VPS Server Setup with Tailscale

## Overview
This guide provides step-by-step instructions to set up a VPS server on a Raspberry Pi and configure Tailscale for secure remote access.

## Prerequisites
Before proceeding, ensure you have:
- **Raspberry Pi OS (64-bit)** (or, any tailscale compatible linux distro)
- **Internet connection** (wired or Wi-Fi)
- **Tailscale account** (Sign up at [tailscale.com](https://tailscale.com/))

## Installation Steps

### 1. Update System Packages
Ensure your system is up to date:
```bash
sudo apt update && sudo apt upgrade -y
```

### 2. Install Tailscale
Download and install Tailscale using the official installation script:
```bash
curl -fsSL https://tailscale.com/install.sh | sh
```

### 3. Start and Authenticate Tailscale
Run the following command to authenticate your Raspberry Pi with Tailscale:
```bash
sudo tailscale up --authkey=YOUR_AUTH_KEY
```
> **Note:** Replace `YOUR_AUTH_KEY` with an authentication key from your Tailscale admin panel.

### 4. Verify Connection
Check the connection status and assigned IP:
```bash
tailscale status
```

### 5. Enable Tailscale on Boot
Ensure Tailscale starts automatically on reboot:
```bash
sudo systemctl enable --now tailscaled
```

## Usage
- To check the current IP address of your Raspberry Pi on the Tailscale network:
  ```bash
  tailscale ip -4
  ```
- To disconnect from Tailscale:
  ```bash
  sudo tailscale down
  ```

## Resources
- Official Tailscale Documentation: [https://tailscale.com/kb/](https://tailscale.com/kb/)
- Raspberry Pi Documentation: [https://www.raspberrypi.org/documentation/](https://www.raspberrypi.org/documentation/)

