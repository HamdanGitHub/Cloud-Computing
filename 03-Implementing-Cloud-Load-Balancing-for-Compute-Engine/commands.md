# 💻 Commands Used

## Verify individual web servers

```bash
curl http://VM_EXTERNAL_IP
```

---

## Check backend health

```bash
gcloud compute backend-services get-health web-backend-service --global
```

---

## List Compute Engine instances

```bash
gcloud compute instances list
```

---

## List forwarding rules

```bash
gcloud compute forwarding-rules list
```

---

## List backend services

```bash
gcloud compute backend-services list
```

---

## List health checks

```bash
gcloud compute health-checks list
```

---

## List managed instance groups

```bash
gcloud compute instance-groups managed list
```

---

## List firewall rules

```bash
gcloud compute firewall-rules list
```

---

## List static external IP addresses

```bash
gcloud compute addresses list
```
