 Working and understanding VPN
## Overview
This repository documents hands-on work on VPN and Tor privacy tools, focusing on:

- Using **Kalitorify** on Kali Linux to route traffic through the Tor network (Task 8)
- Understanding browsing speed differences between normal and VPN connections

---

## Task 8: Routing Kali Linux Traffic Through Tor with Kalitorify

### Objective
Route all network traffic through the Tor network using Kalitorify to ensure anonymity and DNS leak protection.

### Prerequisites
- Kali Linux system
- Internet access
- Basic command line familiarity

### Setup Steps

1. **Clone Kalitorify repository**
   ```bash
   git clone https://github.com/brainfucksec/kalitorify.git
   cd kalitorify
Install Tor

bash
Copy code
sudo apt update
sudo apt install tor -y
Enable Tor transparent proxy using Kalitorify

bash
Copy code
sudo ./kalitorify.sh --tor
Verify Tor service status

bash
Copy code
sudo systemctl status tor
Verify IP and anonymity

Visit https://check.torproject.org to confirm traffic routes through Tor.

Test DNS leak protection

Use https://dnsleaktest.com and run the standard test to ensure no DNS leaks.

Stop Kalitorify transparent proxy (optional)

bash
Copy code
sudo ./kalitorify.sh --stop
Results & Observations
Checkpoint	Result
Tor Service	Active and running
IP Address	Changed to Tor exit node
DNS Leak	No DNS leaks detected
Browsing Speed	Slower than normal connection
| Aspect           | Normal Connection                   | VPN Connection                     |
| ---------------- | ----------------------------------- | ---------------------------------- |
| Speed            | Fastest, direct internet access     | Slower due to encryption & routing |
| Latency          | Low                                 | Increased latency                  |
| Bandwidth        | Full ISP bandwidth                  | Reduced bandwidth due to overhead  |
| Encryption       | Minimal or HTTPS only               | Full traffic encrypted             |
| Typical Use Case | Streaming, gaming, general browsing | Privacy, anonymity, geo-unblocking |
Summary
Kalitorify + Tor offers strong anonymity and DNS leak protection but at a cost to browsing speed.

VPNs provide encrypted tunnels and better speeds compared to Tor, but may still reduce browsing performance.

Choose Tor when maximum privacy/anonymity is required.

Choose VPN for a balance of privacy and speed.
