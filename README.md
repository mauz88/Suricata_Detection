# Suricata IDS Test – Portfolio Project

## Overview
This project demonstrates the setup, configuration, and testing of **Suricata**, an open-source Intrusion Detection System (IDS). The goal was to simulate a network scan attack and capture the resulting alerts and logs for analysis.

The test includes:

- Suricata configuration
- Simulated network scan using Nmap
- Log collection in JSON and fast formats
- Evidence of alerts triggered by malicious activity

---

## Environment

- **Operating System:** Amazon Linux 2 (EC2 instance)
- **Suricata Version:** 6.0.9
- **Network Interface Used:** `ens5`
- **Tools:** Nmap (for scanning)

---

## Steps Performed

1. Install and Configure Suricata

- Suricata installed from source.
- Verified configuration using test mode:

sudo suricata -T -c /etc/suricata/suricata.yaml

Ensured rules were correctly loaded. For testing purposes only scan detection rule was kept.

2. Run Suricata

Suricata started manually on the main network interface:

sudo suricata -c /etc/suricata/suricata.yaml -i ens5

Logs were automatically generated in:

/var/log/suricata/fast.log – human-readable alerts

/var/log/suricata/eve.json – structured JSON logs

3. Simulate Attack
A network scan was performed from a remote machine using Nmap:

nmap -A -p 1-1000 18.232.65.49

This triggered alerts in Suricata, captured in both fast.log and eve.json.

4. Capture Evidence

Collected files for the portfolio:

Suricata configuration (yaml file)

fast log (alerts)

eve.json (structured logs)

nmap scan sample (attack simulation)

screenshots as well attached.

5. Conclusion

This project demonstrates the ability to:

Configure Suricata IDS

Run and test rules


Capture and analyze alerts from network attacks
