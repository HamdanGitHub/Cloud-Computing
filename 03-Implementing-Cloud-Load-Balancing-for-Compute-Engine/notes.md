# 📝 Notes

## Compute Engine

- Created three VM instances:
  - web1
  - web2
  - web3

- Region:
  - us-west4

- Zone:
  - us-west4-a

- Machine Type:
  - e2-small

- Operating System:
  - Debian 12

---

## Startup Script

Installed Apache automatically during VM creation.

The startup script:

- Updates package lists
- Installs Apache
- Starts Apache
- Creates a custom web page for each server

---

## Firewall Rules

Created firewall rules allowing HTTP traffic on port 80.

Tags used:

- network-lb-tag
- allow-health-check

---

## Network Load Balancer

Configured:

- Static External IP
- Target Pool
- Forwarding Rule

Purpose:

Distributes incoming TCP traffic among multiple Compute Engine instances.

---

## HTTP Load Balancer

Created:

- Instance Template
- Managed Instance Group (MIG)
- Backend Service
- Health Check
- URL Map
- Target HTTP Proxy
- Global Forwarding Rule

Purpose:

Distributes HTTP requests across healthy backend instances.

---

## Managed Instance Group (MIG)

Benefits:

- Automatically manages VM instances
- Supports auto-healing
- Works seamlessly with HTTP Load Balancing

---

## Health Checks

Configured HTTP Health Checks to monitor backend instance health.

Verified backend status using:

- HEALTHY

before testing the load balancer.

---

## Skills Learned

- Compute Engine
- Virtual Machines
- Startup Scripts
- Firewall Rules
- Apache Web Server
- Network Load Balancing
- HTTP Load Balancing
- Backend Services
- Health Checks
- Managed Instance Groups
- High Availability
